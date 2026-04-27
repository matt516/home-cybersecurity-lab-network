# home-cybersecurity-lab-network
## (STILL IN PROGRESS)

Hands-on cybersecurity lab using pfsense, linux machines, VLANs, and virtual machines to simulate enterprise network security scenarios.

🛡️ Home Cybersecurity Lab

📌 Overview

This project documents the design and implementation of a home cybersecurity lab built to simulate enterprise network environments. The lab uses pfSense as a firewall, VLAN segmentation, and virtual machines to practice real-world security scenarios.

---

🎯 Objectives

* Build a segmented network using VLANs
* Configure firewall rules and access controls
* Simulate attacks using Kali Linux
* Analyze traffic and logs

---

🧱 Network Architecture

*(Insert diagram in /network-design/diagram.png)*

---

🛠️ Technologies Used

* pfSense (Firewall)
* VirtualBox / VMware
* Kali Linux
* Ubuntu Server
* Windows VM
* Raspberry Pi

---

🔐 Key Concepts Practiced

* Network segmentation
* Firewall rule configuration
* Least privilege access
* Traffic analysis

---

📂 Project Structure

* `/docs` → Overview and planning
* `/network-design` → Diagrams and IP schemes
* `/setup` → Installation steps
* `/security` → Firewall rules and segmentation
* `/testing` → Validation and results
* `/troubleshooting` → Issues and fixes

---

🚀 Status

## Current Progress

- pfSense installed and running
- WAN and LAN configured
- LAN subnet changed to `192.168.10.0/24`
- DHCP configured on LAN
- pfBlockerNG installed
- LAB and ATTACK VLANs created
- Firewall rules created to isolate ATTACK from private internal networks
- Troubleshooting documented for DHCP, interface resets, and USB NIC instability

## Current Security Design

The ATTACK network is intentionally restricted so it can reach the internet but cannot access private internal networks. This simulates lateral movement prevention and segmented trust zones in an enterprise environment.
