# Hackintosh Configuration: AMD Ryzen 5 5600X on ASUS Prime A320M-K
**macOS Version**: 15 Sequoia  
**Status**: Fully Functional ✅  

## System Specifications

### Motherboard
| Property       | Value                  |
|----------------|------------------------|
| Model          | ASUSTEK PRIME A320M-K |
| Chipset        | A320                  |
| Platform       | Desktop               |

### BIOS
| Property        | Value               |
|-----------------|---------------------|
| Version         | 6210                |
| Release Date    | 2023-09-04         |
| System Type     | x64-based           |
| Firmware Type   | UEFI                |
| Secure Boot     | Enabled             |

### Processor
| Property          | Value                                  |
|-------------------|----------------------------------------|
| Manufacturer      | AMD                                    |
| Model             | Ryzen 5 5600X 6-Core Processor        |
| Codename          | Vermeer                                |
| Core Count        | 6                                      |
| SIMD Features     | SSE, SSE2, SSE3, SSSE3, SSE4.1, SSE4.2, SSE4a, AVX, AVX2 |

### Graphics
| Property          | Value                          |
|-------------------|--------------------------------|
| Model             | AMD Radeon RX 580 2048SP      |
| Codename          | Polaris 20                     |
| Device ID         | 1002-6FDF                      |
| PCI Path          | PciRoot(0x0)/Pci(0x3,0x1)/Pci(0x0,0x0) |
| Resizable BAR     | Disabled                       |

### Display
| Model         | Resolution    | Connector | Connected GPU          |
|---------------|---------------|-----------|------------------------|
| LEN D186wA    | 1366x768      | HDMI      | AMD Radeon RX 580 2048SP |

### Storage
**Controller**: A320 Chipset SATA Controller [AHCI mode]  
**Drives**:
- KINGSTON SA400S37480G (480GB SSD)
- WDC WD5000AAKX-083CA1 (500GB HDD)

### Network
| Component                       | Device ID  | Connection Path                          |
|---------------------------------|------------|------------------------------------------|
| Realtek PCIe GbE Family Controller | 10EC-8168 | PciRoot(0x0)/Pci(0x1,0x3)/Pci(0x0,0x2)/Pci(0x6,0x0)/Pci(0x0,0x0) |

### Audio Devices
1. **AMD High Definition Audio Device**  
   - Endpoints: DisplayPort Audio (LEN D186wA)
   
2. **USB Audio Device**  
   - Endpoints: Speakers, Microphone

3. **Realtek High Definition Audio**  
   - Endpoints: Analog Speakers, Digital Output

### USB Controllers
1. **AMD USB 3.10 eXtensible Host Controller**  
   - Device ID: 1022-43BC  
   - Path: `\_SB.PCI0.GPP2.PTXH`

2. **AMD USB 3.10 eXtensible Host Controller #2**  
   - Device ID: 1022-149C  
   - Path: `\_SB.PCI0.GP13.XHC0`

### Input Devices
- USB Input Device (0D8C-0012)
- USB Input Device (1A2C-4C5E)
- 2.4Ghz wireless optical mouse (1D57-130F)
- Dell MS116 Optical Mouse (413C-301A)

### Bluetooth
Generic Bluetooth Radio (0A12-0001)

## Key Notes
1. **GPU Compatibility**: RX 580 works OOB with WhateverGreen
2. **Network**: Realtek RTL8168 requires [LucyRTL8125Ethernet](https://github.com/Mieze/LucyRTL8125Ethernet) kext
3. **Audio**: Layout ID `1` used for Realtek ALC887
4. **SMBIOS**: iMacPro1,1 used for AMD compatibility
5. **Secure Boot**: Disabled in BIOS for OpenCore

## Working Features
- Graphics Acceleration (QE/CI)
- Ethernet
- Audio (All outputs)
- USB Ports (Mapped)
- Sleep/Wake
- iCloud Services
- Bluetooth

## Bootloader
- OpenCore 1.0.0
- AMD Kernel Patches
- Required Kexts:
  - Lilu
  - WhateverGreen
  - VirtualSMC
  - LucyRTL8125Ethernet
  - AppleALC
