---
title: "Installation"
permalink: /docs/installation/
excerpt: "Instructions for installing the theme for new and existing Jekyll based sites."
last_modified_at: 2020-05-08T22:03:18+01:00
toc: true
---

## Download the firmware

Go to the releases page on Github to download the latest hasp-lvgl binaries.

There are 3 download options, pick the one appropriate for your hardware:
- hasp-lvgl-0.2.0-esp32_lolin_2.4_spi.bin
- hasp-lvgl-0.2.0-esp8266_lolin_2.4_spi.bin
- hasp-lvgl-0.2.0-stm32f407_devEbox_3.2_ili9341_fsmc.bin

[<i class="fas fa-download"></i> Hasp-lvgl Releases](https://github.com/fvanroie/hasp-lvgl/releases){: .btn .btn--info}


## Install the firmware

### ESP8266 or ESP32

#### Using Tasmotizer (Windows)

#### Using esp-tool.py

```
esptool.py --port /dev/ttyUSB0 write_flash --flash_mode qio --flash_size 4m 0x0 hasp-lvgl-0.2.0-esp32_lolin_2.4_spi.bin
```

### STM32F407 devEbox

#### Using Serial

- Connect your serial TTL adapter RX and TX pins to PA9 and PA10 of the devEbox.
- Place the boot jumpers into programming mode
- Reset the board.
- Upload the firmware using:

#### Using DFU (USB)

#### Using ST Link (USB)

- Install ST Link software
- Connect the devEbox using the USB port
- Launch ST Link
- Select the hasp-lvgl-0.2.0-stm32f407_devEbox_3.2_ili9341_fsmc.bin file
- Flash the firmware to the board