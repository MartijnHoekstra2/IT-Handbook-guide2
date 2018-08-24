https://www.reddit.com/r/sysadmin/comments/99oea2/vlandhcp_best_practices/

1. Start with working out a diagram to get a better overvieuw of your network
1. Make a baseline / plan
1. SNMP
  1. Use SNMP v3
  1. Look at MIB (Management Information Base) and OIDs (Object Identifiers)
      1. Firewalls
      1. Switches
  1. NetFlow, slow, jflow,cflow,appflow,rflow,Netstram
1. Caution when using PING
1. Bandwith latency
1. Monitoring tempature Fans
1. CPU / Memory
1. Configuration Management, to notify changes on a Firewall / Switch
1. Login notification
1. SNMP Windows Feature to enable
  1. Go to Services and open SNMP Service and fill Contactperson / Location
1. SQL > Transactions Logs
1. SQL > IO
1. SQL > Queries, which are taking long
1. Monitor Apache / IIS
  1. CPU / Memory / Response Time
  1. App pool 
1. SSL Validation / Expire
1. Hyper-V / VMware 
  1. CPU / Memory / Fans / Voltage / Hard Drives
1. Applications / Backup 
1. SNMP Tester
1. MIB Importer

## Switch 
* Disable Telnet
* Disable unused ports
* Enable DHCP snopping
* Set a MOTD banner with a legal note




* [Reddit Network learn list](https://www.reddit.com/r/ITCareerQuestions/comments/8w6rhv/im_sure_this_question_has_come_up_looking_to_get/e1t601u/?context=3)

* [Any small businesses out there that have a true DMZ with 2 firewalls?](https://www.reddit.com/r/sysadmin/comments/8lusyt/any_small_businesses_out_there_that_have_a_true/)
* [Explain like I am 5 What is subnetting?](https://www.reddit.com/r/sysadmin/comments/83nsva/explain_like_i_am_5_what_is_subnetting/)
* [Extending the LAN to a new building](https://www.reddit.com/r/sysadmin/comments/8lt994/extending_the_lan_to_a_new_building/)
* [How to Calculate TCP throughput for long distance WAN links](http://bradhedlund.com/2008/12/19/how-to-calculate-tcp-throughput-for-long-distance-links/)
* [IP Calculator](http://jodies.de/ipcalc?host=10.0.10.1&mask1=24&mask2=255.255.0.0)
* [IP Subnet Calculator](http://www.calculator.net/ip-subnet-calculator.html?cclass=a&csubnet=16&cip=172.16.0.1&ctype=ipv4&printit=0&x=104&y=31)
* [Real-World Network Architecture](https://www.reddit.com/r/sysadmin/comments/8lqr2t/realworld_network_architecture/)
* [Subnet Mask Cheat Sheet](https://www.aelius.com/njh/subnet_sheet.html)
* [Understanding and performing IPv4 subnetting](https://dougvitale.wordpress.com/2013/03/05/understanding-and-performing-ipv4-subnetting/)
* [Should I block ICMP?](http://shouldiblockicmp.com/)
* [What are some important things that are overlooked when initially configuring networking devices (switches for example) .. which can open up problems and cause risk to your networking environment?](https://www.reddit.com/r/sysadmin/comments/8mwzdn/what_are_some_important_things_that_are/)
* [Measure bandwidth usage between switches?](https://www.reddit.com/r/sysadmin/comments/8d2rjg/measure_bandwidth_usage_between_switches/)
* [Do you separate departments in to different VLANs?](https://www.reddit.com/r/sysadmin/comments/8oh40d/do_you_separate_departments_in_to_different_vlans/)
* [Learn Subnetting in just 7 minutes. How to subnet easy](https://www.youtube.com/watch?v=YiV_Vz7Wb-I)
* [CIDR Conversion Table](https://kb.wisc.edu/ns/page.php?id=3493)

* [Full Series | 200-125 CCNA v3.0 | Free Cisco Video Training 2018 | Networking Inc.](https://www.youtube.com/playlist?list=PLh94XVT4dq02frQRRZBHzvj2hwuhzSByN)

* [RADIUS / NPS / 802.11x Enterprise OH MY!!!](https://www.reddit.com/r/sysadmin/comments/8xq9q0/radius_nps_80211x_enterprise_oh_my/)

* [PacketBOMB](http://packetbomb.com/)
* [GNS3](https://www.gns3.com/)
* [How to study for CCNA FREE](https://learningnetwork.cisco.com/thread/15662)

- [Subnetting Made Easy by Cisco Networking Academy Student Brian Morgan](https://www.youtube.com/watch?v=KDig0lOO95M)

## Firewall
- Check Firmware and Software version of the Firewall and if newer version upgrade
- Change default login/password
- Configure logging and send this to a central location
- Configure Lockout Policy
- Configure Session Timeout
- Configure a NTP
- Configure if possible Geo IP prevents unauthorized access from countries
- Deny all traffic by default and only open that what is necassery
- Place the most specific firewall rules on top so when traffic is matched its at the top
- Monitor CPU / Memory / Fans, do this before and after adding new rules
- Disable all unused services that aren't necassery and or in use
- Document: Change Management
  - When is the change made
  - What is changed
  - Who made the change
  - Firmware / Software version
  - MIB and OID packet/version
  
  
https://www.cisco.com/c/en/us/about/security-center/firewall-best-practices.html

- Firmware
- Don't use PTPP, but use LTP or DirectAccess
- WAN interfaces Block > SNMP, TELNET, ISMP




Firewall, network, VPN, wireless
AD
Endpoints
E-mail / Office365




https://www.reddit.com/r/sysadmin/comments/99d9qg/request_for_security_insight_web_servers_dmz_and/

