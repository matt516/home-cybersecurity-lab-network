# ARAKNIS 16 PORT SWITCH

## Port Config
- Port 1 - Uplink from pfsense LAN
- Port 9(VLAN10) - Admin Workstation
- Port 10(VLAN20) - SIEM Server (Wazuh)
- Port 11(VLAN20) - Test Server
- Port 12(VLAN20) - Application Server
- Port 13(VLAN30) - Kali Linux (Attacker)

## VLAN Settings
- 1 default {Access Port} 2-8, 14-16 {Trunk Port} 1
- 10 ADMIN {Access Port} 9 {Trunk Port} 1
- 20 SERVERS {Access Port} 10-12 {Trunk Port} 1
- 30 ATTACK {Access Port} 13 {Trunk Port} 1
