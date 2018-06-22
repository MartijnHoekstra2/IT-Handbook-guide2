## Windows Server Update Services (WSUS)
 
 #### How to identify and decline superseded updates in WSUS
1. Open the Windows Update Services MMC then select the All Updates View as you can see below.
1. Set the display to show the Approval status of ‘Any except Declined’ with a Status of ‘Any’, then  Click Refresh.
1. Right click in the title bar and  Enable the ‘Supersedence’ column to make it visible.
* No icon: update doesn’t supersede another one nor is it superseded by an update.
* Blue square on top: this update supersedes another update, these updates you do not want to clean!
* Blue square in the middle: this update has been superseded by another update, and superseded another update as well, this is an example of an update you may want to clean (decline).
* Blue square in the right below corner: this update has been superseded by another update, this is an example of an update you may want to clean (decline)
 
 Note: Always verify that all superseding updates are approved before doing this operation!
 
 
 
 
 - [Windows Server Update Services (WSUS) & Windows Updates (WU) explained](https://docs.google.com/document/d/1JRByXOwB0qKXjh2qwyq-ob33PsbK9o3wrIe7l60WoTU)
<br />
