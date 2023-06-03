# Opencore Ryzen 5 5600G, ASRock B450
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
