# SOHO
VLAN-Based Inter-VLAN Routing Project (SOHO Project)

This project is a hands-on lab simulation built in Cisco Packet Tracer to practice VLAN segmentation, Inter-VLAN routing (Router-on-a-Stick), and DHCP configuration across different departments in a small office/home office (SOHO) environment.

# Network Topology
![image](https://github.com/user-attachments/assets/d59bb3de-f747-4cb8-a834-13f9316a3543)


# What Was Done in the Switch Configuration
![image](https://github.com/user-attachments/assets/c41b5000-3231-4318-af9e-a11aedd04aaf)
1.	Assigned VLANs to Specific Ports:
o	Ports Fa0/2 to Fa0/4 → Assigned to VLAN 10 (IT Department)
o	Ports Fa0/5 to Fa0/7 → Assigned to VLAN 20 (Finance Department)
o	Ports Fa0/8 to Fa0/10 → Assigned to VLAN 30 (Human Resources Department)
2.	Set Each Port to Access Mode:
o	Used switchport mode access to ensure the ports only connect to end devices (PCs, printers, access points), not other switches (which would require trunking).

# What Was Done in the Router Configuration
![image](https://github.com/user-attachments/assets/22cc5497-f096-4650-a2dc-3a9cbc031480)
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
