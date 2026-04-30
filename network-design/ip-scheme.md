# IP Scheme and Network Design

## Current Topology

```text
Fiber Internet
    ↓
Edge Router
    ↓
pfSense Firewall (WAN)
    ↓
pfSense LAN (VLAN Trunk)
    ↓
Managed Switch (802.1Q VLANs)
    ↓
Lab Clients & Servers

## Internal network Segmentation

LAN: 10.0.1.0/24

Management VLAN (VLAN 10)
10.0.10.0/24
- Admin Workstation: 10.0.10.50
- DHCP Range: 10.0.10.100 - 10.0.10.199

Server VLAN (VLAN 20)
10.0.20.0/24
- Application Server: 10.0.20.70
- SIEM Server (Wazuh): 10.0.20.60
- Test Server: 10.0.20.50
- DHCP Range: 10.0.20.100 - 10.0.20.199

Attack VLAN (VLAN 30)
10.0.30.0/24
- Kali Linux (Attacker): 10.0.30.50
- DHCP Range: 10.0.30.100 - 10.0.30.199


Design Overview

This lab simulates a segmented enterprise network using VLANs to isolate management, server, and attacker environments.

Security controls implemented:
- Inter-VLAN firewall rules (pfSense)
- Principle of least privilege
- Segmentation to prevent lateral movement
- Centralized logging via SIEM (Wazuh)

Validation:
- Nmap scanning from attacker VLAN
- Firewall rule verification
- Detection via SIEM alerts
