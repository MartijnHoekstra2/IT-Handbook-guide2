* [Server 2016 RDS farm - printing](https://www.reddit.com/r/sysadmin/comments/8ddz4f/server_2016_rds_farm_printing/)

* Use a print server where all printers are installed and you have control over all printer drivers
* Use AD groups and GPP to give the users the printers they need and set them up as default printers
* Use DHCP reservation (with the MAC address) instead of static
* Use the print server for the print spooler (performance) and not on the clients


https://www.reddit.com/r/sysadmin/comments/8s1qmb/is_it_worth_it_to_move_to_a_print_server/




If you need your users to be able to add their own print drivers you will have to use GPO to edit the Driver Installation policy. It is located here:

Computer Configuration\Policies\Administrative Templates\System\Driver Installation

The setting is called "Allow non-administrators to install drivers for these devices setup classes". You will need to add the device class GUID of printers. The GUIDs can be found here: http://msdn.microsoft.com/en-us/library/ff553426(v=vs.85).aspx

from https://social.technet.microsoft.com/Forums/windows/en-US/df21d2c2-c2d4-4107-bfe3-bf8c5a1cd946/install-printer-without-being-administrator?forum=w7itprosecurity


If you have a spare couple bucks, PaperCut NG is pretty useful. Especially for how cheap it is.

Install it on the print server and it'll give you management and analytics and even job control if you choose to use it for that. Decent product.

Papercut has completely solved our company’s printing issues. 150 printers over 50 sites used to mean print jobs going not just to the wrong printer but the wrong town, as people could have so many to choose from. We now publish a single print queue and have follow me printing set up, which was extremely simple to set up and the users love. There aren’t many bits of software I’ll sing the praises of, but Papercut is definitely one of them.
