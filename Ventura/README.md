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
Chipset | Intel Mobile CM238 Southbridge
Audio | ALC295
SSD | Samsung PM871
macOS | Ventura 13.1
SmBios|	MacBookPro 14,3
OpenCore | 0.8.8

Bios system information
Processor Type | Intel® Xeon® CPU E3-1505M V6 @3.00GHz
Processor ID  | 906e9
Video Controller | Intel® HD Graphics P630
Video BIOS version | GOP 1080v13
Video memory | 64MB
Panel type | 15,6' FHD 
Native Resolution | 1920 by 1080

Audio controller | ALC3254


## What works?

- Boot
- Ethernet
- WiFi /w issues: long time to connect
- Bluetooth: devices visible, untested
- Keyboard + Trackpad
- Trackpoint
- F1 & F2 & F3 Sound Key
- Battery readout
- USB /w issues: 1 USB not working


## What doesn't work?

- GPU acceleration
- headphone jack
- HDMI


## Untested
- Power Management
- Audio
- Thunderbolt (untested)
- Webcam
- SD card reader
- Sleep
- Brightness Control
- Speaker

- Intel HD P630 iGPU eDP with Backlight Output
- Intel HD P630 iGPU HDMI Output
- Intel HD P630 iGPU Type-C to HDMI Output
- Intel HD P630 iGPU - H264 & HEVC

- ALC256 Internal Speakers
- ALC256 Internal microphone
- ALC256 Combojack headphones
- ALC256 Combojack microphone
- ALC256 HDMI Audio Output
- ALC256 TYPE-C to HDMI Audio Output

- All USB-A 3.1 Ports (TYPE-C 3.1 Included)
- SpeedStep / Sleep / Wake
- HID Key PWRB & SLPB
- I2C ALPS Touchpad with gesture
- Brightness Key
- F11 Print Screen Key

- Wi-Fi and Bluetooth BCM94352Z (DELL DW1560) Module
- Lan Intel I219-LM
- SSD NVME Slot-1 PciE
- Micro SD Cardreader
- WebCam (USB-Internal)

- All Sensors CPU, IGPU, BATTERY, NVME, FAN
- ACPI Battery
- NVRAM (Native)
- Recovery (macOS) boot from OpenCore


# BIOS UEFI Settings
The required changes were moved to their own file *BIOS changes.md*


# Generating your own serial and Editing ROM
Use GenSMBios script to create your own IDs
For ROM you should use your ethernet MAC



