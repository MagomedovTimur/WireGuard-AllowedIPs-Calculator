### WireGuard AllowedIPs Calculator is a script that simplifies the creation of an AllowedIPs string for wireguard configuration
AllowedIPs is created by subtracting disallowed networks from allowed networks and generating a complex string

Usage examples: 
	
	wireguard-ip-calculator.py -a 0.0.0.0/0 -d 192.168.0.0/16
	Allow all networks exclude 192.168.0.0/16

	wireguard-ip-calculator.py -d 192.168.0.0/16
	Allow all networks exclude 192.168.0.0/16
 
	wireguard-ip-calculator.py -d 100.100.100.0/24 -e
	Allow all networks exclude 100.100.100.0/24 and local networks

	wireguard-ip-calculator.py -a 0.0.0.0/0 -e
	Allow all networks exclude local netowrks

	wireguard-ip-calculator.py -e
	Allow all networks exclude local netowrks

Keys: 

	-a <network/mask[,network2/mask][,network3/mask],...>: Allowed networks. Leave blank for 0.0.0.0/0
	-d <network/mask[,network2/mask][,network3/mask],...>: Disallowed networks. Optional if "-e" is used
	-r <Wiregurad allowedNets string>: Reverse wiregurad config string to allowed and disallowed networks
	-e: Preset for fast excluding local networks
	-h: print help message to console

Required libraries: 

	ipaddress, netaddr, sys
