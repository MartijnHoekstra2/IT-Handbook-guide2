* [Cooking up the RetroPie](https://channel9.msdn.com/coding4fun/blog/Cooking-up-the-RetroPie)

https://www.reddit.com/r/sysadmin/comments/82xe4e/raspberry_pi3_as_a_wifi_access_point_and_openvpn/

https://www.reddit.com/r/sysadmin/comments/8ph1gx/what_to_run_on_pi_raspberry/

https://winterminal.com/

https://raspberrypi.stackexchange.com/questions/10251/prepare-sd-card-for-wifi-on-headless-pi

https://kubernetes.io/


Name	Website	Info
 - PI-Hole	https://pi-hole.net/	Network-wide ad blocking via your own Linux hardware
 - Raspberry Pi File Server		Samba
 - Lighttpd		
 - RetroPie	https://retropie.org.uk/	
 - Let's Encrypt https://blog.wirelessmoves.com/2017/01/lets-encrypt-on-a-raspberry-pi-web-server.html	
 - OpenVPN	Building A Raspberry Pi VPN
 - Various Project listed	http://www.modifymypi.com/projects.html
 - Element14 projects	https://www.element14.com/community/community/raspberry-pi/raspberrypi_projects?ICID=menubar_topics_raspiprojects





Raspberry PI

Website
At the specified website below you can choose your download for Raspberry PI.
https://www.raspberrypi.org/downloads/
You can choice for two sort of installations::
NOOBS
NOOBS stands for New Out Of the Box Software, this is the most standard version if you don’t have any experiences with Raspberry PI how to install
Raspbian
Is the official installation for the Raspberry PI

Default login
When you download the core version (without GUI) you can login with the following username and password:
Login: pi
Wachtwoord: Raspberry

Keyboard, time zones and advanced disk options
sudo raspi-config
right alt-gr and with dead keys

Scan WiFi
If you need to find the network name of your local network you can run the following command in the terminal: sudo iwlist wlan0 scan

Configuring WiFI connection
With the GUI you can click on the desired WiFi connection. The configuration file will be automatically created.
With the terminal (no GUI) you can also setup a WiFi connection, you need to do the following steps:
( If you are missing the /etc/wpa_supplicant/wpa_supplicant.conf you can install it if possible with the following command:  sudo apt-get install wpasupplicant )
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
ssid submit the name of your network
psk submit the password of the above specified network if required
proto could be either RSN (WPA2) or WPA (WPA1)
key_mgmt could be either WPA-PSK  (most probably) or WPA-EAP (enterprise networks)
eap could be PEAP, TLS, TTLS, SIM or AKA
pairwise kan zijn CCMP (WPA2) of TKIP (WPA1)
auth_alg is hoogstwaarschijnlijk OPEN, andere opties zijn LEAP en SHARED 
identity your login name to auth
password your password
network={
ssid=”SFT”
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





