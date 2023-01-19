# Dell-Precision-7520-OpenCore
 
### Before you give this EFI a try, make sure you read [this](#BIOS-UEFI-Settings) and [this](#Generating-your-own-serial-and-Editing-ROM)!

This repo includes an OpenCore EFI for the Dell Precision 7520.

Testing on:

Model | Dell Precision 7520
------------- | ---------------
CPU | Intel® Xeon E3-1505M V6 3GHz (4/8 Kaby lake)
Socket | 1440 FCBGA
iGPU | Intel® HD Graphics P630
RAM | 32 GB DDR4 2400MHz
WiFi | Intel® 8265 Dual-Band 2x2 802.11ac Bluetooth® 4.2
Ethernet | Intel® I219LM
Chipset | Intel Mobile CM238
Audio | ALC295
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




# BIOS UEFI settings
- System Configuration > Parallel Port
	- Parallel Port: **Disabled**
	- Default: AT
- System Configuration > Serial Port
	- Serial Port: **Enabled**
	- Default: **COM1**
- Virtualisation Support > Virtualization
	- Virtualization Support: **Enabled**
	- Default:  Enabled
- System Configuration > SATA Operation
	- SATA Operation: **AHCI**
	- Default: AHCI
- System Configuration > Thunderbolt(TM) Adapter Configuration
	- Thunderbolt: **Disabled**
	- Default: Enabled (Enable Thunderbolt(TM) Technology Support)
- Secure Boot > Secure Boot Enable
	- Secure Boot: **Disabled**
	- Default: Disabled
- General > Advanced Boot Options
	- Legacy Option ROM: **Disabled**
	- Default: Enabled
- Wake on LAN/WLAN
	- Wake on LAN/WLAN: **Disabled**
	- Default: Disabled

