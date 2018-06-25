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
* [Active Directory Security Groups](https://docs.microsoft.com/en-us/windows/security/identity-protection/access-control/active-directory-security-groups)
* [Best Practices for Securing Active Directory](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/best-practices-for-securing-active-directory)


#### AD DS - Tools 
   - [Repadmin](http://techgenix.com/repadmin-tool/)
   - [User Profile migrate](https://www.forensit.com/domain-migration.html)

#### AD DS - Websites
   - [Active Directory Security](https://adsecurity.org/)
