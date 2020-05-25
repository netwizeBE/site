---
title: "Hardware"
permalink: /docs/structure/
excerpt: "How the theme is organized and what all of the files are for."
toc: true
---

There is support for the ESP8266, ESP32 and STM32F4 families of MCUs.
Hasp-lvgl needs a compatible micro-controller with drivers supporting the attached display, touch controller, storage and network.

Due to the large number of possible hardware options, a selection of recommended hardware has been made for the pre-built binaries.

**Please note:** The recommended hardware configurations have pre-built binaries available.
Advanced users can build and compile their own configurations in PlatformIO, however this is not recommended or supported.
{: .notice--info}

To use PWM dimming, solder the TFT-LED pin to either D1, D2 or D4. **D4 is recommended** for Backlight control, as this leaves D1 and D2 available as GPIOs.

![TFT-LED PWM dimming](https://github.com/fvanroie/hasp-lvgl/blob/master/docs/img/tft-led-pwm.png)

**Warning** Do *not* use D3 because it is already in use for touch.
{: .notice--warning}

## Recommended Display
### Lolin TFT 2.4"

This is the development display of choice. It has a 320x240 ILI9341 touchscreen and supports backlight dimming via PWM. The touchcontroller is a XPT2046 Resistive Touch driver. Also it is quite cheap to get.

The Lolin TFT 2.4" is **plug-and-play** with the recommended MCU's. If you have another MCU, you can still use this display using jumper cables. Or you can solder a row of headers at the bottom of the display to plug it into a breadboard.

## Recommended MCU's
### ESP32

The ESP32 is a small but powerfull microcontroller with 320KB of memory and a minimum of 4MB of flash.
The available SPI bus is fast enough to drive the 240x320 pixel display.

Lolin TFT 2.4" is **plug-and-play** with:
- Wemos D1 Mini ESP32 *(**only** solder the inner row of the pinheaders)*
- TTGO T7 V1.3 MINI32 ESP32 (Rev1)  *(**only** solder the inner row of the pinheaders)*
- LOLIN D32 Pro V2.0.0 *using an **additional** TFT cable*

### ESP8266

The D1 mini is a popular budget MCU used in many other projects. It can be used, but it is noticably slower then the ESP32.
The ESP8266 only has 80KB of memory, so it is only suitable for simple UI projects.

- Wemos D1 Mini
- Lolin D1 Mini Pro V2.0.0

## Alternative hardware

### SPI Displays
- ILI9341 320x240 4-wire SPI Touch Screen:
    - Lolin TFT 2.4 Touch Shield [aliexpress][3]
    - 2.4" (SKU MSP2402) [aliexpress][4]
    - 2.8" (SKU MSP2807)
    - 3.2" (SKU MSP3218)
    
with
- XPT2046 Resistive Touch driver

### STM32F407 Combo

- STM32F407VET6 + 3.2" ili9341 FSMC display
- STM32F407ZET6 + 3.2" ili9341 FSMC display
- STM32F407ZGT6 + 3.2" ili9341 FSMC display


**Note** The STM32F4xx development boards do not have onboard network connectivity.
{: .notice--info}


