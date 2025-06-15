# SOHO Network Simulation – VLAN & Inter-VLAN Routing
This project is a Cisco Packet Tracer lab that simulates a small office/home office (SOHO) network. It focuses on VLAN segmentation, Inter-VLAN routing (Router-on-a-Stick), DHCP configuration, and wireless access setup across multiple departments, all for a fictitious company named after me (because why not?).

---

# Network Topology

![image](https://github.com/user-attachments/assets/4906ded7-d6d6-4c8e-b980-df81b9f966eb)


## The network consists of three departments:
•	IT (VLAN 10)

•	Finance (VLAN 20)

•	Human Resources (VLAN 30)

Each department has a combination of PCs, wireless devices, and printers.

---

#  Switch Configuration

![image](https://github.com/user-attachments/assets/f98eda0e-0cc0-4727-9b64-34407e0c3bfe)

## Assigned VLANs to Specific Ports:

1) Fa0/2 to Fa0/4 → VLAN 10 (IT)

2) Fa0/5 to Fa0/7 → VLAN 20 (Finance)

3) Fa0/8 to Fa0/10 → VLAN 30 (HR)

## Configured Access Mode on Ports:

Used switchport mode access to ensure the ports only connect to end devices (PCs, printers, access points), not other switches (which would require trunking).

---

# Router Configuration (Router-on-a-Stick)

![image](https://github.com/user-attachments/assets/056adf85-3e96-4235-bbbc-d7891ae43d18)

## Enabled Inter-VLAN Routing on Router0 for:

1) VLAN 10 (192.168.1.0/26)

2) VLAN 20 (192.168.1.64/26)

3) VLAN 30 (192.168.1.128/26)

## Configured Sub-Interfaces:

1) G0/0.10 → 192.168.1.1 (VLAN 10)

2) G0/0.20 → 192.168.1.65 (VLAN 20)

3) G0/0.30 → 192.168.1.129 (VLAN 30)

## Encapsulation:

Used encapsulation dot1Q for VLAN tagging.


---

# DHCP Configuration (on Router)

![image](https://github.com/user-attachments/assets/a3bdac26-1157-4bba-bdeb-b03f1b323095)

## Three separate DHCP pools were created:

1) IT-Pool: 192.168.1.0/26 → Gateway: 192.168.1.1

2) Finance-Pool: 192.168.1.64/26 → Gateway: 192.168.1.65

3) HR-Pool: 192.168.1.128/26 → Gateway: 192.168.1.129

## Each pool provided:

1) Default gateway

2) DNS server (same as gateway)

3) Custom domain name (e.g., IT.com)

All end devices successfully received IPs via DHCP.

---

# Wireless Access Configuration

Access Points were configured with custom SSIDs and secured with passwords for each department.

![image](https://github.com/user-attachments/assets/d2455637-eac5-4e54-af81-f1f52c0ebd0f)
![image](https://github.com/user-attachments/assets/d2348778-05e2-4083-b1d1-2e05657f02f5)
![image](https://github.com/user-attachments/assets/92afd414-5dca-4a5e-a927-5a3fad716627)

---

# Connectivity Tests

## Ping from an IT PC to a PC in the HR Department:
![image](https://github.com/user-attachments/assets/662baa42-e709-4cb3-a68a-25b935a770dc)

## Ping from a Finance smartphone to a PC in the HR Department:
![image](https://github.com/user-attachments/assets/33e08103-80be-4f54-9d37-863a97e77dab)

## Ping from an HR laptop to a printer in the Finance Department:
![image](https://github.com/user-attachments/assets/b13f53c0-06b5-41fe-9560-efcb76bf0076)

---

# Takeaways and Summary 

## Through this project, I strengthened my understanding of:

1) VLAN segmentation and network isolation

2) Sub-interface routing using a single router port (Router-on-a-Stick)

3) DHCP automation across multiple VLANs

4) Wireless integration into VLAN-based networks

5) Troubleshooting and verifying Layer 2 & 3 connectivity


















