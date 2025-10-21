# QEMU Setup for Arch Linux ( with EFIstub )
>This tutorial is based on the ArchWiki of [KVM](https://wiki.archlinux.org/title/KVM) and [QEMU](https://wiki.archlinux.org/title/QEMU)

&nbsp;&nbsp;
##### Check if your Hardware supports Virtualization   
```sh
LC_ALL=C lscpu | grep Virtualization
```
###### *Note: The correct response is VT-x for Intel and AMD-V for AMD*

&nbsp;&nbsp;
##### Enable Virtualization in BIOS ( UEFI )
- Print your Motherboard Details
    ```sh
  cat /sys/devices/virtual/dmi/id/board_{vendor,name,version}
    ```   
- Based on the details, google how to enable Virtualization in BIOS ( UEFI ) and enable it

&nbsp;&nbsp;
##### Get the VFIO PCI ID of the Video Card
- Print your Video Card Details
    ```sh
  lspci -nn | grep -i vga
    ```   
- You can find the PCI ID in the brackets:
<img width="1128" height="35" alt="image" src="https://github.com/user-attachments/assets/fcbbbc6f-25cb-42bb-85d7-7feec603776d" />
- In a typical case there is an integrated Video Card ( Intel ) and one with dedicated memory ( Nvidia )
PCI ID of the Nvidia Card: <b>10de:2560</b>

&nbsp;&nbsp;
##### Get the VFIO PCI ID of the Sound Card
- Print your Audio Card Details
    ```sh
  lspci -nn | grep -i audio
    ```
- PCI IDs are in the brackets
<img width="1224" height="34" alt="image" src="https://github.com/user-attachments/assets/59c156c3-1a48-455a-a406-ef5d721cd3d9" />
- Use the Nvidia Audio Card to separate Sound Output:
<b>10de:228e</b>

&nbsp;&nbsp;
##### Update your System
```
sudo pacman -Syyu
```

&nbsp;&nbsp;
##### Install Prerequisites
```
pacman -S qemu-full virt-manager virt-viewer dnsmasq 
pacman -S bridge-utils libguestfs ebtables vde2 openbsd-netcat
sudo pacman -S qemu libvirt edk2-ovmf virt-manager dnsmasq bridge-utils
```

&nbsp;&nbsp;
##### Edit libvirt config file
```sh
sudo vi /etc/libvirt/libvirtd.conf
```

Uncomment these lines:
```sh
unix_sock_group = "libvirt"
unix_sock_rw_perms = "0770"
```

&nbsp;&nbsp;
##### Enable Virtualization Service
```sh
sudo systemctl enable --now libvirtd.service
```

&nbsp;&nbsp;
##### Add your user to the QEMU related groups and reboot the PC
```sh
sudo usermod -a -G libvirt-qemu "$USER"
sudo usermod -a -G libvirt "$USER"
reboot
```
###### *Note: This will alow you to open the Virtual Machine Manager without password prompt*

&nbsp;&nbsp;
##### Enable Virtual Network
```sh
sudo virsh net-autostart default
sudo virsh net-start default
```

&nbsp;&nbsp;
##### Confirm Virtual Network
```sh
sudo virsh net-list --all
```

&nbsp;&nbsp;
##### Get the EFI System Partition
```sh
lsblk -f
```
<img width="1058" height="179" alt="image" src="https://github.com/user-attachments/assets/fd7579d5-dd0e-4696-a4b0-cb58b75ac0ed" />
Device: /dev/nvme0n1   
Partition Number: 1 (specifically /dev/nvme0n1p1)   
Filesystem: vfat   
Mountpoint: /boot   

&nbsp;&nbsp;
##### Get the details of your Bootloader ( Efistub )
```sh
efibootmgr
```
Expected output:
<img width="1377" height="241" alt="image" src="https://github.com/user-attachments/assets/49bd4e78-dc0e-4736-9061-a28a17c5f1fd" />


&nbsp;&nbsp;
##### Extract current Bootloader Parameters ( Example ) for Arch Linux ( 0000 in the Example )
<b>Partition GUID:</b> a39033ee-7127-4290-8f1f-61e9b998ec14   
<b>Root Partition UUID (from parameter):</b> 7ff26c23-b644-4221-a813-3ffe9e6f3e52   
<b>Boot Arguments:</b> initrd=/initramfs-linux.img root=PARTUUID=7ff26c23-b644-4221-a813-3ffe9e6f3e52 zswap.enabled=0 rw rootfstype=xfs   
<b>Boot Loader:</b> \vmlinuz-linux   

&nbsp;&nbsp;
##### Delete the old Bootloader Entry ( 0000 in the Example )
```sh
sudo efibootmgr -b 0000 -B
```

&nbsp;&nbsp;
##### Recreate the Bootloader Entry with Intel IOMMU Params
```sh
sudo efibootmgr -c -d /dev/sda -p 1 \
-L "Arch Linux (IOMMU)" \
-l "\vmlinuz-linux" \
-u "initrd=/initramfs-linux.img root=PARTUUID=7ff26c23-b644-4221-a813-3ffe9e6f3e52 zswap.enabled=0 rw rootfstype=xfs intel_iommu=on iommu=pt"
```

&nbsp;&nbsp;
##### Open the Virtual Machine Manager
```sh
virt-manager
```
###### *Note: You can also start 'Virtual Machine Manager' from your Launcher aka 'Start Menu'*

&nbsp;&nbsp;
##### Virtual Machine Manager
<img src="https://github.com/sonus89/linux_scripts/assets/10185202/f6fe9cab-2f94-4391-b207-73de690b90eb" width="25%" height="25%" />

&nbsp;&nbsp;
##### Add Connection
<img src="https://github.com/sonus89/linux_scripts/assets/10185202/cdad7589-84ae-489a-b655-b95cb13578f9" width="25%" height="25%" />
<img src="https://github.com/sonus89/linux_scripts/assets/10185202/8ee330a4-eeba-43fb-812b-b2224df1dd12" width="25%" height="25%" />
<img src="https://github.com/sonus89/linux_scripts/assets/10185202/01b5fa58-3f9f-469b-afde-d690ac6414c0" width="25%" height="25%" />

&nbsp;Select: File → Add Connection&ensp;&ensp;&ensp;&ensp;Select: QEMU/KVM, click Connect

&nbsp;&nbsp;
##### Install and Setup different Operating Systems
&emsp;[Windows](https://github.com/sonus89/linux_scripts/blob/master/arch/_install/qemu/windows_setup.md)
&emsp;[MacOS](https://github.com/sonus89/linux_scripts/blob/master/arch/_install/qemu/macos.md)


