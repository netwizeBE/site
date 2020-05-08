---
title: "Hardware"
permalink: /docs/structure/
excerpt: "How the theme is organized and what all of the files are for."
last_modified_at: 2018-03-20T15:19:22-04:00
classes: wide
---

There is support for the ESP8266, ESP32 and STM32F4 families of MCUs.
Hasp-lvgl needs a compatible micro-controller with drivers supporting the attached hardware: display, touch controller, storage and network.


## Recommended hardware

### Display: Lolin TFT 2.4"

This is the development display of choice. It has a 320x240 ILI9341 touchscreen and supports backlight dimming via PWM. The touchcontroller is a XPT2046 Resistive Touch driver. Also it is quite cheap to get.

### MCU

The screen is **plug-and-play** with these MCU's:
- ESP8266:
    - Wemos D1 Mini
    - Lolin D1 Mini Pro V2.0.0
- ESP32: 
    - Wemos D1 Mini ESP32 *(**only** solder the inner row of the pinheaders)*
    - TTGO T7 V1.3 MINI32 ESP32 (Rev1)  *(**only** solder the inner row of the pinheaders)*
    - LOLIN D32 Pro V2.0.0 *using an **additional** TFT cable*

To use PWM dimming, solder the TFT-LED pin to either D1, D2 or D4. **D4 is recommended** for Backlight control, as this leaves D1 and D2 available as GPIOs.

![TFT-LED PWM dimming](https://github.com/fvanroie/hasp-lvgl/blob/master/docs/img/tft-led-pwm.png)

**Warning** Do *not* use D3 because it is already in use for touch.
{: .notice--warning}

If you have another MCU, you can still use this display using jumper cables. Or you can solder a row of headers at the bottom of the display to plug it into a breadboard.

**Please note:** These are supported hardware configurations for which there are binaries available. You can build and compile your own configurations in PlatformIO, however this is not recommended or supported.
{: .notice--info}

## Compatible hardware

### SPI Displays
- ILI9341 320x240 4-wire SPI Touch Screen:
    - Lolin TFT 2.4 Touch Shield [aliexpress][3]
    - 2.4" (SKU MSP2402) [aliexpress][4]
    - 2.8" (SKU MSP2807)
    - 3.2" (SKU MSP3218)
    
with
- XPT2046 Resistive Touch driver