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
LAN: 192.168.10.0/24
pfSense LAN IP: 192.168.10.1
DHCP range: 192.168.10.100 - 192.168.10.199
LAB VLAN: 192.168.20.0/24
pfSense LAB IP: 192.168.20.1
ATTACK VLAN: 192.168.30.0/24
pfSense ATTACK IP: 192.168.30.1

Design Reasoning:
192.168.10.0/24 is used for the main trusted LAN
192.168.20.0/24 is used for lab systems and targets
192.168.30.0/24 is used for attacker/testing systems
