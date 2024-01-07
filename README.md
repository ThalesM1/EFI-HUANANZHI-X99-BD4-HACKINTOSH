# HUANANZHI X99 BD4 + Intel® Xeon® E5-2670 v3 + AMD Radeon™ RX 6600 + Fenvi T919


**Latest working macOS**: 14.2.1
<br>
**Current OpenCore**: 0.9.7

---

## Complete hardware specs

- Intel® Xeon® E5-2670 v3 (All cores activated)
- HUANANZHI X99 BD4 + Unlock Turbo Boost + Resizable Bar Activated
- AMD Radeon™ RX 6600
- 2x 16Gb DDR4 3200Mhz ECC Atermiter
- Wi-fi/Bluetooth replaced by Fenvi T919

## What works

- macOS Sonoma, Ventura, Big Sur, Catalina and macOS Monterey
- Audio
- HDMI/DP (in dGPU - Works OOB)
- All USB ports
- Everything iCloud related (Drive, iMessage, Facetime, unlock with Apple Watch, etc)
- Temperature monitoring for everything
- DRM content (Netflix, ATV+, Airplay 2 mirroring etc)
- Shutdown/Reboot/Update to newer macOS builds over time
- Resizable Bar ON (ResizeUsePciRbIo = true)
- Wi-fi/Bluetooth/AirDrop - OpenCore Legacy Patcher

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

## BIOS Settings:
## Disable
Fast Boot
Secure Boot
Serial/COM Port
Parallel Port
VT-d (can be enabled if you set DisableIoMapper to YES)
Compatibility Support Module (CSM).
Thunderbolt(For initial install, as Thunderbolt can cause issues if not setup correctly)
Intel SGX
Intel Platform Trust
CFG Lock (MSR 0xE2 write protection)
This must be off, if you can't find the option then ENABLE AppleXcpmCfgLock.
Your hack will not boot with CFG-Lock enabled.
For 10.10 and older, you'll need to ENABLE AppleCpuPmCfgLock as well.
## Enable
VT-x
Above 4G decoding.
This must be on, if you can't find the option then add npci=0x2000 to boot-args.
Do not have both this option and npci on boot-args enabled at the same time.
Hyper-Threading
Execute Disable Bit
EHCI/XHCI Hand-off
OS type: Windows 8.1/10 UEFI Mode
SATA Mode: AHCI

## Thanks/Credits

- [Opencore Team](https://dortania.github.io/getting-started/)
- [BASE-EFI-INTEL-HEDT-4THGEN-X99-HASWELL-E](https://github.com/luchina-gabriel/BASE-EFI-INTEL-HEDT-4THGEN-X99-HASWELL-E)
- [Gabriel Luchina](https://github.com/luchina-gabriel)
- [vncsmnl](https://github.com/vncsmnl)

  
## Discord - Universo Hackintosh

- [Access Discord](https://discord.universohackintosh.com.br)

<div><img align="right" src="./Images/vncsmnl.gif" alt="signature" width="200"></div>
<div><img align="left" src="./Images/rate1_w.png" alt="like" width="80"></div>
