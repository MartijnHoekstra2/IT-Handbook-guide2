https://www.digitalocean.com/community/tutorials/how-to-use-an-spf-record-to-prevent-spoofing-improve-e-mail-reliability
https://serverfault.com/questions/584708/is-the-10-dns-lookup-limit-in-the-spf-spec-typically-enforced
https://www.reddit.com/r/sysadmin/comments/8ghwjo/spf_10_dns_lookup_limit/
https://www.reddit.com/r/sysadmin/comments/8f1hwf/dmarc_opensource_analyser_software/
https://www.reddit.com/r/sysadmin/comments/8mxd94/dmarc_safe_to_use_preject_pct100_if_all_known/
* [SPF Wizard](https://www.spfwizard.net/)
* [Sender Policy Framework](http://www.openspf.org/)
* [A free tool to monitor & implement DMARC](https://dmarc.postmarkapp.com/)
* [DMARCian](https://dmarcian.com/
* [SMTP Mail from External Provider - Quick Question](https://www.reddit.com/r/sysadmin/comments/8s2enh/smtp_mail_from_external_provider_quick_question/

# Mail Security: SPF, DKIM and DMARC
[Source](http://techblog.exonet.nl/2017-02-03-spf-dkim-dmarc)
</br>
</br>
Email was developed in the early 1970s when the internet was still a research project with mainly university networks connected. It relies on the Simple Mail Transfer Protocol (SMTP), which is a protocol designed to transmit messages between systems. At the time when email was developed, security was not really a concern. Everyone on these networks could be trusted; why on earth would someone abuse it?

A few decades later it’s hard to imagine the internet and email without security. Email as we know it today is heavily abused with spoofed emails, trying to cheat and mislead people. Techniques which can help to protect against spoofing are  **SPF**,  **DKIM**  and  **DMARC**. In this post we will explain what these protections are and how they work.

## From

By default, email clients only show a few pretty lines including the  `From`  address:

```ruby
To: John Doe <john.doe@example.net>
From: Security <security@exonet.nl>
Subject: Please verify your account password
```

This  `From`  address is called the  `header-from`  address. The tricky part is: it does not mean that an email really came from that header-from address. There is another one not displayed, which is called the  `envelope-from`  address.

```ruby
Received: from localhost ([127.0.0.1] helo=mail.example.com)
    by mail.example.com with esmtp (Exim 4.87) (envelope-from
    <xyz@example.com>) id 1cUgTa-0001nf-Vn for 
    john.doe@exmaple.net; Fri, 03 Feb 2017 10:12:43 +0100
From: Security <security@exonet.nl>
```

An email actually consists of two parts. The first part is SMTP with the envelope-from, responsible for the email delivery. The second part is the message, the actual email with the header-from. The header-from and the envelope-from are independent from each other, these can be different addresses. If an email client shows security@exonet.nl (header-from) the SMTP headers could contain xyz@example.com (envelope-from), which is not displayed.

Having different addresses is by design, because sometimes it is necessary to change the envelope-from. This is also why email addresses can be spoofed, because both addresses can be anything and recipients (mostly) only see the header-from address.

## SPF

**Sender Policy Framework**  (SPF) is currently probably the most applied email protection. A SPF record is actually a record in DNS with a list of servers which are authorised to send mail for a specific domain. If a SPF record is published, a receiving server is able to validate if an email is coming from an authorised server. Depending on the SPF policy, an email may  `Pass`  (accept),  `SoftFail`  (move to spam) or  `Fail`  (reject).

Example SPF record in DNS:

```ruby
example.com. IN TXT "v=spf1 a mx include:_spf.exonet.nl -all”
```

The  `v=spf1`  is currently default, it defines the protocol version. The other mechanisms tell a receiving server that only the  `A`  records,  `MX`  records and the included SPF record from  `_spf.exonet.nl`  are authorised to send mail for  `example.com`. The  `-all`  matches anything else. This one tells a receiving server to reject a mail if it was not send from an authorised server.

SPF does have it’s limitations. A big shortcoming is that it  **only protects the envelope-from address**. Which means if an email passes SPF checks, the header-from may still be a spoofed address. SPF also breaks email forwards if the forwarding server is not published in the SPF record from the original sending domain.  [Sender Rewriting Scheme](https://en.wikipedia.org/wiki/Sender_Rewriting_Scheme)  (SRS) is an attempt to fix this problem, but it’s currently not widely implemented. Even with SRS support a forward may still break with DMARC (explained below).

## DKIM

**DomainKeys Identified Mail**  (DKIM) uses cryptographic keys to add signatures on emails, which can be verified with a cryptographic public key in DNS by receiving mail servers.

Example DKIM record in DNS:

```ruby
mail._domainkey.example.com. IN TXT "v=DKIM1; k=rsa; p=MIIBIjANBgkqhkiG9wQBAQEFAAOCAQ8AMIIBCgKCAQEA1S59rofl+T1eUQ0OGnhCJMG15iyqxN9VITKOXQ5jYg5olV+dXYCCB43Ub1DFbOpvCNPsdTt2gH1JZW8FNMhIrE4fMvWbS54wpa9QhzfBNV7knDq4U3s84kcRlsOuHaA1o7DgZ7u9iHFuMdw4K7goRZdmfW/L7utC108Gmrq4oFxnsJSrEMALsu3gyIGOK0L2STYWkKAlmYNmv8QauOa2m6mIyBl0mRtH8Qdm8A5dY0xa1KKC41RG+FyMcecPfu+FznFDhqTA+wlZkIyl2eG/HLuRExIe5R9uoVirkO3wj3M2jR5S8K4HcWINF6DiAozQGRK/CIScFGSy9DH4wfuS0QIDAQAB";
```

The subdomain  `mail._domainkey`  contains the selector (`mail`). The selector is required to define a specific DKIM record in case there are multiple DKIM records present. The TXT record contains the protocol version  `v=DKIM1`, the key type  `k=rsa`  followed by the actual public key  `p=<...>`.

If an email has been signed with DKIM, the headers will have a DKIM-Signature which consists of hashed values (header fields and message body). These values are generated with the private key, which is only known to the owner of the sending domain.

Example DKIM-Signature:

```ruby
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; d=example.com ; s=mail; 

h=Message-ID:Subject:To:From:Date:Content-Transfer-Encoding: Content-Type:MIME-Version:Sender:Reply-To:Cc:Content-ID:Content-Description: Resent-Date:Resent-From:Resent-Sender:Resent-To:Resent-Cc:Resent-Message-ID: In-Reply-To:References:List-Id:List-Help:List-Unsubscribe:List-Subscribe: List-Post:List-Owner:List-Archive;

bh=tGRRtnsaIk2pynmMYhtRkZJY/5jaVEPy3kSOhAcg2tg=;

b=a/ZthBQYLG7Sh0x+8ShFS4CCvF ojIhug0J8aXqtJYWMPAEpnz8U2ytXGupxDP3mgututZ4MFsDPGvH+vgyXg778Djzj5939CnYoIl6W 4KPSQ7NKQy0dFoRCXs6KE0ejE8GhuPFGAJL+RhUBRDyyXl68NugXf/NLK210XziY05pXXbg9h3H0P GE0KHz3iy+j8AEgjr5X+Dwj71iagpzRCzPFRGp5HsorsGIKli0yEHVWZBbK6+XcJ90MuePpC2yYSN GJ20nhYrE+glijopMJ8LeIC7oJuzgPaOa4x5ugElTOpdLYLAMV+nZEu50uqVEr2REh7KbJ1KkqEw/ fkNxnKvA==;
```

This signature shows that the signing domain  `d=example.com`  with selector  `s=mail`  can be used to lookup the public key in DNS. The other lines are the header fields  `h=`, the body hash  `bh=`  and the signature data  `b=`. The hashed values and the signature combined with the public key can be verified by a receiving server and must match to pass a validation. If any of the header fields or the message body has been altered during the email delivery, the validation will fail.

However, an attacker can also setup DKIM and sign malicious emails from another domain. For example, an attacker could use xyz@example.com (envelope-from) and sign all the headers including security@exonet.nl (header-from). The DKIM validation would perfectly pass, because a receiving server  **only verifies the DKIM record for example.com (`d=domain`)**.

DKIM helps to validate the actual email content and headers, but it doesn’t prevent attackers from abusing the header-from address. It also doesn’t tell what a receiving server should do if a signature validation fails. This is where DMARC comes into the picture.

## DMARC

**Domain-based Message Authentication, Reporting and Conformance**  (DMARC) is an anti-spoofing protection built on top of SPF and DKIM. It allows the owner of a domain to control email for a domain by publishing a DMARC policy in DNS. The policy tells a receiving server to either  `quarantine`  (move to spam) or  `reject`  (do not accept) the email if a validation fails. The biggest advantage of DMARC is that it also checks the header-from address.

Example DMARC record in DNS:

```ruby
_dmarc.example.com. IN TXT "v=DMARC1\; p=reject\; rua=mailto:postmaster@example.com"
```

Subdomain  `_dmarc`  is a default prefix for DMARC. The TXT record contains the protocol version  `v=DMARC1`, the policy  `p=reject`  and a reporting email address  `rua=mailto:<...>`. The reporting email address is useful for domain administrators to analyse email delivery. If a receiving server supports DMARC, it will send reports to the  `rua=`  address.

DMARC uses a concept which is called  **alignment**. This checks if the  `header-from`matches with the  `envelope-from`  (SPF) or with the  `d=domain`  (DKIM). A DMARC policy requires that either SPF and/or DKIM passes. It does not require both to pass because, if an email has been forwarded, SPF checks will probably fail but DKIM should still pass (if nothing has been altered). However, even if SPF and DKIM both pass, DMARC still fails if the alignment does not match.

## Conclusion

SPF, DKIM and DMARC together can be considered a best practice to finally prevent spoofing and make email more trustworthy. In an ideal world every domain would have these anti-spoofing protections enabled. Unfortunately it is not always that simple because a domain can have multiple mail servers on various locations. It requires some investigation first before all protections can be enabled. However, we do believe it is worthwhile to implement these protections because both, the owner of a domain and the recipients, will benefit from it.

## Information
* https://mxtoolbox.com/ 
* https://www.fraudmarc.com/spf-record-check/
* You can have only 1 DMARC record per (top level) domain AFAIK.
* Do a check every month to see if you are not blacklisted:heavy_check_mark:
* [Lessons Learned from the US Federal Government’s Ongoing Deployment of SPF and DMARC](https://seanthegeek.net/310/spf-dmarc-federal-government-checkdmarc/)
