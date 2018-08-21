## Prep-AD
- [Everything you need to get started with Active Directory](https://blogs.technet.microsoft.com/ashleymcglone/2012/01/03/everything-you-need-to-get-started-with-active-directory/)
- [Capacity Planning for Active Directory Domain Services](https://social.technet.microsoft.com/wiki/contents/articles/14355.capacity-planning-for-active-directory-domain-services.aspx)
- [PowerShell: How to install a Domain Controller with Server Core](https://sid-500.com/2017/07/01/powershell-how-to-install-a-domain-controller-with-server-core/)
- [Setting up Active Directory via PowerShell](https://blogs.technet.microsoft.com/uktechnet/2016/06/08/setting-up-active-directory-via-powershell/)
- [Set Up Child Domain on Windows Server 2016](http://www.itprotoday.com/windows-8/set-child-domain-windows-server-2016)
- [Why you shouldn't use .local in your Active Directory domain name](http://www.mdmarra.com/2012/11/why-you-shouldnt-use-local-in-your.html)
- [Active Directory: Best Practices for Internal Domain and Network Names](https://social.technet.microsoft.com/wiki/contents/articles/34981.active-directory-best-practices-for-internal-domain-and-network-names.aspx)
- [Designing OU Structures that Work: Choosing the Best Model](https://technet.microsoft.com/en-us/library/2008.05.oudesign.aspx)
- [You've just stood up a brand new AD and get to build it from scratch, what are the first things you change or put into place?](https://www.reddit.com/r/sysadmin/comments/94hjpo/youve_just_stood_up_a_brand_new_ad_and_get_to/)

## Active Directory Domain Services - Disaster Recovery(AD DS - DR)
- [Some of my notes when it comes to Disaster Recovery of Active directory and security](https://www.reddit.com/r/sysadmin/comments/8whlon/some_of_my_notes_when_it_comes_to_disaster/)

## Active Directory Domain Services (AD DS)
- [Active Directory Domain Services 2016](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/active-directory-domain-services)
- [Active Directory Domain Naming Considerations](https://social.technet.microsoft.com/wiki/contents/articles/17974.active-directory-domain-naming-considerations.aspx)
- [Active Directory – Installing Second or Additional Domain Controller](https://harmikbatth.com/2017/04/25/active-directory-installing-second-or-additional-domain-controller/)

Example:

As an example, if I ever started a consulting business and used the Internet-facing website mdmarra.com as my company's site, I should name my Active Directory domain ad.mdmarra.com or internal.mdmarra.com, or something similar. You want to avoid making up a TLD like .local and you also want to avoid the headache of using mdmarra.com for the Internet-facing zone and the internal zone.

## DNS
- [DNS servers on adapter name should include the loopback address, but not as the first entry](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff807362(v=ws.10))
- [DNS client and server best practices for AD](https://blogs.technet.microsoft.com/askds/2010/07/17/friday-mail-sack-saturday-edition/#dnsbest)
- [Advice for best practices for DNS on Domain Controllers](https://www.reddit.com/r/sysadmin/comments/8l28bl/advice_for_best_practices_for_dns_on_domain/)

Example:

|                      | Domain Controller 1 | Domain Controller 2 | Domain Controller 3 |
|----------------------|---------------------|---------------------|---------------------|
| Preferred DNS server | Domain Controller 2 | Domain Controller 1 | Domain Controller 1 |
| Alternate DNS server | Domain Controller 3 | Domain Controller 3 | Domain Controller 2 |
| Tertiary             |       127.0.01      |       127.0.01      |       127.0.01      |

## DHCP
- [Plan DHCP Deployment](https://docs.microsoft.com/en-us/windows-server/networking/technologies/dhcp/dhcp-deploy-wps#bkmk_plan)
- [DHCP & DNS Scavenging](https://www.reddit.com/r/sysadmin/comments/8biwvg/dhcp_dns_scavenging/)

## Users and Groups
- [ARCHIVED: In Active Directory, what are the differences between universal, global, and domain local groups?](https://kb.iu.edu/d/ahrl)
- [When to use a Domain Local Group versus Global Group](https://community.spiceworks.com/topic/306028-when-to-use-a-domain-local-group-versus-global-group)
- [Active Directory Security Groups](https://docs.microsoft.com/en-us/windows/security/identity-protection/access-control/active-directory-security-groups)
- [Best Practices for Securing Active Directory](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/best-practices-for-securing-active-directory)

## Windows Time Service
- [Configuring the Windows Time Service in an Active Directory Forest – A step by step with a Contingency Plan](https://blogs.msmvps.com/acefekay/2014/04/26/configuring-the-windows-time-service/)
- [How To Synchronize Microsoft Windows to a NTP Server](https://timetoolsltd.com/time-sync/how-to-synchronize-microsoft-windows-to-a-ntp-server/)
- [Time.windows.com](https://www.reddit.com/r/sysadmin/comments/8qcsyt/timewindowscom/)
- [What is the best to use as an NTP server in windows environment?](https://www.reddit.com/r/sysadmin/comments/8gh6h6/what_is_the_best_to_use_as_an_ntp_server_in/)
- [“It’s Simple!” – Time Configuration in Active Directory](https://blogs.technet.microsoft.com/nepapfe/2013/03/01/its-simple-time-configuration-in-active-directory/)
- [Do w32tm NTP servers transfer w/FSMO?](https://www.reddit.com/r/sysadmin/comments/95bc50/do_w32tm_ntp_servers_transfer_wfsmo/)

## Remove DC
- [How to remove completely orphaned Domain Controller](https://support.microsoft.com/en-ca/help/555846)
- [Best practices for domain controller decommission?](https://www.reddit.com/r/sysadmin/comments/8n8owx/best_practices_for_domain_controller_decommission/)
- [Question: Demoting a domain controller running as a DFS namespace and wanting to keep it as a DFS namespace](https://www.reddit.com/r/sysadmin/comments/8juixh/question_demoting_a_domain_controller_running_as/)
- [Successful demotion of domain controller now what should I clean in DNS?](https://www.reddit.com/r/sysadmin/comments/917alr/successful_demotion_of_domain_controller_now_what/)

## AD Security
- [Securing Privileged Access](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access)
- [Securing Privileged Access Reference Material](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material)
- [Implementing Least-Privilege Administrative Models](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/implementing-least-privilege-administrative-models)

## Others
- [Forgot the domain admin password?](https://4sysops.com/archives/forgot-the-domain-admin-password/)
- [How to: Make sure Active Drecitory Domain Controllers have an NTDS object](http://techgenix.com/domain-controllers-ntds-object/)
- [Any way to send Active Directory users email after 30 days of inactivity?](https://www.reddit.com/r/sysadmin/comments/8fujc1/any_way_to_send_active_directory_users_email/)
- [How to create and verify and Active Directory forest external trust](http://techgenix.com/active-directory-forest-external-trust/)
- [Active Directory Flexible Single-Master (FSMO) in Action](https://sid-500.com/2017/11/19/active-directory-flexible-single-master-fsmo-in-action/)
- [Understanding Urgent Replication](https://blogs.technet.microsoft.com/kenstcyr/2008/07/05/understanding-urgent-replication/)
- [What the fuck is sysvol](https://www.reddit.com/r/sysadmin/comments/97h1bc/what_the_fuck_is_sysvol/)
- [Server 2016 (Hyper-V Role only) adding to domain](https://www.reddit.com/r/sysadmin/comments/9661d8/server_2016_hyperv_role_only_adding_to_domain/)


## AD DS - Tools 
- [Repadmin](http://techgenix.com/repadmin-tool/)
   - [Active Directory Replication Status Tool](https://www.microsoft.com/en-us/download/details.aspx?id=30005)
- [User Profile migrate](https://www.forensit.com/domain-migration.html)
- [AD Overview Graphical Tool: Active Directory Domain Services Section](https://sid-500.com/2018/03/25/active-directory-domain-services-section-tool-for-active-directory-administrators/)
- [AdRestore v1.1](https://docs.microsoft.com/en-us/sysinternals/downloads/adrestore)
- [Active Directory Migration Tool version 3.2](https://www.microsoft.com/en-us/download/details.aspx?id=56570)
- [Active Directory migration tool: A comprehensive guide](http://techgenix.com/active-directory-migration-tool/)
- [Network Diagnostics: How to run DCDIAG remotely on all Domain Controllers](http://techgenix.com/run-dcdiag-remotely-powershell/)
- [Integrating database of pwned password hashes with Microsoft AD - haveibeenpwned with AD! Yay](https://www.reddit.com/r/sysadmin/comments/8bod2o/integrating_database_of_pwned_password_hashes/)
- [How to: Interforest migration using Active Directory migration tool](http://techgenix.com/interforest-migration/)

## Troubleshoot
- [How to rebuild the SYSVOL tree and its content in a domain](https://support.microsoft.com/en-us/help/315457/how-to-rebuild-the-sysvol-tree-and-its-content-in-a-domain)


## AD DS - Websites
- [Active Directory Security](https://adsecurity.org/)
- [Active Directory Best Practices - Ten Years Later](https://www.youtube.com/watch?v=_Q-rLcBKJaw)
