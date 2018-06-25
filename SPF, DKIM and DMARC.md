## SPF, DKIM and DMARC
* [Microsoft SPF, DKIM & DMARC Information](https://blogs.technet.microsoft.com/fasttracktips/2016/07/16/spf-dkim-dmarc-and-exchange-online/)
* [Information about: SPF](http://www.openspf.org/)
* [Information about: Protection against email spoofing: SPF, DKIM and DMARC](https://techblog.exonet.nl/2017-02-03-spf-dkim-dmarc)
* [Information about: How to use an SPF Record to Prevent Spoofing & Improve E-mail Reliability](https://www.digitalocean.com/community/tutorials/how-to-use-an-spf-record-to-prevent-spoofing-improve-e-mail-reliability)

* [SPF Check](https://www.fraudmarc.com/spf-record-check/)
* [SPF Creation](https://www.spfwizard.net/)
* [SPF 10 DNS lookup limit - option 1](https://serverfault.com/questions/584708/is-the-10-dns-lookup-limit-in-the-spf-spec-typically-enforced)
* [SPF 10 DNS lookup limit - option 2](https://www.reddit.com/r/sysadmin/comments/8ghwjo/spf_10_dns_lookup_limit/)
* [What is an SPF Record](https://www.digitalocean.com/community/tutorials/how-to-use-an-spf-record-to-prevent-spoofing-improve-e-mail-reliability)
* [What is an DKIM Record](https://support.dnsimple.com/articles/dkim-record/)
* [DMARC Check - option 1](https://www.fraudmarc.com/dmarc-check/)
* [DMARC Check - option 2](https://dmarcian.com/dmarc-tools/)
* [DMARC Record Published](https://mxtoolbox.com/problem/dmarc/dmarc-record-published)

## Types of mail
1. Cloud-Based
1. Hybrid
1. On-Premises

## Step of setup
1. DNS: Configure DNS and PRT record
1. SPF: Prevent spoofing
1. DKIM: Will validates that an organization delivering an email has the right to do so
1. DMARC: Will validated incoming messages
1. Email security Appliance / Cloud-based / Service / Software
1. If possible setup a Spam confidence levels (SCL)
1. Use a Realtime BlackList (RBL)
1. Setup or know the Outgoing Mail Control (limit sending per user / per day)
1. Potential configure Geo IP to block specific countries. Beaware of the redundant mail servers when using Cloud-Based
1. Attachement filtering (Block .exe), and scan zip files atleast 2 layers deep.

## Gotcha's & Information
* You can have only 1 DMARC record per (top level) domain
* Do a check every month to see if you are not blacklisted
* [MX Toolbox](https://mxtoolbox.com/)
* [Lessons Learned from the US Federal Government’s Ongoing Deployment of SPF and DMARC](https://seanthegeek.net/310/spf-dmarc-federal-government-checkdmarc/)
