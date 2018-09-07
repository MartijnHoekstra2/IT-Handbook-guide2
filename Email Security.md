## Email Security
* [Lessons Learned from the US Federal Government’s Ongoing Deployment of SPF and DMARC](https://seanthegeek.net/310/spf-dmarc-federal-government-checkdmarc/)
* [Microsoft SPF, DKIM & DMARC Information](https://blogs.technet.microsoft.com/fasttracktips/2016/07/16/spf-dkim-dmarc-and-exchange-online/)
- [SPF shorterner / limit advice?](https://www.reddit.com/r/sysadmin/comments/96ybi0/spf_shorterner_limit_advice/)
* [SPF/PTR records](https://www.reddit.com/r/sysadmin/comments/9dhw98/spfptr_records/)

##### SPF
* [SPF Check](https://www.fraudmarc.com/spf-record-check/)
* [SPF Creation](https://www.spfwizard.net/)
* [SPF 10 DNS lookup limit - option 1](https://serverfault.com/questions/584708/is-the-10-dns-lookup-limit-in-the-spf-spec-typically-enforced)
* [SPF 10 DNS lookup limit - option 2](https://www.reddit.com/r/sysadmin/comments/8ghwjo/spf_10_dns_lookup_limit/)
* [What is an SPF Record](https://www.digitalocean.com/community/tutorials/how-to-use-an-spf-record-to-prevent-spoofing-improve-e-mail-reliability)
* [Information about: SPF](http://www.openspf.org/)
* [Information about: Protection against email spoofing: SPF, DKIM and DMARC](https://techblog.exonet.nl/2017-02-03-spf-dkim-dmarc)
* [Information about: How to use an SPF Record to Prevent Spoofing & Improve Email Reliability](https://www.digitalocean.com/community/tutorials/how-to-use-an-spf-record-to-prevent-spoofing-improve-e-mail-reliability)

##### DKIM
* [What is an DKIM Record](https://support.dnsimple.com/articles/dkim-record/)
- [DKIM Exchange](https://github.com/Pro/dkim-exchange)

##### DMARC
* [DMARC Check - option 1](https://www.fraudmarc.com/dmarc-check/)
* [DMARC Check - option 2](https://dmarcian.com/dmarc-tools/)
* [DMARC Check - option 3](https://dmarc.org/resources/products-and-services/)
* [DMARC Record Published](https://mxtoolbox.com/problem/dmarc/dmarc-record-published)

## Types of Email
1. Cloud-Based
1. Hybrid
1. On-Premises

## Steps of Configuring / Options / Setup / Tips
1. DNS: Configure DNS and PRT record
1. SPF: Prevents spoofing
1. DKIM: Will validates that an organization delivering an email has the right to do so
1. DMARC: Will validated incoming messages
1. Email security Appliance / Cloud-based / Service / Software
1. AV on clients
1. If possible setup a Spam confidence levels (SCL)
1. Use a Realtime BlackList (RBL)
1. Setup or know the Outgoing Mail Control (limit sending per user / per day)
1. Potential configure Geo IP to block specific countries. Beaware of the redundant email servers when using Cloud-Based
1. Attachement filtering (Block .exe) and scan zip files atleast 2 layers deep
1. If available use some sort of Advanced Threat Protection (Link reading / Sandboxing) 
1. Configure the SPAM filter
1. Sender ID Filtering
1. Configure SPF Record Hard/Soft fail
1. Email encryption (TLS if available)
1. User training for example a webinar
1. When sending out mass email set a banner for legal stand point
1. Don't post any email addresses on your website instead of that use a contact form. Crawlers will catch your mail address
1. Install and Configure MFA (Multi Factor Authentication)
1. Port 25 outbound should be blocked for anything that's not a mail server. Of course exceptions can be made on a case by case basis.

## Gotcha's
* You can have only 1 DMARC record per (top level) domain
* Do a check every month to see if you are not blacklisted
