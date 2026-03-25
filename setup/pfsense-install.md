I installed pfSense on an old Mac Desktop
I downloaded a netgate installer and got a .imd.gz
I had to extract to get the .imd file
Put the .imd file in rufus to make a bootable USB drive
Booted the Mac with the EFI Drive and installed pfSense
I ran ethernet from my router to the native port on the Mac as WAN
I used a USB adapter to run a second ethernet cable to an araknis switch as LAN
So now I have a dedicated pfSense machine sitting between the internet and my LAN
