# Dell-Precision-7520-OpenCore
 
### Before you give this EFI a try, make sure you read [this](#BIOS/UEFI-Settings) and [this](#Generating-your-own-serial-and-Editing-ROM)!

This repo includes an OpenCore EFI for the Dell Precision 7520.

Testing on:

Model | Dell Precision 7520
------------- | ---------------
CPU | Intel Xeon E3-1505MV5 2.80GHz
iGPU | Intel® HD Graphics P530
RAM | 32 GB DDR4
WiFi | Intel® Dual Band-Wireless-AC 8265
macOS | Ventura 13.0

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




## BIOS/UEFI settings

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
###MAKE SURE YOU KNOW WHAT YOU ARE DOING BEFORE CHANGING THESE VALUES, AS IT MAY BREAK YOUR SYSTEM!
From there enter these commands:
setup_var 0x4ED 0x00 (Disable CFG-Lock)
setup_var 0x79A 0x1 (Enable Above 4G Decoding)
setup_var 0x795 0x2 (set DVMT Pre-Allocation to 64MB)
setup_var 0x796 0x3 (set DVMT Total GFX Size to MAX)

## How to install

Download this repo and place the EFI folder into your internal drive's EFI partition... That's it.

## How to Install macOS Ventura

1. Have a working install of macOS, [download](https://mrmacintosh.com/macos-ventura-13-full-installer-database-download-directly-from-apple/) the full installer package, install it to get the installer app, then make a bootable Installer with `createinstallmedia` by using this command in Terminal `sudo /Applications/Install\ macOS\ Ventura.app/Contents/Resources/createinstallmedia --volume /Volumes/NameOfTheUSB`

After you have created a bootable Installer, copy the EFI folder to the EFI partition of the installer drive and install as usual (GUID Partiton Map; APFS). After the installation, mount the EFI partition of the installed OS and copy the EFI folder to its partition.

## Generating your own serial and Editing ROM

Use GenSMBIOS (https://github.com/corpnewt/GenSMBIOS) to generate a serial for MacBookPro13,3 (Skylake) or 14,3 (Kaby Lake)

use Xcode, ProperTree or any decent plist editor to manually enter the details in the following sections of the config (as shown in the video): (SystemSerialNumber, MLB, and UUID)

https://user-images.githubusercontent.com/59102649/116117179-3ea51200-a6bc-11eb-8a18-a03f7bb5bf1d.mp4

You should also put in your ethernet adapter's MAC address into the ROM section.

## Credits

* [acidanthera](https://github.com/acidanthera) (for OpenCore and the kexts)
* [dortania](https://dortania.github.io/OpenCore-Install-Guide/) (for their awesome guide)
* [OpenIntelWireless](https://github.com/OpenIntelWireless) (for Intel WiFi and Bluetooth)
* [blankmac](https://github.com/blankmac/AlpsHID) (for the APLS I2C TouchPad kext)
