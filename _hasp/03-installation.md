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
- d1_mini_esp32_lolin_2.4_spi.bin
- d1_mini_esp8266_lolin_2.4_spi.bin
- stm32f407_devEbox_3.2_ili9341_fsmc.bin

[<i class="fas fa-download"></i> Hasp-lvgl Releases](https://github.com/fvanroie/hasp-lvgl/releases){: .btn .btn--info}

**Note:** The theme uses the [jekyll-include-cache](https://github.com/benbalter/jekyll-include-cache) plugin which will need to be installed in your `Gemfile` and added to the `plugins` array of `_config.yml`. Otherwise you'll throw `Unknown tag 'include_cached'` errors at build.
{: .notice--warning}

## Install the firmware

### ESP8266 or ESP32

#### Using Tasmotizer (Windows)

#### Using esp-tool.py

**Post/Page Settings**: Be sure to read through the "Working with..." documentation to learn about all the options available to you. The theme has been designed to be flexible --- with numerous settings for each.
{: .notice--info}

### STM32F407 devEbox

#### Using Serial

#### Using DFU (USB)

#### Using ST Link (USB)
