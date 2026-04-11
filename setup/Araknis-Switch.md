# ARAKNIS 16 PORT SWITCH

## Port Config
- Port 1 - Uplink from pfsense LAN
- Port 2 - ea3 control4 controller
- Port 9(VLAN10) - Admin laptop
- Port 10(VLAN20) - Dell Laptop running Ubuntu Desktop(Wazuh)
- Port 11(VLAN20) - Raspberry PI running Ubuntu Server
- Port 12(VLAN20) - Mac Desktop Ubuntu Desktop
- Port 13(VLAN30) - Mac Desktop Kali Linux(Attacker)

## VLAN Settings
- 1 default {Access Port} 2-8, 14-16 {Trunk Port} 1
- 10 ADMIN {Access Port} 9 {Trunk Port} 1
- 20 SERVERS {Access Port} 10-12 {Trunk Port} 1
- 30 ATTACK {Access Port} 13 {Trunk Port} 1
