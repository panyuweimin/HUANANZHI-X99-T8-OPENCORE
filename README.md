# HUANANZHI X99-T8 + Intel® Xeon® E5-2696 v3 + 256GB RAM + AMD Radeon™ RX 580 + BCM943602CS


**Latest working macOS**: Ventura 13.6.1 (Sonoma 14.1 works without Wifi/BT) 
<br>
**Current OpenCore**: 0.9.5

---

## Hardware Specs

- Intel® Xeon® E5-2696 v3 18 Cores 36 Threads
- HUANANZHI X99-T8 (2021 revised version) + Unlock Turbo Boost + Resizable Bar Activated + Apple Boot Logo
- AMD Radeon™ RX 580
- 256GB RAM 8x 32Gb DDR3 CL9 1333Mhz ECC Hynix 4Rx4 
- Wifi/BT BCM934602CS with A/E Key adapter

## What Works

- Ventura works perfectly, Sonoma and Monterey can install but haven't tested, no native WiFi in Sonoma
- Onboard Audio
- HDMI/DP from RX580, HDMI audio works but not from DP
- All USB ports
- Everything iCloud related
- DRM content
- Shutdown/Reboot/Update to newer macOS builds over time
- Resizable Bar Activated for Windows
- Wifi/BT, continuity features
- FileVault
- Sleep

## Kexts Used:

- AppleALC.kext 1.8.6
- CpuTscSync.kext 1.1.0
- Lilu.kext 1.6.7
- NVMeFix.kext 1.1.1
- RealtekRTL8111.kext 2.4.2
- RadeonBoost.kext
- SMCSuperIO.kext 1.3.2
- SMCProcessor.kext 1.3.2
- USBPorts.kext
- VirtualSMC.kext 1.3.2
- WhateverGreen.kext 1.6.6
- XHCI-unsupported.kext

## Hardware Preparation

- X99-T8 was from Sep 2023, Nuvoton nct5567D-B and Winbond W25Q128JVSQ, factory BIOS 2022-10-29
- Flash the included modified BIOS to boot installer, none of the other BIOS version works
- Modified BIOS based on Koshak1013 X99-F8 2020-05-25 BIOS v11:
  - Based on 2020-05-25 X99-F8 board
  - Nuvoton 5567D-B controller suitable
  - ALC codec
  - ECC works
  - No beeps
  - All core turbo unlocked with 60/60 offset
  - ResizableBar support
  - Custom Apple logo instead of Huananzhi logo, correct resolution in HDMI monitor
- BIOS settings:
  - CSM => Disable (first change Video to UEFI, then reboot to disable CSM)
  - EHCI/XHCI => Enable
  - VT-d => Disable
  - Above 4G Encoding => Enable
  - Serial/COM Port => Disable
  - Chipset Lock/MSR Lock => Disable
- To active Resizeable Bar in Windows, run RebarState.ext in admin mode, enter 32 and restart

## OpenCore Features

- MacPro7,1 SMBIOS
- Power Management
- Custom compiled SSDT
- USB mapped manually, two front USB 3.0 ports are not mapped
- Bootpicker
- Start-up Chime
- FileVault enabled
- Support Windows Resizeable Bar (ResizeAppleGpuBars = 0, ResizeUsePciRbIo = True)
- Custom Memory Profile

## OpenCore Preparation

- Build your own OpenCore EFI folder based on the uploaded files
- Generate your own series numbers using GenSMBIOS
- Post-install, update custom memory profiles and set CustomMemory = true OR use RestrictEvents.kext for memory profile error notification


## Thanks/Credits

- [Opencore Team](https://dortania.github.io/getting-started/)
- [Koshak1013](https://github.com/Koshak1013/HuananzhiX99_BIOS_mods/tree/master/Huananzhi%20X99-F8/2020-05-25%20(%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D1%82%D1%81%D1%8F))
- [Xeon e5450](https://xeon-e5450.ru/socket-2011-3/huananzhi-x99-t8/)
- [xCuri0 ReBarUEFI](https://github.com/xCuri0/ReBarUEFI)




