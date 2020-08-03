# arch-setup

arch-setup is a console menu based (TUI) install script for Arch Linux.

The goal of this project is to provide a "Debian-like" install experience for new users interested
in Arch Linux. Nearly every aspect of the install process is configurable by the installer. However,
when it comes to more complicated aspects such as partitioning, the installer uses sane defaults to
keep the installation process as user friendly as possible.

![preview](https://media.giphy.com/media/kGQ5M2i1oVTk3I1t4o/giphy.gif)

## Usage

### Prerequisites

* Bootable installation media
  * First, [download](https://www.archlinux.org/download/) the latest Arch ISO. Then, follow the instructions to [create a bootable device](https://wiki.archlinux.org/index.php/USB_flash_installation_media)
* Working internet connection
  * If you require a wireless connection, use the `iwctl` command to [connect to a network](https://wiki.archlinux.org/index.php/Iwd#iwctl)

### Downloading and Running the Script

1. Once you have booted into the live media, install git and dialog: `pacman -Sy git dialog`
   * If you encounter `error: not enough free disk space`, then increase cowspace:

     `mount -o remount,size=1G /run/archiso/cowspace`

2. Clone this repository: `git clone https://github.com/jorgeluiscarrillo/arch-setup && cd arch-setup/`
3. Run the script: `./setup`

## Features

### Sane Defaults

Sane defaults are a set of predefined configurations that simply make sense for users of all levels
of Linux experience.

* Automatic Partitioning
  * Full disk partitioning with optional swap partition
  * Full disk partitioning with LVM
  * Full disk partitioning with LVM and root disk encryption (LVM on LUKS)

* Networking
  * NetworkManager: Provides detection and configuration to automatically connect to a network
  * nm-applet: GUI front-end for NetworkManager

* Boot loader
  * GRUB: Provides support for BIOS/UEFI systems and most file systems

### Desktop Environment and Window Managers

Users may choose to install a complete desktop environment or a minimal window manager

* Desktop Environments
  * Budgie
  * Cinnamon
  * GNOME
  * KDE Plasma
  * LXDE
  * LXQT
  * MATE
  * Xfce
* Window Managers
  * awesome
  * bspwm
  * Fluxbox
  * i3
  * Openbox
  * xmonad

### Graphics Drivers and Virtual Machine Support

Discrete graphics hardware is automatically detected. Users may choose to install open-source or
proprietary drivers. If a virtual machine is detected, any utilities and drivers will be installed.

* ATI/AMD
  * AMDGPU open-source driver
  * ATI (Radeon) open-source driver
* NVIDIA
  * Nouveau open-source driver
  * NVIDIA proprietary driver
* Virtual Machine Utilities
  * VirtualBox: Guest Additions
  * VMware Workstation: Open Virtual Machine Tools
