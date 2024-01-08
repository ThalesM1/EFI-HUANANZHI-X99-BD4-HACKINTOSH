# HUANANZHI X99 BD4 + Intel® Xeon® E5-2670 v3 + AMD Radeon™ RX 6600 + Fenvi T919


**Latest working macOS**: 14.2.1
<br>
**Current OpenCore**: 0.9.7

---

## Complete hardware specs

- Intel® Xeon® E5-2670 v3 (All physical cores activated)
- HUANANZHI X99 BD4 + Unlock Turbo Boost + Resizable Bar Activated
- AMD Radeon™ RX 6600
- 2x 16Gb DDR4 3200Mhz ECC Atermiter
- Wi-fi/Bluetooth replaced by Fenvi T919

## What works

- macOS Sonoma, Ventura, Big Sur, Catalina and macOS Monterey
- Audio (Sonoma ->  you will have to add in boot-args: alcid=11)  
- HDMI/DP (in dGPU - Works OOB)
- All USB ports
- Everything iCloud related (Drive, iMessage, Facetime, unlock with Apple Watch, etc)
- Temperature monitoring for everything
- DRM content (Netflix, ATV+, Airplay 2 mirroring etc)
- Shutdown/Reboot/Update to newer macOS builds over time
- Resizable Bar ON (ResizeUsePciRbIo = true)
- Wi-fi/Bluetooth/AirDrop - OpenCore Legacy Patcher (see below) 

## Kexts used:

- [x] AppleALC.kext
- [x] CpuTscSync.kext
- [x] FeatureUnlock.kext
- [x] Lilu.kext
- [x] RealtekRTL8111.kext
- [x] RestrictEvents.kext
- [x] SMCSuperIO.kext
- [x] SMCProcessor.kext
- [x] USBMap.kext
- [x] VirtualSMC.kext
- [x] WhateverGreen.kext
- [x] XHCI-unsupported.kext


## How does it works (if you have the same hardware): 
  0. Config the BIOS, expecs bellow
  1. Get the EFI
  2. Config the SMBIOS, generating one with genSMBIOS, then edit it using properTree: ROM, SystemUUID, MLB, system serial number
  3. Download **macOs Catalina** from macrecovery
  4. Create the bootable pen drive, install Catalina from Open Core
  5. Update from oficial Apple
  6. A few modifications will be needed to make the wifi works, this modification will be made within the apple environment, with the opencore configurator
    6.1. Use the hackintool to see if the wifi card is recognizes
    6.2 Open config.plist and modify secure-boot to false and 
    6.3 Add two kexts to kext folder: IOSkywalkFamily.kext and IO80211SkywalkFamily.kext and change the min kernel in the config.plist to 23.0.0
    6.4 Go to block add a new block: inside the field identifier type: com.apple.iokit.IOSkywalkFamily; and in the field comment type: Allow IOSkywalk Downgrade. Set the min kernel = 23.0.0 and Strategy to enable, and then enable
    6.5 go to boot-args and add amfi=0x80, go to csr-active-config and set the value to 03080000
    6.6 Reboot     
    6.7 Use the [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher/releases), go to Root Patching
    6.8 Done    


## BIOS Settings:
Access the bios, using DEL key during start
## Disable
  1. Go to advanded -> ACPI settings -> ACPI sleep state -> disable
  2. Go to advanded -> NCT55320 Super IO configuration -> Serial Port 1 -> serial port -> disable
  3. Go to advanded -> CSM Configuration -> video -> change to UEFI -> disable
  4. Reboot the machine
  5. Go to advanded -> CSM Configuration -> CSM Support -> disable
  6. IntelRCSetup -> Processor Configuration -> MSR Lock Control -> disable
  7. IntelRCSetup -> Processor Configuration -> Execute Disable Bit -> disable

 ## Enable
 1. Go to advanded -> USB Configuration -> XHCI Hand-off -> enable
 2. Go to advanded -> USB Configuration -> EHCI Hand-off -> enable
 3. InterRCSetup -> Processor Configuration -> Hyper Threading -> enable

## Thanks/Credits

- [Opencore Team](https://dortania.github.io/getting-started/)
- [BASE-EFI-INTEL-HEDT-4THGEN-X99-HASWELL-E](https://github.com/luchina-gabriel/BASE-EFI-INTEL-HEDT-4THGEN-X99-HASWELL-E)
- [Gabriel Luchina](https://github.com/luchina-gabriel)
- [vncsmnl](https://github.com/vncsmnl)

  
## Discord - Universo Hackintosh

- [Access Discord](https://discord.universohackintosh.com.br)

<div><img align="right" src="./Images/vncsmnl.gif" alt="signature" width="200"></div>
<div><img align="left" src="./Images/rate1_w.png" alt="like" width="80"></div>
