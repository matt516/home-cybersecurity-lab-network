Configured IP address range for LAN devices inside of pfSense
Existing Control4 controller had an existing IP address that was outside the newly established range
Updated the controller to fit the new IP range

## 4. Connectivity loss after LAN subnet change

### Symptom
After changing the LAN from `192.168.1.0/24` to `192.168.10.0/24`, the admin laptop lost connectivity.

### Finding
The laptop still had an address from the previous subnet and could no longer communicate with the firewall.

### Resolution
Reconfigured the LAN interface in pfSense and renewed addressing on the client side.

---

## 5. DHCP failure on LAN

### Symptom
`ipconfig /renew` would hang and the laptop could not get an address.

### Finding
The `dhcpd` service was not running properly after changes and interface resets.

### Resolution
Reconfigured the LAN interface and restarted/rebooted pfSense to restore DHCP service.

---

## 6. USB Ethernet instability

### Symptom
Intermittent network drops, DHCP failures, and web configurator instability occurred during lab setup.

### Finding
The USB Ethernet adapter introduced instability when used for critical interfaces.

### Resolution
Identified USB NIC instability as the likely root cause and noted that the long-term fix is to move pfSense to hardware with native or PCIe Ethernet interfaces.

---

## 7. Firewall rule design confusion

### Symptom
Initial ATTACK rules only targeted the WAN address or were too broad.

### Finding
This either failed to allow internet correctly or unintentionally allowed internal network access.

### Resolution
Created a two-rule model:
1. Block ATTACK to private networks
2. Allow ATTACK to any remaining destination

This correctly enforced segmentation.
