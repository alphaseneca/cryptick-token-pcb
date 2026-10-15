# Cryptick Token Hardware PCB

[![Manufacturing Release](https://github.com/alphaseneca/cryptick-token-pcb/actions/workflows/release.yml/badge.svg)](https://github.com/alphaseneca/cryptick-token-pcb/actions/workflows/release.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![KiCad](https://img.shields.io/badge/EDA-KiCad%208.x-orange.svg)](https://www.kicad.org/)

Hardware schematics, 4-layer PCB layout, and manufacturing files for **Cryptick Token** — the 100% open-source biometric hardware security key and cryptographic hardware enclave.

---

## Hardware Highlights

- **Main Processing Unit**: Espressif ESP32-S3-WROOM-1 (N16R8) Dual-Core Xtensa LX7 @ 240 MHz with hardware cryptography accelerators (AES-256, SHA-256, RSA-3072, ECC point multiplication, TRNG) and 16 MB encrypted SPI Flash.
- **Biometric Security Enclave**: R558S optical/capacitive fingerprint sensor (508 DPI, 120 on-sensor template slots, hardware wake-on-touch interrupt on GPIO 16).
- **Physical WYSIWYS Display**: 0.96" 128x64 Monochrome OLED (SSD1306) on hardware I2C (Address 0x3C, SDA GPIO 8, SCL GPIO 9) for origin verification ("What You See Is What You Sign").
- **Physical Navigation**: 5-Way Tactile Navigation Switch (UP GPIO 7, DOWN GPIO 4, LEFT GPIO 6, RIGHT GPIO 5, CENTER GPIO 15) for tactile PIN entry, menu navigation, and physical user presence (UP) confirmation.
- **Wireless & Wired Interfaces**:
  - Bluetooth Low Energy (BLE 5.0) via onboard 2.4 GHz PCB antenna.
  - Native USB Type-C Receptacle (USB 2.0 Full-Speed OTG) with bidirectional TVS diode ESD protection (USBLC6-2SC6).
- **Power Management**:
  - TP4056 / BQ24040 LiPo/Li-Ion linear battery charge management with dual status monitoring (STAT1 GPIO 38, STAT2 GPIO 39).
  - High-efficiency 3.3V LDO regulator with low quiescent current for ultra-deep sleep.
  - WS2812B Addressable RGB Neopixel LED on GPIO 48 for device status.

---

## PCB Specifications

| Parameter | Specification |
| :--- | :--- |
| **Dimensions** | 56.0 mm × 24.0 mm × 1.6 mm |
| **Layer Count** | 4 Layers (Signal / GND Plane / 3.3V Power Plane / Signal) |
| **Copper Weight** | 1 oz Outer, 1 oz Inner |
| **Min Trace / Space** | 0.127 mm / 0.127 mm (5/5 mil) |
| **Surface Finish** | ENIG (Electroless Nickel Immersion Gold) - RoHS compliant |
| **Solder Mask** | Matte Black with Gold Traces |
| **Silkscreen** | High-definition White |
| **Design Rules** | JLCPCB 4-Layer Standard Impedance (JLC04161H-7628) |

---

## Schematic & Manufacturing Files

- Schematic source: `cryptick-token-pcb.kicad_sch`
- Board layout: `cryptick-token-pcb.kicad_pcb`
- KiCad project: `cryptick-token-pcb.kicad_pro`
- Automated releases produce:
  - Gerber RS-274X drill and layer files (`gerbers.zip`)
  - Bill of Materials (BOM) in JLCPCB SMT format (`bom.csv`)
  - Pick and Place Component Centroid coordinates (`pos.csv`)

---

## Automated Tag Release

Pushing any semantic version tag (e.g. `v0.1.0`) triggers `.github/workflows/release.yml`, executing [KiForge](https://github.com/alphaseneca/kiforge) in CI to automatically generate and attach production fabrication assets to GitHub Releases.

---

## Part of the Cryptick Token Ecosystem

- [Main Consolidated Repository](https://github.com/alphaseneca/cryptick-token)
- [Firmware & Core Logic](https://github.com/alphaseneca/cryptick-token-code)
- [Host Daemon, CLI & SmartCard PIV](https://github.com/alphaseneca/cryptick-token-daemon)
- [Browser Extension](https://github.com/alphaseneca/cryptick-token-extension)

---

## License

Hardware schematics and PCB designs are licensed under the [MIT License](LICENSE) / CERN Open Hardware Licence.