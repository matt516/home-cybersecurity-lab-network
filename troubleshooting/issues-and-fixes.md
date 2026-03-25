Configured IP address range for LAN devices inside of pfSense
Existing Control4 controller had an existing IP address that was outside the newly established range
Updated the controller to fit the new IP range

Internet keeps dropping from wired connection
I swapped the interfaces so router is plugged into native eth, the switch is plugged into the USB NIC
The problems persisted but this time the ethernet stayed connected to the internet on my laptop and lost connection to pfsense webGUI
The problem seems to be with the USB NIC so I got a mini pc to replace the old mac as the pfsense machine

Alias wasn't showing up in firewall rules
I had to assign my own alias to use
