# SOHO
VLAN-Based Inter-VLAN Routing Project (SOHO Project)

This project is a hands-on lab simulation built in Cisco Packet Tracer to practice VLAN segmentation, Inter-VLAN routing (Router-on-a-Stick), and DHCP configuration across different departments in a small office/home office (SOHO) environment.

# Network Topology
![image](https://github.com/user-attachments/assets/d59bb3de-f747-4cb8-a834-13f9316a3543)


# What Was Done in the Switch Configuration
![image](https://github.com/user-attachments/assets/a081cf16-0dfc-4bf7-b40c-ff24fee1b8aa)
1.	Assigned VLANs to Specific Ports:
o	Ports Fa0/2 to Fa0/4 → Assigned to VLAN 10 (IT Department)
o	Ports Fa0/5 to Fa0/7 → Assigned to VLAN 20 (Finance Department)
o	Ports Fa0/8 to Fa0/10 → Assigned to VLAN 30 (Human Resources Department)
2.	Set Each Port to Access Mode:
o	Used switchport mode access to ensure the ports only connect to end devices (PCs, printers, access points), not other switches (which would require trunking).

# What Was Done in the Router Configuration
![image](https://github.com/user-attachments/assets/e1b2fa65-d368-4567-9420-d677137d8616)
1.	Created a Basic Inter-VLAN Routing Setup (Router-on-a-Stick)
You used Router0 to enable communication between two VLANs:
o	VLAN 10 for the IT Department (192.168.1.0/26)
o	VLAN 20 for the Finance Department (192.168.1.64/26)
o	VLAN 30 for the Human Resources Department (192.168.1.128/26)
2.	Configured Sub-Interfaces on Router0:
o	GigabitEthernet0/0.10 with IP 192.168.1.1 for VLAN 10
o	GigabitEthernet0/0.20 with IP 192.168.1.65 for VLAN 20
o	GigabitEthernet0/0.30 with IP 192.168.1.129 for VLAN 30
3.	Used encapsulation dot1Q for VLAN tagging.
This ensures each sub-interface handles traffic for a specific VLAN.
4.	Verified Config and Saved It:
o	Used do wr (write) to save the configuration
o	Used do show start to confirm the startup config

# DHCP Server Setup (on Router)
![image](https://github.com/user-attachments/assets/158545d7-1c46-42f5-a854-afa36619070c)
•	Configured three separate DHCP pools:
o	IT-Pool: 192.168.1.0/26, default gateway 192.168.1.1
o	Finance-Pool: 192.168.1.64/26, default gateway 192.168.1.65
o	Resource-Pool: 192.168.1.128/26, default gateway 192.168.1.129
•	Each pool included:
o	DNS server (same as gateway)
o	Custom domain name (e.g., IT.com, Finance.com, Resource.com)
o All devices were given an IP address using DHCP

# Configured Access Points with SSID and Password
![image](https://github.com/user-attachments/assets/90606b59-9d05-41d6-b837-c66ad35935f8)
![image](https://github.com/user-attachments/assets/737953de-ae35-424a-83d9-02fa87ce1c38)
![image](https://github.com/user-attachments/assets/ae803814-8185-4cb1-98d9-5cbc98cd64ae)

# Pings to confirm connectivity
Ping from IT department PC to PC in the Human Resource Department
![image](https://github.com/user-attachments/assets/35f7afcd-f494-4313-9e18-cddfe3e82b59)

Ping from smartphone in the Finance Department to PC in the Human Resource Department
![image](https://github.com/user-attachments/assets/31540a9e-bc52-4e33-9055-b7688cafa8d6)






