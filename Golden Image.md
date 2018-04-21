#### Download and edit Windows 10
1. [Download Windows 10](https://www.microsoft.com/en-us/software-download/windows10)
1. [Convert ESD to WIM File on Windows 10](https://docs.google.com/document/d/1EK7zYbx1wvVdE1Enkn4Oh4IYnT917MCO8xFysvKe5ZE)
1. [Removing apps from Windows 10 media](https://community.spiceworks.com/how_to/123554-removing-apps-from-windows-10-media)
1. [Enable or Disable Windows Features Using DISM](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/enable-or-disable-windows-features-using-dism)

#### Download deployment software
1. [Download Windows ADK](https://docs.microsoft.com/en-us/windows-hardware/get-started/adk-install)
1. [Download MDT](https://blogs.technet.microsoft.com/msdeployment)

#### Install deployment software
1. Start the installation of Windows ADK and select only the following components:<br />
    1. Deployment Tools
    1. Windows Preinstallation Environment (Windows PE)
1. Install MDT<br />
1. Start the installation of WDS and select only the following components:<br />
    1. Deployment Server
    1. Transport Server
      
#### Start MDT 
1. Start the **Deployment Workbench**
1. Create a **New Deployment Share**
1. At the **New Deployment Share Wizard** at **Options** unselect all the options

#### Secure the MDT Deployment Share
1. [MDT: Secure the Deployment Share](http://www.ingmarverheij.com/mdt-secure-deployment-share/)

#### Configure DHCP for PXE booting with WDS for BIOS or UEFI
1. [Configure DHCP for PXE booting with WDS for BIOS or UEFI](https://gal.vin/2017/05/05/pxe-booting-for-uefi-bios/)

#### Customize the Deployment Share
1. Import your **Operating System**
    1. Full set of sourc files
1. Test    
