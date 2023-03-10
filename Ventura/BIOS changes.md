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


## For the next part there are some settings that are hidden from the BIOS menu.
## MAKE SURE YOU KNOW WHAT YOU ARE DOING BEFORE CHANGING THESE VALUES, AS IT MAY BREAK YOUR SYSTEM!
## I can not be held responsible for any harm that is done to your system using those values!
Boot the OpenCore EFI, press Space and select modGRUBShell.efi


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



# The above values were extracted from BIOS version 1.14.1 for the Dell Precision 7520 (BIOS values dump is seen below)

Location | CFG Lock
------------- | ---------------
0x399A3 |			One Of: **CFG Lock**, VarStoreInfo (VarOffset/VarName): **0x4ED**, VarStore: 0x1, QuestionId: 0x2BB, Size: 1, Min: 0x0, Max 0x1, Step: 0x0 {05 91 EF 02 F0 02 BB 02 01 00 ED 04 10 10 00 01 00}
0x399B4 |			One Of Option: **Disabled**, Value (8 bit): **0x0** {09 07 04 00 00 00 00}
0x399BB |			One Of Option: Enabled, Value (8 bit): **0x1 (default)** {09 07 03 00 30 00 01}

Location | 4GB MMIO BIOS assignment
------------- | ---------------
0x40E49 |			One Of: Above 4GB MMIO BIOS assignment, VarStoreInfo (VarOffset/VarName): **0x79A**, VarStore: 0x1, QuestionId: 0x51F, Size: 1, Min: 0x0, Max 0x1, Step: 0x0 {05 91 1C 06 1D 06 1F 05 01 00 9A 07 10 10 00 01 00}
0x40E5A |			One Of Option: **Enabled**, Value (8 bit): **0x1** {09 07 8F 00 00 00 01}
0x40E61 |			One Of Option: Disabled, Value (8 bit): **0x0 (default)** {09 07 90 00 30 00 00}

Location | DVMT Pre-Allocated
------------- | ---------------
0x411C6 |				One Of: **DVMT Pre-Allocated**, VarStoreInfo (VarOffset/VarName): **0x795**, VarStore: 0x1, QuestionId: 0x52F, Size: 1, Min: 0x0, Max 0xFE, Step: 0x0 {05 91 0C 05 1F 05 2F 05 01 00 95 07 14 10 00 FE 00}
0x411D7 |				One Of Option: 0M, Value (8 bit): 0x0 {09 07 0D 05 00 00 00}
0x411DE |				One Of Option: 32M, Value (8 bit): 0x1 {09 07 0E 05 00 00 01}
0x411E5 |				One Of Option: **64M**, Value (8 bit): **0x2** (default) {09 07 0F 05 30 00 02}
0x411EC |				One Of Option: 4M, Value (8 bit): 0xF0 {09 07 10 05 00 00 F0}
0x411F3 |				One Of Option: 8M, Value (8 bit): 0xF1 {09 07 11 05 00 00 F1}
0x411FA |				One Of Option: 12M, Value (8 bit): 0xF2 {09 07 12 05 00 00 F2}
0x41201 |				One Of Option: 16M, Value (8 bit): 0xF3 {09 07 13 05 00 00 F3}
0x41208 |			One Of Option: 20M, Value (8 bit): 0xF4 {09 07 14 05 00 00 F4}
0x4120F |				One Of Option: 24M, Value (8 bit): 0xF5 {09 07 15 05 00 00 F5}
0x41216 |				One Of Option: 28M, Value (8 bit): 0xF6 {09 07 16 05 00 00 F6}
0x4121D |				One Of Option: 32M/F7, Value (8 bit): 0xF7 {09 07 17 05 00 00 F7}
0x41224 |				One Of Option: 36M, Value (8 bit): 0xF8 {09 07 18 05 00 00 F8}
0x4122B |			One Of Option: 40M, Value (8 bit): 0xF9 {09 07 19 05 00 00 F9}
0x41232 |				One Of Option: 44M, Value (8 bit): 0xFA {09 07 1A 05 00 00 FA}
0x41239 |			One Of Option: 48M, Value (8 bit): 0xFB {09 07 1B 05 00 00 FB}
0x41240 |			One Of Option: 52M, Value (8 bit): 0xFC {09 07 1C 05 00 00 FC}
0x41247 |				One Of Option: 56M, Value (8 bit): 0xFD {09 07 1D 05 00 00 FD}
0x4124E |				One Of Option: 60M, Value (8 bit): 0xFE {09 07 1E 05 00 00 FE}

Location | DVMT Total Gfx Mem
------------- | ---------------
0x41259 |			One Of: **DVMT Total Gfx Mem**, VarStoreInfo (VarOffset/VarName): **0x796**, VarStore: 0x1, QuestionId: 0x530, Size: 1, Min: 0x1, Max 0x3, Step: 0x0 {05 91 20 05 21 05 30 05 01 00 96 07 10 10 01 03 00}
0x4126A |			One Of Option: 256M, Value (8 bit): 0x2 (default) {09 07 23 05 30 00 02}
0x41271 |				One Of Option: 128M, Value (8 bit): 0x1 {09 07 22 05 00 00 01}
0x41278 |				One Of Option: **MAX**, Value (8 bit): **0x3** {09 07 24 05 00 00 03}

