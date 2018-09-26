# wifiFirmwareUpdater

To use this, you must:

1. Install the .deb file on a jailbroken 64 bit iPhone (no iPads or iPods are tested).

2. Go to ipsw.me and download the ipsw for your iPhone only. Choose whichever OS that contains the WiFi firmware that you desire.

3. Open the IPSW by changing the file extension to .zip and extracting it. From here, open the dmg that is the largest in size.

4. Navigate to /usr/share/firmware/wifi and copy every folder from their onto your device into /var/mobile/wififirmware (this is where my tool will look to find your proper wifi firmware.

5. When the folders are in place, make sure that they are given proper permissions. If they are not, you may use chmod +x to give the files proper permissions.

6. Run wifiFirmwareUpdater AS ROOT, or it won't work.

If you're curious to exactly which files your device uses, you can run a script that I included with this project, wifioutput. Some iPhone 7's use different wifi firmware, and this is why some IPSW's contain more folders in /usr/share/firmware/wifi.

My script parses the output of /usr/libexec/wifiFirmwareLoader -f (or /usr/libexec/wifiFirmwareLoaderLegacy -f) to find these files and then properly uses them to load whichever wifi firmware is present based on name. DO NOT CHANGE THE NAME OF THE FILES, OR THIS WON'T WORK.

Why is this safe?

1. iOS reverts to the default WiFi firmware on reboot, which is present on the device in /usr/share/firmware/wifi. My script doesn't mess with these files, so therefore iOS still looks to them when booting up. I highly recommend not messing with these files although you technically can get it working in a non-jailbroken state with this file modification.

2. If for some reason the WiFi firmware that you use causes WiFi to stop working, you can reboot and as mentioned above, iOS will revert to default firmware.

3. Rather than modifying system files, wifiFirmwareUpdater uses an already present executable in iOS called wifiFirmwareLoader to load specified firmware files. Developer of Liberty. Ryley Angus discovered what this can do by finding what arguments it takes and presented the idea for me to write this script here: https://www.reddit.com/r/jailbreak/comments/6scs80/tutorial_possible_method_to_patch_broadpwn_wifi/

My script simply makes this easier as it is as simple as placing a few folders inside of /var/mobile/wififirmware.

I no longer have time to keep updating this at least for now, so feel free to help with it if you feel it is worth your time. I also cannot host Apple's wifi firmware files here as that is illegal, which is why you must download the IPSW and get them yourself.

