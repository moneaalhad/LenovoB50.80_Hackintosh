# Lenovo B50-80 Hackintosh (Lenovo 80EW)

This EFI folder comes with absolutely no warranty - use at your own risk. I've removed my system's serial number and MLB settings, so you will need to add those in order to install macOS. See CorpNewt's GenSMBIOS on how to do that - https://github.com/corpnewt/GenSMBIOS.

## Specifications
1. 5th Generation Dual-Core Intel i3-5005U, 1.9 GHz (Configured to 0.8 GHz idle, 1.9 GHz Max)
2. Intel HD 5500 Graphics, Integrated, 1536 MB VRAM
3. 12 GB DDR3 Memory (upgraded from 4 GB in-built)
4. Intel Dual-Band Wireless AC 3160, 2.4 + 5.0
5. Realtek SD Card Reader (may or may not work) 
6. Realtek Wildcat-Point LP Sound Controller, based on codec ALC233
7. Realtek RTL8111 Ehernet (RJ45)
8. Crucial 480 GB SATA SSD, CT480BX500SSD1, Internal (upgraded from 1 TB SATA HDD, WD-Blue, in-built)
9. ELAN Synaptics Pointing Device (Trackpad)
10. Fingerprint Scanner (doesn't work in macOS, no way to emulate T2 Security Chip)

![About This Mac](https://user-images.githubusercontent.com/90323866/143816309-45de882f-ed23-43bb-8cf0-706fcb130ff1.png)


## What Works:
1. Wireless: Connecting to internet services and keyboards/mice works well. There may be some minor issues with Airportitlwm or itlwm, but so far they can be fixed by a system restart. Mobile Hotspot and Internet Sharing won't work, don't bother with it - this is because Airportitlwm is reverse-engineered based on patched Apple .kexts and generic ID is spoofed to prevent kernel panics.
2. Partial Hardware Acceleration: DRM-Based services like Netflix and Apple TV are a huge IF, but sometimes work. Safari's YouTube and video playback, Chess, Final Cut Pro and Premiere Pro work flawlessly - refer WhateverGreen's FB Patching guide for more
3. TRIM is enabled: Startup time was 18 seconds at last count.
4. Sound works fully, with native AppleALC.kext. Use `device-id` 11 or set `alcid=11` in boot-args, requires SSDT-HPET in OC/ACPI for Big Sur 11.3+
5. Power Management: X86_PlatformPlugin is loaded, and CPUFriendFriend works. Idle clock is set to 0.8 GHz with max clock 1.9 GHz. EPP is set to 15
6. All USB Ports + HDMI Port + VGA Port + Microphone + Internal Speakers + Webcam (only with MacBookAir7,2 SMBIOS or MacBookPro SMBIOS, MacBook's SMBIOS will NOT work)
7. Battery Readout - I'm not convinced this is 100% accurate but go for it
8. Trackpad (some gestures)

## What doesn't work
1. Sleep - this is the most disappointing of them all - sleeping will cause kernel panics. I've tried USB Mapping, NVRAM emulation, power management, NIC management and even LidWake.kext - nothing works. If you can get it working, feel free to DM me on Reddit
2. Continuity and Handoff - AirDrop doesn't work. Your other iDevices will show up, and so will the MacBook Air, but no files will be shared
3. LidSleep / LidWake - see above, doesn't work
4. Touch Sensor - this is a hardware problem, will NOT be fixed
5. Sidecar - the 5th Gen Processors do not have H.265 Decode-Encode so Sidecar requires a cable. Moreover the picture will be distorted and bleed horribly; not recommended at all.

## Remember to add your Serial Number, MLB, ROM, UUID and SMBIOS!
If you try to boot using the stock EFI folder, you will not be able to. Feel free to try. 

As mentioned above, use CorpNewt's GenSMBIOS to add a suitable SMBIOS.

[Wallpaper Link](https://github.com/moneaalhad/LenovoB50.80_Hackintosh/files/7615976/iOS.13.png.zip)
