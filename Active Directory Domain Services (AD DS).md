## Active Directory Domain Services (AD DS)
   - [Active Directory Domain Services](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/active-directory-domain-services)
      - [Domain naming explained](https://docs.google.com/document/d/1QTrEi7ZSpEi4CYMOcE79W1x3F4pAlGE5o19yfCiW1Mg)
**Implementation DNS server addresses**

|                      | Domain Controller 1 | Domain Controller 2 | Domain Controller 3 |
|----------------------|---------------------|---------------------|---------------------|
| Preferred DNS server | Domain Controller 2 | Domain Controller 1 | Domain Controller 1 |
| Alternate DNS server | Domain Controller 3 | Domain Controller 3 | Domain Controller 2 |
| Tertiary             |       127.0.01      |       127.0.01      |       127.0.01      |

[Active Directory Security Groups](https://docs.microsoft.com/en-us/windows/security/identity-protection/access-control/active-directory-security-groups)
[Best Practices for Securing Active Directory](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/best-practices-for-securing-active-directory)

    
   #### AD DS - Tools 
   - [Repadmin](http://techgenix.com/repadmin-tool/)
   - [User Profile migrate](https://www.forensit.com/domain-migration.html)

   #### AD DS - Websites
   - [Active Directory Security](https://adsecurity.org/)
