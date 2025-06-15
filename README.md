# SOHO Network Simulation – VLAN & Inter-VLAN Routing
This project is a hands-on Cisco Packet Tracer lab designed to simulate a small office/home office (SOHO) network. It demonstrates VLAN segmentation, Inter-VLAN routing using Router-on-a-Stick, and DHCP configuration to enable communication and automation across different departments.

# Network Topology
![image](https://github.com/user-attachments/assets/d59bb3de-f747-4cb8-a834-13f9316a3543)
The network consists of three departments:
IT (VLAN 10)
Finance (VLAN 20)
Human Resources (VLAN 30)
Each department has a combination of PCs, wireless devices, and printers.

# Switch Configuration
![image](https://github.com/user-attachments/assets/a081cf16-0dfc-4bf7-b40c-ff24fee1b8aa)
Assigned VLANs to Specific Ports:
Fa0/2 to Fa0/4 → VLAN 10 (IT)
Fa0/5 to Fa0/7 → VLAN 20 (Finance)
Fa0/8 to Fa0/10 → VLAN 30 (HR)

Configured Access Mode on Ports:
Used switchport mode access to ensure only end devices (not switches) are connected.

# Router Configuration
![image](https://github.com/user-attachments/assets/e1b2fa65-d368-4567-9420-d677137d8616)
Enabled Inter-VLAN Routing on Router0 for:
VLAN 10 (192.168.1.0/26)
VLAN 20 (192.168.1.64/26)
VLAN 30 (192.168.1.128/26)

Configured Sub-Interfaces:
G0/0.10 → 192.168.1.1 (VLAN 10)
G0/0.20 → 192.168.1.65 (VLAN 20)
G0/0.30 → 192.168.1.129 (VLAN 30)

Encapsulation:
Used encapsulation dot1Q for VLAN tagging.

Saved and Verified Configuration:
do wr to save
do show start to confirm startup config

# DHCP Configuration (on Router)
![image](https://github.com/user-attachments/assets/158545d7-1c46-42f5-a854-afa36619070c)
Three separate DHCP pools were created:
IT-Pool: 192.168.1.0/26 → Gateway: 192.168.1.1
Finance-Pool: 192.168.1.64/26 → Gateway: 192.168.1.65
HR-Pool: 192.168.1.128/26 → Gateway: 192.168.1.129

Each pool provided:
Default gateway
DNS server (same as gateway)
Custom domain name (e.g., IT.com)

All end devices successfully received IPs via DHCP.

# Wireless Access Configuration
![image](https://github.com/user-attachments/assets/90606b59-9d05-41d6-b837-c66ad35935f8)
![image](https://github.com/user-attachments/assets/737953de-ae35-424a-83d9-02fa87ce1c38)
![image](https://github.com/user-attachments/assets/ae803814-8185-4cb1-98d9-5cbc98cd64ae)

# Connectivity Tests
Ping from IT department PC to PC in the Human Resource Department
![image](https://github.com/user-attachments/assets/35f7afcd-f494-4313-9e18-cddfe3e82b59)

Ping from smartphone in the Finance Department to PC in the Human Resource Department
![image](https://github.com/user-attachments/assets/31540a9e-bc52-4e33-9055-b7688cafa8d6)

Ping from laptop in the Human Resource Department to printer in Finance Department
![image](https://github.com/user-attachments/assets/ac0b0e4f-89f7-4bf6-a8c5-f50659ee891c)

# Takeaways
Through this project, I strengthened my understanding of:
VLAN segmentation and network isolation
Sub-interface routing using a single router port (Router-on-a-Stick)
DHCP automation across multiple VLANs
Wireless integration into VLAN-based networks
Troubleshooting and verifying Layer 2 & 3 connectivity



