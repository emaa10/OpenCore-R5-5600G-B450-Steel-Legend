# Opencore Ryzen 5 5600G, ASRock B450
Current OC Version: v0.9.4
Current macOS Version: 13.5
## Hardware
- CPU: Ryzen 5 5600G
- GPU: MSI RX 6600
- Mainboard: ASRock B450 Steel Legend
    - Ethernet: Realtek RTL8111H
    - Audio: ALC892, 0x100302, layout 1, 2, 3, 4, 5, 7, 12, 15, 16, 17, 18, 20, 22, 23, 28, 31, 32, 90, 92, 97, 99, 100
- RAM: Crucial Dual Channel (16GB)
- SSD: Intenso 500GB Sata3
- Power supply: Be quiet! Power 9 650 Watt
- Wifi / BT: Ubit WiFi 6 AX200 (using Airportitlwm.kext and IntelBluetoothFirmware)

## Setup OpenCore
1. Change SMBios using [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) (I used MacPro7,1 because of Navi 21 GPU)
    1. change MLB, SystemSerialNumber, ROM and SystemUUID
2. Update kexts to your needs ([Guide](https://dortania.github.io/OpenCore-Install-Guide/ktext.html))
3. Update config.plist using Propertree (⌘ + Shift + R)
4. If running into problems, add `-v` to your boot-args to display log on screen

## Current Problems
- ~~GPU displays image only after ~5 minute~~
    ->  fixed by adding `-wegnoigpu` boot arg
- ~~Apple ID not working (Connectivity error)~~
    -> fixed by adding `PciRoot(0x0)/Pci(0x2,0x1)/Pci(0x0,0x2)/Pci(0x4,0x0)/Pci(0x0,0x0)` DeviceProperty entry to mark en0 as builtin (read the [dortania guide](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#fixing-en0) for a how-to)

## What's working?
- Shutdown
- Restart
- GPU acceleration
- WiFi (only through itlwm.kext, otherwill willl result in random kernel panics)
- Apple ID (requires en0 to be marked as built-in, see the dortania guide if you run into problems)
- Dual boot with windows
