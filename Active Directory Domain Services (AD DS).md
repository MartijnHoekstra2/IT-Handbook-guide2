   - [Securing Privileged Access](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access)
   - [Securing Privileged Access Reference Material](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material)

## Active Directory Domain Services (AD DS)
* [Active Directory Domain Services 2016](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/active-directory-domain-services)
* [Active Directory Domain Naming Considerations](https://social.technet.microsoft.com/wiki/contents/articles/17974.active-directory-domain-naming-considerations.aspx)

Example:

As an example, if I ever started a consulting business and used the Internet-facing website mdmarra.com as my company's site, I should name my Active Directory domain ad.mdmarra.com or internal.mdmarra.com, or something similar. You want to avoid making up a TLD like .local and you also want to avoid the headache of using mdmarra.com for the Internet-facing zone and the internal zone.

## DNS
* [DNS servers on adapter name should include the loopback address, but not as the first entry](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff807362(v=ws.10))
* [DNS client and server best practices for AD](https://blogs.technet.microsoft.com/askds/2010/07/17/friday-mail-sack-saturday-edition/#dnsbest)

Example:

|                      | Domain Controller 1 | Domain Controller 2 | Domain Controller 3 |
|----------------------|---------------------|---------------------|---------------------|
| Preferred DNS server | Domain Controller 2 | Domain Controller 1 | Domain Controller 1 |
| Alternate DNS server | Domain Controller 3 | Domain Controller 3 | Domain Controller 2 |
| Tertiary             |       127.0.01      |       127.0.01      |       127.0.01      |

## Users and Groups
* [ARCHIVED: In Active Directory, what are the differences between universal, global, and domain local groups?](https://kb.iu.edu/d/ahrl)
* [When to use a Domain Local Group versus Global Group](https://community.spiceworks.com/topic/306028-when-to-use-a-domain-local-group-versus-global-group)
* [Active Directory Security Groups](https://docs.microsoft.com/en-us/windows/security/identity-protection/access-control/active-directory-security-groups)
* [Best Practices for Securing Active Directory](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/best-practices-for-securing-active-directory)

## Windows Time Service
* [Configuring the Windows Time Service in an Active Directory Forest – A step by step with a Contingency Plan](https://blogs.msmvps.com/acefekay/2014/04/26/configuring-the-windows-time-service/)
* [How To Synchronize Microsoft Windows to a NTP Server](https://timetoolsltd.com/time-sync/how-to-synchronize-microsoft-windows-to-a-ntp-server/)
* [Time.windows.com](https://www.reddit.com/r/sysadmin/comments/8qcsyt/timewindowscom/)
* [What is the best to use as an NTP server in windows environment?](https://www.reddit.com/r/sysadmin/comments/8gh6h6/what_is_the_best_to_use_as_an_ntp_server_in/)

## AD DS - Tools 
* [Repadmin](http://techgenix.com/repadmin-tool/)
   * [Active Directory Replication Status Tool](https://www.microsoft.com/en-us/download/details.aspx?id=30005)
* [User Profile migrate](https://www.forensit.com/domain-migration.html)
* [AD Overview Graphical Tool: Active Directory Domain Services Section](https://sid-500.com/2018/03/25/active-directory-domain-services-section-tool-for-active-directory-administrators/)
* [AdRestore v1.1](https://docs.microsoft.com/en-us/sysinternals/downloads/adrestore)
* [Active Directory Migration Tool version 3.2](https://www.microsoft.com/en-us/download/details.aspx?id=56570)
* [Active Directory migration tool: A comprehensive guide](http://techgenix.com/active-directory-migration-tool/)

## AD DS - Websites
* [Active Directory Security](https://adsecurity.org/)
