* [Hyper-V 2016 Host Mode: GUI vs Core](https://www.altaro.com/hyper-v/hyper-v-2016-host-mode-gui-core/)
* [Are there any good tools to monitor Hyper-V performance?](https://www.reddit.com/r/sysadmin/comments/89y916/are_there_any_good_tools_to_monitor_hyperv/)
* [Yes, Your Hyper-V Host Should be Domain-Joined](https://www.altaro.com/hyper-v/domain-joined-hyper-v-host/)
* [Time Configuration in Active Directory](https://blogs.technet.microsoft.com/nepapfe/2013/03/01/its-simple-time-configuration-in-active-directory/


https://www.youtube.com/watch?v=XawQrbRzow0

https://kristopherjturner.com/2016/02/29/hyper-v-and-nat-virtual-switch-in-windows-10/

https://www.red-gate.com/simple-talk/sysadmin/powershell/hyper-v-and-powershell-shielded-virtual-machines/

https://www.youtube.com/watch?v=Suyt8aIFFp4

https://www.altaro.com/hyper-v/the-hyper-v-virtual-switch-explained-part-1/

https://www.reddit.com/r/sysadmin/comments/851vlg/what_hypervisors_are_you_linux_shops_running/

https://www.reddit.com/r/sysadmin/comments/8ll151/the_confusion_of_hyperv_virtual_processors/




Hyper-V doesn’t sync time across domain
cmd, "w32tm /query /status" to see which NTP server it uses.
What you need to do on the hosts:
Turn off Hyper-V's time integration on all of your domain joined guests.
If the host is a domain member, sync from your domain: w32tm /config /syncfromflags:domhier /update
If the host is not a domain member, sync from a reputable time server: w32tm /config /manualpeerlist:"pool.ntp.org" /syncfromflags:manual /update
What you need to do on the guests:
If the guest is a regular domain member or domain controller, set the config of the time to sync from the PDC-E machine: w32tm /config /syncfromflags:domhier /update
What you need to do on your PDC-Emulator FSMO role holder:
Sync the machine from a reputable time server, ie: w32tm /config /manualpeerlist:"pool.ntp.org" /syncfromflags:manual /update







# How to clone Windows VM's in Hyper-V
1. Install, Patch and Update your VM so it meets your requirments.
2. Then run sysprep
> Export-VM -Name VM1 -Path D:\Export

> Import-VM -Path 'D:\Export\8A148B6D-C673-423E-9FCC-4FBED182C54D.XML' -Copy -GenerateNewId`
