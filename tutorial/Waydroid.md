# Waydroid with Dedicated Bluetooth ( on Arch Linux )

## Install Waydroid

## Add Dedicated Bluetooth
1. Get a Bluetooth Dongle
2. Execute the <b>watch</b> Command and Plug in your Device
   
       watch -n 0.5 lsusb
3. Save the Bus & Device Numbers   
   <img width="536" height="22" alt="image" src="https://github.com/user-attachments/assets/4344495c-63a0-44f7-9bf9-06c43f5fd24f" />

5. Edit the Config File for Waydroid   
   
       sudo gedit /var/lib/waydroid/lxc/waydroid/config
6. Allow <b>Waydroid</b> to access this specific <b>USB device</b> (Bus 003, Device 032)

         lxc.cgroup.devices.allow = c 189:* rwm
         lxc.mount.entry = /dev/bus/usb/003/032 dev/bus/usb/003/032 none bind,optional,create=file
7. Give Permission to the Device

         sudo chmod 666 /dev/bus/usb/003/032
9. Restart <b>Waydroid</b>
         
         waydroid session stop
         waydroid session start
