# Desktop Environment - Basic Installation Guide

## Customize KDE

Install Basic Tools

    sudo pacman -S --noconfirm usbutils git base-devel openssh wget vi less cmake rsync reflector

Network Configuration for the Wifi

    # Configure Reflector
    sudo reflector --country Switzerland --latest 10 --sort rate --save /etc/pacman.d/mirrorlist
    
    # Disable ECN
    sudo sysctl net.ipv4.tcp_ecn=0
    
    # Disable IPv6
    sudo sysctl -w net.ipv6.conf.all.disable_ipv6=1

    # Disable Power Save
    sudo iw dev wlan0 set power_save off

Install Desktop Apps

    sudo pacman -S --noconfirm dolphin firefox flatpak discover kscreen gwenview gedit kinfocenter spectacle ktorrent p7zip unrar ark
    
Install and Configure Uncomplicated Firewall

    sudo pacman -S ufw
    sudo systemctl enable --now ufw

Install Partitioning Tools

    sudo pacman -S --noconfirm gparted ntfs-3g dosfstools exfatprogs
  
Setup Bluetooth

    sudo pacman -S --noconfirm bluez bluez-utils bluedevil
    sudo systemctl enable --now bluetooth

Install Qt5-Webkit

    sudo pacman -U --noconfirm  https://archive.archlinux.org/packages/q/qt5-webkit/qt5-webkit-5.212.0alpha4-18-x86_64.pkg.tar.zst

Add Hotkey for Screenshot

    1. Open Spectacle
    2. Select: Configure -> Shortcuts
    3. Add Win+Shift+S as Capture Rectangular Region

Install yay Package Manager

    git clone https://aur.archlinux.org/yay.git
    cd yay
    makepkg -si

Install important AUR Packages

    yay -S mkinitcpio-firmware
    sudo mkinitcpio -P
    yay -S jdk

Install Wine for Gaming

    sudo sed -i '/^#\[multilib\]/,/^#Include = \/etc\/pacman.d\/mirrorlist/s/^#//' /etc/pacman.conf
    sudo pacman -Syu
    sudo pacman -S --noconfirm wine winetricks wine-gecko

Customize Look and Feel

- Firefox / Chromium -> Settings -> General -> Dark
- Customize KDE
    - Global Theme -> Get New -> Download a Theme ( i.e. Utterly Sweet )
    - Night Light
    - Desktop Effects
        - Magic Lamp
        - Blur
- Plasma Style -> Utterly Round
- Splash Screen -> Get New -> Arch
- Login Screen -> Get New -> Utterly Sweet
- Screen Locking -> Never
- Power Management -> Do Nothing
- Konsole -> Settings -> Configure Konsole -> Profiles -> New -> OK -> Select new Profile -> Set as Default -> Edit -> Appearance -> Get New -> Select Color Scheme ( i.e. Utterly Sweet ) -> Install & Apply 
