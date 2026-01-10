# Waydroid with Dedicated Bluetooth ( on Arch Linux )

## Install Waydroid

## Add Dedicated Bluetooth
1. Get a Bluetooth Dongle
2. Execute the <b>watch</b> Command and Plug in your Device
   
       watch -n 0.5 lsusb
3. Save the Bus & Device Numbers   
   <img width="536" height="22" alt="image" src="https://github.com/user-attachments/assets/4344495c-63a0-44f7-9bf9-06c43f5fd24f" />

5. Edit the Config File for Waydroid   
   
       sudo nano /var/lib/waydroid/lxc/waydroid/config
6. 
