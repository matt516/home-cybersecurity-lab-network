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

<img width="624" height="441" alt="Cyber-Security-Home-Lab (1)" src="https://github.com/user-attachments/assets/72bd39d0-05e8-41c5-ac58-0a85523a066b" />

---

🛠️ Technologies Used

* pfSense (Firewall)
* Kali Linux
* Ubuntu Server
* Ubuntu Desktop
* Raspberry Pi
* Managed Switch

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
* `/security` → Firewall rules and hardening
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
