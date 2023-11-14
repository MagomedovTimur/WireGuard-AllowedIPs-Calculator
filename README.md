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

 	wireguard-ip-calculator.py -a 10.10.0.0/16 -d 10.10.20.0/24,10.10.10.100/32
	Allow network 10.10.0.0/16 but disallow network 10.10.20.0/24 and host 10.10.10.100
Keys: 

	-a <network/mask[,network2/mask][,network3/mask],...>: Allowed networks. Leave blank for 0.0.0.0/0
	-d <network/mask[,network2/mask][,network3/mask],...>: Disallowed networks. Optional if "-e" is used
	-e: Preset for fast excluding local networks
	-h: print help message to console

Required libraries: 

	ipaddress, netaddr, sys
