## Group Policy overview

#### Group Policy - Tools 
  - [How to restore the Default Domain Policy and Default Domain Controller GPO settings](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/dcgpofix)
  - [How to See Which Group Policies are Applied to Your PC and User Account](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/gpresult)
  
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
