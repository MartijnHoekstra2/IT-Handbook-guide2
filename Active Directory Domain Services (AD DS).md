## Active Directory Domain Services (AD DS)
* [Active Directory Domain Services](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/active-directory-domain-services)
* Information regardig Domain Naming:<br />
    1. Use a valid TLD (Top Level Domain, also known as routable domain) registered to your company. Some examples of this are company.ca or company.com
    1. Use a subdomain of a valid TLD that is registered to your company. Some examples include corp.company.ca, ad.company.ca, etc.
    3. Use non-TLD name (or non-routable domain). For example, you may want to use domain.local, domain.int, or domain.corp


* Information regarding DNS Settings:<br />
[DNS servers on adapter name should include the loopback address, but not as the first entry](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff807362(v=ws.10))<br />
[DNS client and server best practices for AD](https://blogs.technet.microsoft.com/askds/2010/07/17/friday-mail-sack-saturday-edition/#dnsbest) <br />
Below an example of an implementation of DNS server addresses<br /> 

|                      | Domain Controller 1 | Domain Controller 2 | Domain Controller 3 |
|----------------------|---------------------|---------------------|---------------------|
| Preferred DNS server | Domain Controller 2 | Domain Controller 1 | Domain Controller 1 |
| Alternate DNS server | Domain Controller 3 | Domain Controller 3 | Domain Controller 2 |
| Tertiary             |       127.0.01      |       127.0.01      |       127.0.01      |
<br />
<br />

* [Active Directory Security Groups](https://docs.microsoft.com/en-us/windows/security/identity-protection/access-control/active-directory-security-groups)</br>
* [Best Practices for Securing Active Directory](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/best-practices-for-securing-active-directory)</br>

    
#### AD DS - Tools 
   - [Repadmin](http://techgenix.com/repadmin-tool/)
   - [User Profile migrate](https://www.forensit.com/domain-migration.html)

#### AD DS - Websites
   - [Active Directory Security](https://adsecurity.org/)
