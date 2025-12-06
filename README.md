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

## Archinstall

```bash
loadkeys la-latin1
setfont ter-v20b
pacman -Sy archinstall
archinstall
```

- Archinstall language: **English 100%**
- Locales
  - Keyboard layout: **la-latin1**
  - Locale language: **en_US.UTF-8**
  - Locale encoding: **UTF-8**
- Mirrors and repositories
  - Select regions: **Brazil**
  - Optional repositories: **multilib**
- Disk configuration
  - Partitioning
    - Use a best-effort default partition layout: **VMware..**
      - Filesystem: **ext4**
- Bootloader:
  - Bootloader: **Grub**
- Autehntication
  - User account
    - Add a user
      - Should $USER be a superuser (sudo)?: **Yes**
- Profile
  - Type
    - Desktop: **Bspwm**
  - Graphics driver: **All open-source**
  - Greeter: **lightdm-gtk-greeter**
- Applications
  - Audio: **Pipewire**
- Kernels: **linux**
- Network configuration: **Copy ISO network configuration to installation**
- Timezone: **America/Argentina/Buenos_Aires**
- Automatic time sync (NTP): **YES**

## Install packages

```bash
sudo pacman -S base base-devel bind bspwm burpsuite clang clinfo dmenu docker docker-compose firefox git gnome-themes-extra grub gst-plugin-pipewire gtkmm3 hashcat htop iwd kitty libpulse lightdm lightdm-gtk-greeter linux linux-firmware metasploit nano nfs-utils nmap noto-fonts-emoji ntp open-vm-tools openbsd-netcat opencl-mesa openssh openvpn paru paru-debug pipewire pipewire-alsa pipewire-jack pipewire-pulse pocl polybar python-pipx rlwrap ruby-default-gems ruby-evil-winrm ruby-stdlib rxvt-unicode seclists smartmontools sxhkd ttf-jetbrains-mono-nerd unzip vim wget wireless_tools wireplumber wireshark-qt wpa_supplicant xclip xdg-utils xdo xorg-server xorg-xinit zip zram-generator
```

```bash
paru -S ffuf
```

## Firefox Middle Click Scroll Solution

1. Open Firefox and type `about:config` in the address bar
2. Click `Accept the Risk and Continue`
3. In the search box, type `general.autoScroll`
4. Toggle the value to true (double-click or use the toggle button)
