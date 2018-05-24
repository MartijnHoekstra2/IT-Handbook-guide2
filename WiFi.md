#### Guest WiFi suggestions
1. Guests gets full access to the internet but primary network has full priority
1. Guests recieves a temporary ticket for using WiFI which expierces in X hours / days / weeks
1. Seperate SSID and VLAN (Guest WiFI / Coperated WiFi)
1. Isolated from the primary network
1. Individual guest clients may even be isolated from each other
1. Always use as few SSIDs as possible, as they consume quite a bit of airtime
1. Traffic shaping, QoS, and blocking outbound tcp/25 are appropriate measures for the guest uplink
1. Web filtering and preventing most "bad" wesbites
1. Block all outbound ports except common ones: 21, 22, 23, proxy 53 to dns filter, proxy 80, 443
1. Don't forget to deny inter-user bridging (Aruba-speak for stopping devices talking to other devices on the vlan)
