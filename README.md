![Arch Logo](https://archlinux.org/static/logos/archlinux-logo-light-90dpi.png)

# Install Arch Linux on VMware

## Virtual Machine Settings

- **Memory**: 4096
- **Processors**:
  - **Number of processors**: 2
  - **Number of cores per processors**: 2
- **Hard disk**: 100GB
- **Network adapter**: Bridged (Replicate physical network connection state)

Open `Arch.vmx` and add the following lines:

```
keyboard.allowBothIRQs = "FALSE"
keyboard.vusb.enable = "TRUE"
keyboard.typematicMinDelay = "500000"
```

## Install packages

```bash
sudo pacman -S base base-devel bspwm burpsuite clang clinfo dmenu docker docker-compose firefox git grub gst-plugin-pipewire gtkmm3 hashcat htop iwd kitty libpulse lightdm lightdm-gtk-greeter linux linux-firmware metasploit nano nmap noto-fonts-emoji ntp open-vm-tools openbsd-netcat opencl-mesa openssh openvpn paru paru-debug pipewire pipewire-alsa pipewire-jack pipewire-pulse pocl polybar python-pipx rlwrap ruby-default-gems ruby-evil-winrm ruby-stdlib rxvt-unicode seclists smartmontools sxhkd ttf-jetbrains-mono-nerd unzip vim wget wireless_tools wireplumber wireshark-qt wpa_supplicant xclip xdg-utils xdo xorg-server xorg-xinit zip zram-generator
```

```bash
paru -S ffuf
```

## Firefox Middle Click Scroll Solution

1. Open Firefox and type `about:config` in the address bar
2. Click `Accept the Risk and Continue`
3. In the search box, type `general.autoScroll`
4. Toggle the value to true (double-click or use the toggle button)
