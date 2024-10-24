
Driver for Linux RTL8188GU (RTL8710B) (VID:PID = 0x0BDA:0xB711)
===============================================================

Is not original driver from Realtek, is build from source code from others official Realtek drivers.

Instructions for Debian 12

User root:

systemctl --now disable wpa_supplicant

iwd is an alternative to wpasupplicant. IWD itself is considered stable since debian Bookworm / 11, is supported as backed by both ConnMan and NetworkManager, however the NetworkManager backend is considered in an experimental state

apt install iwd

systemctl --now enable iwd

Connecting through iwctl

Interactive mode

 iwctl

To get the list of Wifi devices

 [iwd]# device list







Compiling & Building
--------------------
### Dependencies
To compile the driver, you need to have make and a compiler installed. In addition,
you must have the kernel headers installed. If you do not understand what this means,
consult your distro.
### Compiling

> make

### Installing

> sudo make install

### Disable CDROM mode and select in WiFi mode. (not for Ubuntu 20.04)

> eject /dev/cdrom0

### Known problems

1. Very slow upload speed.
2. Problem reconnect from KNetworkManager in Kubuntu 20.04.
3. In Ubuntu 20.04 detected as GSM modem, need remove option driver as "sudo rmmod option".

### Testing
I tested on Ubuntu 16.04, 20.04 and last version OpenWRT, it's work...
