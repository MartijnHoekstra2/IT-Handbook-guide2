## Group Policies (GP)

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