# IP Scheme and Network Design

## Current Topology

```text
Fiber Internet
    ↓
Google Nest Router
    ↓
pfSense WAN
    ↓
pfSense LAN / VLANs
    ↓
Araknis Switch
    ↓
Client devices / lab devices

Internal networks
LAN: 192.168.1.0/24
ADMIN VLAN: 192.168.10.0/24
Admin Laptop IP: 192.168.10.50
DHCP range: 192.168.10.100 - 192.168.10.199
SERVERS VLAN: 192.168.20.0/24
Ubuntu-Desktop(Dell): 192.168.20.70
Ubuntu-Desktop(Mac): 192.168.20.60
Ubuntu-Server: 192.168.20.50
DHCP range: 192.168.20.100 - 192.168.20.199
ATTACK VLAN: 192.168.30.0/24
Kali IP: 192.168.30.50
DHCP range: 192.168.30.100 - 192.168.30.199


Design Reasoning:
192.168.10.0/24 is used for the main trusted LAN
192.168.20.0/24 is used for lab systems and targets
192.168.30.0/24 is used for attacker/testing systems
