---
name: hardware-iot-ics-security
description: Hardware, IoT, Embedded, ICS/SCADA, Vehicle, and Drone Security auditing skill distilled from Awesome-Hacking (Embedded and IoT Security, ICS Security, Vehicle Security, Drone Hacking). Use when analyzing firmware, UART/JTAG interfaces, or industrial/automotive protocols.
---

# Hardware, IoT, ICS/SCADA & Vehicle Security

> [!CAUTION]
> **Safety First:** ICS/SCADA, tibbiy qurilmalar va avtomobil tizimlarida faqat laboratoriya (offline/testbench) sharoitida test o'tkazing.

## 1. Firmware Extraction & Analysis
```bash
# Firmware faylini ochish va ichki fayl tizimini (SquashFS/JFFS2) ajratib olish
binwalk -e firmware.bin
# Ichki fayllarda hardcoded parol va private keylarni qidirish
grep -rnE "(password|secret|BEGIN RSA PRIVATE KEY)" _firmware.bin.extracted/
```
- **Emulation:** `Firmadyne` yoki `QEMU` yordamida firmware ni virtual muhitda ishga tushirib, web-interfeysini tekshirish.

## 2. Hardware Interfaces & Protocols
- **UART / JTAG / SPI:** Serial konsolga ulanish (`minicom`, `screen`), root shell ochiq qolganini va bootloader (U-Boot) himoyasini tekshirish.
- **IoT Protocols:** MQTT (autentifikatsiyasiz brokerlar), CoAP, Zigbee va BLE (GATT) zaifliklari.

## 3. ICS/SCADA & Vehicle (CAN-Bus)
- **ICS/SCADA:** Modbus, DNP3, S7comm protokollarida shifrlash va autentifikatsiya yo'qligini hisobga olib, tarmoq segmentatsiyasini (Purdue Model) tekshirish.
- **Vehicle:** `can-utils` (`candump`, `cansend`) orqali CAN-bus trafikini tahlil qilish.
