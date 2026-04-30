
# pfSense Installation and Initial Configuration

## Summary

pfSense Community Edition was installed on an older Intel-based Mac as a temporary firewall platform for the lab. After getting it set up, it was dropping the connection to the LAN due to the use of a usb ethernet adapter, so I had to replace the mac with a mini Vault PC. Now with the Vault in place it has 4 ethernet ports, one is being used for WAN coming from the router and one for the LAN travelling to the switch.

## Installation Process

### Initial Mac Setup
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
   
### Vault Setup
- Flashed installer with rufus for CE pfsense for Vault
- pfsense booted onto the Vault
- Followed same setup steps

## Initial LAN Configuration

- LAN IP: `10.0.1.0/24`
- DHCP enabled on LAN
- DHCP range: `10.0.1.100 - 10.0.1.199`

## WAN Configuration

- WAN type: DHCP
- Upstream router: Edge Router
- WAN received a private DHCP address from the upstream router

## DNS Configuration

- Primary DNS: `1.1.1.1`
- Secondary DNS: `8.8.8.8`

