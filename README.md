# Opencore-i5-11400F-RX6600XT
Hackintoshing my friends' PC with an i5-11400F, RX 6600 XT, Z490 Gaming Edge WiFi, 32GB G.Skill RAM. → Goal: macOS Ventura
[Reddit Post](https://www.reddit.com/r/hackintosh/comments/wfdymc/success_monterey_on_i5_11400f_msi_z490_mpg_edge/)

Opencore config for my PC.
- Current OC version: 0.9.7
- Current macOS Version: 13.5.2

### Hardware
- CPU: Intel Core i5-11400F
    - Cpu1Data: <EA060900 00000000 00000000 00000000>
    - Cpu1Mask: <FFFFFFFF 00000000 00000000 00000000>
- GPU: RX 6600 XT
- Mainboard: MSI MPG Z490 Gaming Edge WiFi
- RAM: 32GB G.Skill RipJaws V DDR4-3600
- Power: System Power 9 CM 700W
- Case: Kolink Void RGB weiß
- SSD: Samsung SSD 860 EVO 500GB, M.2


### Benchmarks
- [Geekbench 5](https://browser.geekbench.com/v5/cpu/16321404)
- Cinebench R23: 1383 (S) 9652 (M)
- Geekbench 5 OpenCL: 69523
- Geekbench 5 Metal: 84592
- 3DMark Time Spy: 9080

### Installation
1. Download the latest release
2. Download propertree and edit EFI/OC/config.plist
    1. Change PlatformInfo -> MLB, ROM, SystemUUID and SystemSerialNumber using [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
3. Create the macOS Installer USB-Stick using [this](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) guide. You don't need to create the EFI, that work have I done already. 
4. Update the BIOS settings according to [this](https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html#intel-bios-settings) guide. 
5. Insert USB and boot! When entering the macOS Recovery, click Disk Utility, format your Disk as APFS/GUID and then install macOS on your disk.
6. For dual-booting on one disk, follow the dortania guide.

### Working
- iServices
- WiFi
- Ethernet
- Davinci Resolve
- Audio (over USB, didn’t test the headphone-jack)
- GPU Acceleration
- AirDrop, all Continuity features
- USB Ports (only on the back, I had to remove the USB-Header cable for the io-panel to get bluetooth working)
- Shutdown and Restart
- CPU temp
- Xcode
- Magic Keyboard and Mouse working in Bios, Windows and macOS without reconnecting (used a native apple-wifi-card and connected it in macOS, didn’t have to install bootcamp but wasn’t allowed to install the bluetooth driver)


### Not working
- Sidecar because unsupported iGPU on AMD (or no iGPU found)
- AirDrop, some Continuity features (because of non-native Intel-WiFi)

### Fixed bugs
- Bluetooth
