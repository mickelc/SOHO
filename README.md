SOHO Network Simulation – VLAN & Inter-VLAN Routing
This project is a Cisco Packet Tracer lab that simulates a small office/home office (SOHO) network. It focuses on VLAN segmentation, Inter-VLAN routing (Router-on-a-Stick), DHCP configuration, and wireless access setup across multiple departments.

Network Topology


Departments and VLANs
Department	VLAN	IP Range
IT	10	192.168.1.0/26
Finance	20	192.168.1.64/26
Human Resources	30	192.168.1.128/26

Key Configurations
Switch Setup
Assigned access ports to VLANs

Used switchport mode access to prevent trunking on user ports

Router-on-a-Stick
Configured sub-interfaces on Router0 using dot1Q encapsulation

Assigned gateways for each VLAN

Enabled Inter-VLAN routing

DHCP
Created 3 DHCP pools (IT, Finance, HR) with appropriate IP ranges

Assigned default gateway, DNS, and domain for each

Wireless
Configured Access Points with SSIDs and passwords

Smartphones connected wirelessly and received IPs via DHCP

Connectivity Tests
Ping from IT PC to HR PC

Ping from Finance smartphone to HR PC

Ping from HR laptop to Finance printer

Screenshots of these successful pings are included in the Full Documentation.

Skills Practiced
VLAN creation and port assignment

Sub-interface routing (Router-on-a-Stick)

DHCP setup across VLANs

Wireless configuration

Network troubleshooting and testing
