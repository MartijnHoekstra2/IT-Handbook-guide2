## Windows Server Update Services (WSUS)
- [Windows Server Update Services (WSUS)](https://docs.microsoft.com/en-us/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [WSUS - select devices in OU with GPO](https://www.reddit.com/r/sysadmin/comments/8uhjr2/wsus_select_devices_in_ou_with_gpo/)
- [Security Update Guide](https://portal.msrc.microsoft.com/en-us/security-guidance)
- [Microsoft®Update Catalog](https://www.catalog.update.microsoft.com/Home.aspx)
- [Fixing IIS worker WSUSpool issue](http://www.systemsitpro.com/2017/03/fixing-up-iis-worker-wsuspool-issue.html)

#### WSUS WID or SQL?
Windows Internal Database ships with the Windows operating system, and there are no additional license costs associated with it. Most organizations opt to use the Windows Internal Database to help reduce licensing costs, but it is important to note that WID will not work when installing WSUS Server in a load balancing/high availability scenario. As a result, you must choose the SQL Server database option when installing WSUS Server in a load balancing/high availability scenario. For more information: [Choose a WSUS storage strategy](https://docs.microsoft.com/en-us/windows-server/administration/windows-server-update-services/plan/plan-your-wsus-deployment#wsus-database)

#### How to identify and decline superseded updates in WSUS
1. Open the Windows Update Services MMC then select the All Updates View.
1. Set the display to show the Approval status of ‘Any except Declined’ with a Status of ‘Any’, then  Click Refresh.
1. Right click in the title bar and Enable the ‘Supersedence’ column to make it visible.
- No icon: update doesn’t supersede another one nor is it superseded by an update.
- Blue square on top: this update supersedes another update, these updates you do not want to clean!
- Blue square in the middle: this update has been superseded by another update, and superseded another update as well, this is an example of an update you may want to clean (decline).
- Blue square in the right below corner: this update has been superseded by another update, this is an example of an update you may want to clean (decline)
 
 Note: Always verify that all superseding updates are approved before doing this operation!
 
#### Gotcha's
- [Demystifying “Dual Scan”](https://blogs.technet.microsoft.com/wsus/2017/05/05/demystifying-dual-scan/)
- [Fixing WSUS - When the Best Defense is a Good Offense](https://deploymentresearch.com/Research/Post/665/Fixing-WSUS-When-the-Best-Defense-is-a-Good-Offense)
- [What are the correct WSUS GPO settings so that Windows 10 clients will never see updates unless I specifically approve them in WSUS?](https://www.reddit.com/r/sysadmin/comments/8vst6u/what_are_the_correct_wsus_gpo_settings_so_that/)
