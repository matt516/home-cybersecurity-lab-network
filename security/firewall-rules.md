# Firewall Rules and Segmentation

## Networks

- WAN
- LAN: `10.0.1.0/24`
- ADMIN: `10.0.10.0/24`
- SERVERS: `10.0.20.0/24`
- ATTACK: `10.0.30.0/24`

## ADMIN Rules
### The ADMIN VLAN should be able to ssh into servers and access web servers and block everything else
- Allow all traffic from ADMIN subnets

## SERVERS Rules
### The SERVERS VLAN should be able to access the internet and DNS and let ADMIN access certain ports and block everything else
- Allow TCP/UDP traffic from ADMIN subnets through ports 22, 443, 3389 to SERVERS subnets
- Allow TCP/UDP traffic from SERVERS subnets through ports 80, 443, 53
- Block all traffic from SERVERS subnets

## ATTACK Rules
### The ATTACK VLAN should be highly restricted letting only certain traffic through for the sake of the lab and allowing internet access
- Allow TCP traffic from ATTACK subnets through port 1515 to 192.168.20.70
- Allow TCP/UPD traffic from ATTACK subnets through port 1514 to 192.168.20.70
- Allow TCP/UDP traffic from ATTACK subnets through port 22 to 192.168.20.50
- Block all traffic from ATTACK subnets to ADMIN subnets
- Block all traffic from ATTACK subnets to SERVERS subnets
- Allow TCP/UDP traffic from ATTACK subnets through ports 53, 80, 443
- Block all traffic from ATTACK subnets

