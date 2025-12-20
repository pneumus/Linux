# Desktop Environment - Basic Installation Guide

## Customize KDE

Disable Explicit Congestion Notification (ECN)

    sudo sysctl net.ipv4.tcp_ecn=0

Install Basic Tools

    sudo pacman -S --noconfirm usbutils git base-devel openssh wget vi less cmake rsync reflector

Install and Configure Uncomplicated Firewall

    sudo pacman -S ufw
    sudo systemctl enable --now ufw

Install Desktop Apps

    sudo pacman -S --noconfirm dolphin firefox chromium flatpak discover kscreen gwenview gedit kinfocenter spectacle ktorrent ark p7zip unrar

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
