## Active Directory Domain Services (AD DS)
* [Active Directory Domain Services](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/active-directory-domain-services)
* [Domain naming explained](https://docs.google.com/document/d/1QTrEi7ZSpEi4CYMOcE79W1x3F4pAlGE5o19yfCiW1Mg)
 
* Example: Implementation of DNS server addresses

|                      | Domain Controller 1 | Domain Controller 2 | Domain Controller 3 |
|----------------------|---------------------|---------------------|---------------------|
| Preferred DNS server | Domain Controller 2 | Domain Controller 1 | Domain Controller 1 |
| Alternate DNS server | Domain Controller 3 | Domain Controller 3 | Domain Controller 2 |
| Tertiary             |       127.0.01      |       127.0.01      |       127.0.01      |


1. [DNS servers on adapter name should include the loopback address, but not as the first entry](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff807362(v=ws.10) )
 
1. [DNS client and server best practices for AD](https://blogs.technet.microsoft.com/askds/2010/07/17/friday-mail-sack-saturday-edition/#dnsbest)


[Active Directory Security Groups](https://docs.microsoft.com/en-us/windows/security/identity-protection/access-control/active-directory-security-groups)</br>
[Best Practices for Securing Active Directory](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/best-practices-for-securing-active-directory)</br>

    
   #### AD DS - Tools 
   - [Repadmin](http://techgenix.com/repadmin-tool/)
   - [User Profile migrate](https://www.forensit.com/domain-migration.html)

   #### AD DS - Websites
   - [Active Directory Security](https://adsecurity.org/)
