# ESP8266 WiFi Development Board

A custom ESP8266-based WiFi development board designed in KiCad 8, featuring onboard USB-to-serial, 3.3V regulation, and a breadboard-friendly pinout — perfect for IoT prototyping.

---

## Features
- ESP8266 (ESP-12E/F module) WiFi MCU
- Onboard USB-to-Serial (CH340G)
- 3.3V LDO regulator (AMS1117-3.3)
- Auto-reset circuit for one-click flashing
- All GPIO pins broken out to 2.54mm headers
- Flash and Reset buttons onboard
- Power LED and user LED (GPIO2)

## Specifications

| Parameter | Value |
|-----------|-------|
| Module | ESP-12E / ESP-12F |
| MCU | Tensilica L106 (32-bit) |
| Clock Speed | 80MHz / 160MHz |
| WiFi | 802.11 b/g/n (2.4GHz) |
| Operating Voltage | 3.3V |
| USB Input | 5V via Micro USB |
| Flash Memory | 4MB |
| GPIO Pins | 11 usable |
| PCB Layers | 2 |
| Designed With | KiCad 8 |

## Project Structure

```
├── Schematic/       # KiCad schematic (.kicad_sch, PDF)
├── PCB/             # PCB layout (.kicad_pcb, .kicad_pro)
├── Gerbers/         # Fabrication files
├── BOM/             # Bill of materials (CSV)
├── 3D/              # 3D model (.step)
└── Images/          # PCB renders and schematic screenshots
```

## How It Works

The CH340G converts USB to UART for programming. The auto-reset circuit uses transistors on the DTR/RTS lines to automatically pull GPIO0 LOW and reset the ESP8266 before flashing — no manual button pressing needed.

## Programming

1. Install the ESP8266 board in Arduino IDE via Boards Manager
2. Select **Generic ESP8266 Module** or **NodeMCU 1.0**
3. Connect via Micro USB and select the correct COM port
4. Upload directly — auto-reset handles the rest

## Bill of Materials (Summary)

| Component | Value | Qty |
|-----------|-------|-----|
| WiFi Module | ESP-12F | 1 |
| USB-Serial IC | CH340G | 1 |
| LDO Regulator | AMS1117-3.3V | 1 |
| Capacitors | 100nF, 10µF | 4 |
| Transistors | BC817 | 2 |
| Buttons | Tactile | 2 |
| USB Connector | Micro-B | 1 |

## Fabrication

Gerber files are in `/Gerbers`, ready for JLCPCB, PCBWay, or similar.

## License

This project is licensed under the [CERN Open Hardware Licence Version 2 - Strongly Reciprocal (CERN OHL-S v2)](https://ohwr.org/cern_ohl_s_v2.txt).

## Author

**Abhi90808** — [GitHub Profile](https://github.com/Abhi90808)
