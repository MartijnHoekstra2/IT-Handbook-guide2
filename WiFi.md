## WiFI
* Always use as few SSIDs as possible, as they consume quite a bit of airtime(overhead)
* Block all outbound ports except common ones: 21, 22, 23, proxy 53 to dns filter, proxy 80, 443
* Don't forget to deny inter-user bridging (Aruba-speak for stopping devices talking to other devices on the vlan)
* Guests gets full access to the internet but primary network has full priority
* Guests recieves a temporary ticket for using WiFI which expierces in X hours / days / weeks
* Individual guest clients may even be isolated from each other
* Isolated from the primary network
* Seperate SSID and VLAN (Guest WiFI / Coperated WiFi)
* Traffic shaping, QoS, and blocking outbound tcp/25 are appropriate measures for the guest uplink
* Web filtering and preventing most "bad" wesbites