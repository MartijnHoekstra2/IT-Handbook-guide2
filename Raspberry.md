## Raspberry
* [RetroPie Cooking up](https://channel9.msdn.com/coding4fun/blog/Cooking-up-the-RetroPie)
* [RetroPie](https://retropie.org.uk/)
* [Raspberry Pi3 as a Wi-Fi access point and OpenVPN client](https://www.reddit.com/r/sysadmin/comments/82xe4e/raspberry_pi3_as_a_wifi_access_point_and_openvpn/)
* [What to run on Pi Raspberry?](https://www.reddit.com/r/sysadmin/comments/8ph1gx/what_to_run_on_pi_raspberry/)
* [WTware for Raspberry thin client operating system](https://winterminal.com/)
* [Prepare SD card for Wifi on Headless Pi](https://raspberrypi.stackexchange.com/questions/10251/prepare-sd-card-for-wifi-on-headless-pi)
* [PI-Hole](https://pi-hole.net/)
* [Samba: Setup a Raspberry PI as a file server for your local network](https://www.raspberrypi.org/magpi/samba-file-server/)
* [How to setup Raspberry Pi Lighttpd](https://pimylifeup.com/raspberry-pi-lighttpd/)
* [Let’s Encrypt On A Raspberry Pi Web Server](https://blog.wirelessmoves.com/2017/01/lets-encrypt-on-a-raspberry-pi-web-server.html)
* [Raspberry Pi VPN Server: Build Your Own Virtual Private Network](https://pimylifeup.com/raspberry-pi-vpn-server/)

#### Other intreseting projects
* [Projects for Your Raspberry Pi Computer](http://www.modifymypi.com/projects.html)
* [Raspberry Pi Projects](https://www.element14.com/community/community/raspberry-pi/raspberrypi_projects?ICID=menubar_topics_raspiprojects)

#### None related info:
- sudo raspi-config
- right alt-gr and with dead keys
- If you need to find the network name of your local network you can run the following command in the terminal: sudo iwlist wlan0 scan

#### WiFi settings for Raspberry
1. With the GUI you can click on the desired WiFi connection. The configuration file will be automatically created.
1. With the terminal (no GUI) you can also setup a WiFi connection, you need to do the following steps:
1. If you are missing the /etc/wpa_supplicant/wpa_supplicant.conf you can install it if possible with the following command:
sudo apt-get install wpasupplicant
1. sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
1. ssid submit the name of your network
1. psk submit the password of the above specified network if required
1. proto could be either RSN (WPA2) or WPA (WPA1)
1. key_mgmt could be either WPA-PSK  (most probably) or WPA-EAP (enterprise networks)
1. eap could be PEAP, TLS, TTLS, SIM or AKA
1. pairwise kan zijn CCMP (WPA2) of TKIP (WPA1)
1. auth_alg is highlikly OPEN, other options are LEAP en SHARED 
1. Identity your login name to auth
1. password your password
network={
ssid=”FILL IN SSID”
proto=RSN
key_mgmt=WPA-EAP
eap=PEAP
pairwise=CCMP
phase2=”auth=MSCHAPV2”
identity=””
password=””
priority=1
}
sudo nano /etc/network/interfaces
allow-hotplug wlan0 if you are using a WiFI extender
wpa-driver wext if you are using a WiFi Extender
wpa-config submit here the location of your configuration file for the WiFi
auto wlan0 automatically connect to wlan0 (could cause an error “Failed to start Raise network interfaces”)
auto lo the loopback network interface
iface lo inet loopback the loopback network interface
wpa-config /etc/wpa_supplicant/wpa_supplicant.conf
sudo reboot
