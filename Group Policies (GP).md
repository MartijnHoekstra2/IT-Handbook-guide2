## Group Policies (GP)
https://social.technet.microsoft.com/Forums/lync/en-US/1a01d2db-7f90-4cfd-b1f0-9fb7377a69c4/windows-7-using-rdp-to-server-2016-login-failed?forum=w7itprosecurity



#### Intreseting GPO's
  - [Removing wireless profiles through GPO?](https://www.reddit.com/r/sysadmin/comments/8watf6/removing_wireless_profiles_through_gpo/)
  - [Startup Script to add wireless profile to devices via GPO](https://www.reddit.com/r/sysadmin/comments/8waekk/startup_script_to_add_wireless_profile_to_devices/)
  - [What are your must-have quality of life group policies?](https://www.reddit.com/r/sysadmin/comments/8zam8f/what_are_your_musthave_quality_of_life_group/)
  - [Configuring Audit Policies](https://technet.microsoft.com/en-us/library/dd277403.aspx)
  - [Add the Administrator security group to roaming users profiles](http://www.grouppolicy.biz/2010/02/group-policy-setting-of-the-week-15-add-the-administrator-security-group-to-roaming-users-profiles/)
  - [Adding Domain Users To The Local Administrators Group Using Group Policy](https://richardstk.com/2013/11/26/adding-domain-users-to-the-local-administrators-group-using-group-policy/)
  - [Group Policies: Enabling WinRM for Windows Client Operating Systems (Windows 10, Windows 8, Windows 7)](https://sid-500.com/2018/08/16/enabling-winrm-for-windows-client-operating-systems-windows-10-windows-8-windows-7/)
  - [How to Monitor User Logоns in a Domain](https://www.netwrix.com/how_to_monitor_user_logons_in_domain.html?rid=gDd88kwH)
  - [Using Group Policy to configure Desktop Wallpaper (“Background”)](http://www.grouppolicy.biz/2011/03/best-practice-using-group-policy-to-configure-desktop-wallpaper-background/)

#### Group Policy - Tools 
  - [How to restore the Default Domain Policy and Default Domain Controller GPO settings](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/dcgpofix)
  - [How to see which Group Policies are Applied to Your PC and User Account](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/gpresult)
  - [Microsoft Security Compliance Toolkit 1.0](https://www.microsoft.com/en-us/download/details.aspx?id=55319)
  - How to export all group policies to HTML

    Get-GPO -all | % { Get-GPOReport -GUID $_.id -ReportType HTML -Path "C:\GPOExport\$($_.displayName).html" }
  - 
  
#### Group Policy - Websites
  - [Group Policy Administrative Templates Catalog](https://getadmx.com/)
  - [Group Policy Search](https://gpsearch.azurewebsites.net/)
  - [Who broke my user GPOs](https://blogs.technet.microsoft.com/askpfeplat/2016/07/05/who-broke-my-user-gpos/)


## Computer Configuration
  - Policies
    - Administrative Templates
      - Control Panel/Personalization
          - Do not display the lock screen
      - Network/DNS Client
          - Turn off multicast name resolution
      - System/Display Highly Detaioled Status Messages
          - Enable it to see more information while logging in
      - System/Logon
          - Always wait for the network at computer startup and logon
      -  System/Power Management/Video and Display Settings
          - Turn off the display (plugged in)
      -  System / Server Manager
          - Do not display Server Manager automatically at logon
       - Windows Components/Cloud Content
          - Do not show Windows tips
          - Turn off Microsoft consumer experiences
       - Windows Components/Credential User Interface
          - Do not display the password reveal button
       - Windows Components/Data Collection and Preview Builds
          - Allow Telemetry
          - Disable pre-release features or settings
          - Do not show feedback notifications
          - Toggle user control over Insider builds
       - Windows Components/File Explorer
          - Turn off caching of thumbnail pictures
          - Turn off the caching of thumbnails in hidden thumbbs.db files
          - Turn off the display of thumbnails and only display icons
          - Turn off the display of thumbnails and only display icons on network folders 
       - Windows Components/OneDrive
          - Prevent the usage of OneDrive for file storage
       - Windows Components/Search
          - Allow Cortana
          - Do not allow web search
          - Don't search the web or display web results in Search
       - Windows Components/Store
          - Turn off the Store application
       - Windows Components/Windows Update
          - Remove access to use all Windows Update features
          - Turn off auto-restart for updates during active hours


## User Configuration
  - Preferences
    - Control Panel Settings
      - Folder Options
        - Folder Options (At least Windows Vista)
          - Show hidden files and folders
          - Hide extensions for know file types > Uncheck
