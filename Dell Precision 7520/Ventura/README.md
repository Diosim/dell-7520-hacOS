# Dell-Precision-7520-OpenCore
 
### Before you give this EFI a try, make sure you read [this](#BIOS/UEFI-Settings) and [this](#Generating-your-own-serial-and-Editing-ROM)!

This repo includes an OpenCore EFI for the Dell Precision 7520.

Testing on:

Model | Dell Precision 7520
------------- | ---------------
CPU | Intel® Xeon E3-1505MV5 2.80GHz (4/8 Skylake)
iGPU | Intel® HD Graphics P530
RAM | 32 GB DDR4
WiFi | Intel® Dual Band-Wireless-AC 8265
Ethernet | Intel® I219
SSD | Samsung PM871
macOS | Ventura 13.0
SmBios|	MacBookPro 13,3
OpenCore | 0.8.8

## What works?

- Battery readout
- Boot
- Ethernet
- Keyboard + Trackpad
- Power Management
- WiFi
- Bluetooth
- USB
- Trackpoint

## Untested

- Audio
- Thunderbolt (untested)
- Webcam
- SD card reader
- Sleep
- Brightness Control
- Speaker

## What doesn't work?

- GPU acceleration
- headphone jack
- HDMI




# BIOS/UEFI settings

- Parallel Port: Disabled
- Serial Port: Enabled
- Virtualization Support: Enabled
- SATA Operation: AHCI
- Thunderbolt: Disabled
- Secure Boot: Disabled
- Legacy Option ROM: Disabled
- Wake on LAN/WLAN: Disabled

You'll also need to set some settings that are hidden from the menu.
Boot the OpenCore EFI, press Space and select modGRUBShell.efi
## MAKE SURE YOU KNOW WHAT YOU ARE DOING BEFORE CHANGING THESE VALUES, AS IT MAY BREAK YOUR SYSTEM!
From there enter these commands:
Disable CFG-Lock (Default:	0x01):
```
setup_var 0x4ED 0x00
```

Enable Above 4G Decoding (Default:	0x00):
```
setup_var 0x79A 0x1
```

set DVMT Pre-Allocation to 64MB (Default:	0x02):
```
setup_var 0x795 0x2
```

set DVMT Total GFX Size to MAX (Default:	0x02):
```
setup_var 0x796 0x3
```



