https://www.red-gate.com/simple-talk/sysadmin/data-protection-and-privacy/detecting-data-breaches/

https://www.youtube.com/watch?v=4gR562GW7TI

#### Anti-Spam filter / settings
* Customize your serviceprovider to block incoming message that have one of the following extensions: .exe, .scr, .vbs, .js, .jar, .bat, .pif, or .cpl. 
* Do not rely on the default spam filter settings provided by your serviceprovider. Always make sure you have gone through every possible option to make sure you have the best settings for your organisation.

#### Backup strategy
* Consider having a second NAS to backup first to. Restoring a backup from internet can take a lot of time, be expensive, or both.
* Every so often, be it quarterly or yearly, do an archive of company files. Burn it to CD/DVD/Blu-Ray/M-Disk. In fact, burn three copies. This way, if all goes pointy-end up, the company may hurt, but won't be out of business.
* Implemented [The 3-2-1 Rule](https://www.veeam.com/blog/how-to-follow-the-3-2-1-backup-rule-with-veeam-backup-replication.html).
* Make sure modify/write permissions are set correctly on account that is being used.
* Make weekly, daily or hourly backups. Classify which server or applications needs to have the weekly, daily or hourly.
* Test the backup from time to time.
* Use multi locations.

#### Microsoft Office

###### Group Policy Administrative Template´s
* [2007 Office system (SP2) Administrative Template files (ADM, ADMX, ADML) and Office Customization Tool](http://www.microsoft.com/en-us/download/details.aspx?id=3795)
* [Office 2010 Administrative Template files (ADM, ADMX/ADML) and Office Customization Tool download](http://www.microsoft.com/en-us/download/details.aspx?id=18968)
* [Office 2013 Administrative Template files (ADMX/ADML) and Office Customization Tool](https://www.microsoft.com/en-us/download/details.aspx?id=35554)
* [Office 2016 Administrative Template files (ADMX/ADML) and Office Customization Tool](https://www.microsoft.com/en-us/download/details.aspx?id=49030)

###### Disbale DDE 

###### Disbale Macros
To prevent unwanted macros to excute follow the steps below:
1. Open the __Group Policy Management Editor__, go to __User configuration__.
1. Click __Administrative templates__ > __Microsoft Office 20XX__
1. Depending on your version you have to go 
1. Depending on which version you will have you ne

__Microsoft Word "version" > __Word options__ > __Security__ > __Trust Center__.
1. Open the __Block macros from running in Office files from the Internet__ setting to configure and enable it.


https://cloudblogs.microsoft.com/microsoftsecure/2016/03/22/new-feature-in-office-2016-can-block-macros-and-help-prevent-infection/
https://superuser.com/questions/1073060/disable-all-microsoft-office-macros-globally-for-all-users
http://www.thewindowsclub.com/block-macro-malware-microsoft-office

https://technet.microsoft.com/en-us/library/security/4053440.aspx
https://gist.github.com/wdormann/732bb88d9b5dd5a66c9f1e1498f31a1b
https://www.vertekmti.com/malware-distributed-via-ms-office-dde-feature-no-macros-required/
https://www.ghacks.net/2017/10/23/disable-office-ddeauto-to-mitigate-attacks/
Cyber extortionists have recently started resorting to an old-school contamination trick based on macros in Microsoft Office documents. The strain dubbed Locky is circulating over emails with a Microsoft Word attachment disguised as an invoice. Originally, the contents of this document are gibberish, but a prompt to enable macros promises the user to make the text intelligible. However, doing so will allow the attacker to deposit and execute malicious code remotely through a known macro vulnerability. Therefore, if a document asks you to turn on macros, be sure to opt out of this offer.


#### Patch
* Patch both your operating system and applications
* For deploying patches you could use [Chocolatey](https://chocolatey.org/), [PDQ Deploy](https://www.pdq.com/pdq-deploy/) or [SCCM](https://docs.microsoft.com/en-us/sccm/sum/plan-design/plan-for-software-updates)













#### Network Segmentation
This mitigation methodology pursues the goal of protecting the IT infrastructure of an organization by restricting the scope of resources that a cyber intruder can access. In other words, it presupposes the compartmentalization of data, network assets, and applications into standalone segments while limiting communication between these segments. Consequently, if a ransomware compromise takes place, the infection will not be able to traverse the whole network for data and encrypt it.

#### Audit and IDS
Popular Internet security programs and premium security suites deliver custom firewalls featuring advanced intrusion detection and prevention. These tools normally won’t conflict with the stock firewall built into Windows, so the two can operate concurrently and enhance the efficiency of each other. Their usefulness for thwarting ransomware assaults is out of the question because these threats don’t work autonomously and reach out to their C&Cs multiple times throughout a breach. Because this activity leaves a conspicuous footprint in the target system’s web traffic patterns, the firewall defense is indispensable.

#### Keep Windows Firewall turned on
The native Firewall is rather efficient in tackling ransomware because it monitors inbound and outbound traffic for known malicious and potentially harmful activity. Since ransom Trojans will actively exchange data with their C2 servers, the Firewall can identify this stealthy communication, block it and alert the user.

#### Permissions
Removable media such as thumb drives or portable hard disks can carry ransomware payloads and thus spread the infection from one machine to another. One of the new samples dubbed ZCrypt or Ransom:Win32/ZCryptor.A was found to exhibit self-replication features, just like computer worms. It can, therefore, copy itself to adjacent devices and further propagate this way. When a contagious piece of hardware is connected to a healthy computer, it’s in the user’s best interest to prevent it from opening automatically.

When an adversary targets a system, they will primarily look for user accounts with administrative privileges. Administrators are targeted because they have a high level of access to the organisation’s ICT system. If an adversary gains access to a user account with administrative privileges they can access any data the administrator can access – which generally means everything. Minimising administrative privileges makes it more difficult for the adversary to spread or hide their existence on a system.

Administrative privileges should be tightly controlled. It is important that only staff and contractors that need administrative privileges have them. In these cases, separate accounts with administrative privileges should be created which do not have access to the internet. This reduces the likelihood of malware infecting the administrator as they should not be web browsing or checking emails while using their privileged account.


#### Have a response plan in store
This tip is particularly valuable for organizations. When hit by a ransomware threat, it’s critical for an enterprise to adopt timely countermeasures and mitigations before the payment deadline expires and the ransom goes up. To this end, IT executives should do an inventory of critical data resources, know where these assets are located, and evaluate the damage from the possible unavailability of this data.

#### AV Solution

#### Educate users
The phishing methodology being a widespread ransomware distribution vector, some basic security awareness can save you a lot of hassle. The rule of thumb is to refrain from opening suspicious email attachments and clicking dubious hyperlinks links received via instant messaging clients as well as social networks. Cyber criminals may compromise your contacts’ accounts and send out booby-trapped files or malicious links on their behalf. Therefore, even if you know who the sender is, think twice before quenching your curiosity.

#### Maintain secure backups
Compared to other tactics to thwart ransomware attacks and reduce the damage for end users and enterprise networks, data backups strike a golden mean. If there is an efficient backup strategy in place, all it takes to recover from such a compromise is remove the offending code and then download original copies of the mutilated files from a protected place outside of the targeted machine. The Trojan obliteration part tends to be easy. In fact, some of these infections trigger a self-termination routine after completing data encryption.

It’s recommended to avoid online backup services that map the cloud drive as a drive letter in the computer’s data structure. This approach makes the cloud drive an easy target for crypto ransomware. A good practice is to follow the 3-2-1 backup rule: have at least three copies of the most valuable data, keep two of them on different external media, and store one copy offsite.

#### Software whitelisting
The idea of whitelisting boils down to defining what is allowed to run on a computer rather than blocking suspicious or known malicious processes. Security suites can barely keep track of the huge volumes of new or slightly modified virus variants, so malware signatures are no longer an efficient response to the present-day cyber threat landscape. The tool called Windows AppLocker can automate the app whitelisting routine by allowing users to create a list of processes and applications that are authorized to run on the PC by default.

#### Configure Windows to show file extensions
The perpetrators may disguise ransomware executables as files considered harmless. To this end, they tend to assign several extensions to the loader that make it look like an image, a video or an innocuous document. The filename Flowers.jpg, followed by a bunch of spaces and .exe, would be an example of this trick. Because some email clients display a limited number of characters of attachments’ names, the user will think it’s an image file, open it and get infected. Therefore, configuring the operating system and the preferred webmail client to show the genuine file extensions can help identify malicious payloads.




### AV solution
* Implement an AV solution product
* Ensure that AV is always up to date. This means making sure your central store is always available. Investigate AV products that can update even when not on the domain network (without use of a vpn).


### Local Admin
* Ensure that users do not have unnecessary admin access to local machines OR servers. Giving a user admin rights to anything should be the absolute desperate last-resort in any scenario.

### Desktops
* Ensure that either UAC is forcibly set using GPO OR give admin access using a separate account and use GPO security settings to "Deny Logon Locally" to that account on desktop machines (this should be only be for non-IT staff)

### Microsoft Office
* Use GPO to configure trust settings in office regarding macros and trusted locations

### Software
* Use GPO to configure software restrictions on running from appdata directory

### Trace when infected
* If/when you are infected with an instance of Crypto, do not just wipe the PC and move on. Trace the crypto to its source and remove that too. Crypto infected emails will often be sent to a number of users (or a distribution list), not just one, and reinfections can happen very easily after the initial incident if the infected file/email is not removed from circulation.

### Network Shares
* There is no necessity for users to have "full control" to share drive. This is a hang up from legacy applications (which should be decommissioned if they insist on full control permissions). Use modify permissions in all scenarios (or read-only if necessary). If more is required, use advanced permissions editing to give specific requirements.
* Lock down the root of the share to departments/functions/etc and only give access to the appropriate personnel
* Do not use generic accounts for share access!
* Ensure that there are no other open shares on your network!
* Protecting machines from each other is wise. I have each of my machines backing up to a separate share using a different user. This way, if one gets infected and trashes the share, I can restore the share from a snapshot or backup, and the other machines are not touched.



### Other solutions
* You have Enterprise version of Windows? Use AppLocker. Otherwise, use (Windows Software Restriction Policies)SRPs, since this are just Group Policies. Block all script/program files not located in program files, (x86), or Windows. If a program needs to run from AppData, create specific allows. Basically run an SRP whitelist. 
* Force certain extensions to open in Notepad to prevent from running code. Think of HTA, JAR, JS, JSE and HTA
* Block Macros in Office programs. If for some reason an user still needs to have a macro then create a Trust Locations
* Setup FSRM for the file server itself. You could use https://fsrm.experiant.ca/ as solution to monitor specificied extensions
* Block traffice from certain countries / regions. Be sure that you don't have any business with parties from the specific countries / regions
* Software Restriction Policies blocking most stuff running out of localappdata
* Don't give users localadmin rights
* OpenDNS
* Alerts from file server when a user modifies too many files in a short time
* https://www.asd.gov.au/infosec/mitigationstrategies.htm
* http://resources.infosecinstitute.com/ransomware-mitigation-and-prevention/#gref
* https://www.lepide.com/blog/nine-ways-to-address-ransomware-attacks-in-todays-security-landscape/

### Result No measurments are taken
![Alt text](http://i0.kym-cdn.com/entries/icons/mobile/000/012/073/7686178464_fdc8ea66c7.jpg "Mission Failed")
