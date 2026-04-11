
# pfSense Installation and Initial Configuration

## Summary

pfSense Community Edition was installed on an older Intel-based Mac as a temporary firewall platform for the lab. The installation required external storage and a USB Ethernet adapter because the hardware did not have a sufficient number of built-in Ethernet interfaces. After getting it set up, it was dropping the connection to the LAN so I had to replace the mac with a mini Vault PC. Now with the Vault in place it has 4 ethernet ports, one is being used for WAN coming from the nest router and one for the LAN travelling to the switch.

## Installation Process

1. Downloaded the Netgate installer image
2. Extracted the `.img.gz` file into a raw `.img`
3. Flashed the installer image to USB using Rufus
4. Booted the Mac using EFI boot
5. Installed pfSense to an external drive
6. Assigned interfaces:
   - WAN: built-in Ethernet
   - LAN: USB Ethernet adapter
7. Configured LAN IP and DHCP
8. Logged into the pfSense web interface and completed setup wizard
9. Flashed installer with rufus for CE pfsense for Vault
10. pfsense booted onto the Vault 

## Initial LAN Configuration

- LAN IP: `192.168.10.1/24`
- DHCP enabled on LAN
- DHCP range: `192.168.10.100 - 192.168.10.199`

## WAN Configuration

- WAN type: DHCP
- Upstream router: Google Nest
- WAN received a private DHCP address from the upstream router

## DNS Configuration

- Primary DNS: `1.1.1.1`
- Secondary DNS: `8.8.8.8`

## Notes

The lab initially used a USB Ethernet adapter for LAN or WAN depending on interface testing. This introduced intermittent instability and became a major troubleshooting point during setup. As such the mac was replaced with a mini pc that runs pfsense, it has 4 dedicated ethernet ports.
