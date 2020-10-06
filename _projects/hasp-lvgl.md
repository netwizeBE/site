---
title: "HASP-lvgl"
excerpt: "HomeAutomation Switchplate based on LittlevGL"
permalink: /hasp-lvgl/
header:
  image: /assets/images/hasp/header.png
  teaser: /assets/images/hasp/header-small.png
sidebar:
  - nav: "hasp"
gallery:
  - url: https://raw.githubusercontent.com/fvanroie/hasp-lvgl/0.0.11/docs/img/sliders.png
    image_path: https://raw.githubusercontent.com/fvanroie/hasp-lvgl/0.0.11/docs/img/sliders.png
    alt: "placeholder image 1"
  - url: https://raw.githubusercontent.com/fvanroie/hasp-lvgl/0.0.11/docs/img/buttons.png
    image_path: https://raw.githubusercontent.com/fvanroie/hasp-lvgl/0.0.11/docs/img/buttons.png
    alt: "placeholder image 2"
  - url: https://raw.githubusercontent.com/fvanroie/hasp-lvgl/0.0.11/docs/img/mediaplayer.png
    image_path: https://raw.githubusercontent.com/fvanroie/hasp-lvgl/0.0.11/docs/img/mediaplayer.png
    alt: "placeholder image 3"
classes: wide
---

This project is a re-implementation of the popular HASwitchPlate sketch created by aderusha.
The [original HASwitchPlate][1] project uses a Wemos D1 mini and requires a Nextion/TJC HMI display.
This rewrite removes the Nextion/TJC requirement by running the [Light and Versatile Graphics Library][2]
on the MCU to drive a cheap commodity display.

This version also adds ESP32 and STM32 support to take advantage of the additional hardware capabilities.


## Demo Screens
{% include gallery caption="This is a sample of controls that can are available to use." %}

## Features

| Feature                 | ESP8266 | ESP32   | STM32F4
|-------------------------|---------|---------|----------
| SPI display             | ✅ yes | ✅ yes | ✅ yes
| Parallel display        | ❌ no  | ✅ yes | ✅ yes
| PWM Screen dimming      | ✅ yes | ✅ yes | ✅ yes
| Maximum Page Count      | 4       | 12 | 12
| Object Types / Widgets  | 14      | 15 | 15
| Dynamic Objects         | ✅ yes | ✅ yes | ✅ yes
| [Lvgl Theme Support][3] | basic only | all themes | tbd
| [Custom .zi V5 font][4] | ✅ yes (latin1) | ✅ yes (latin1) | no
| [FontAwesome Icons][5]  | ✅ 1300+ | ✅ 1300+ | no
| PNG images              | ❌ no | ❔ tbd | ❔ tbd 
| Network                 | 📶 Wifi | 📶 Wifi | ✅ Ethernet

## Getting Started

Check out the [Quick-Start Guide](../projects/hasp-lvgl/hardware/) for information, how-to's, examples and frequently asked questions.

Join the [Discord channel][6] to chat with other users and developers.
  <a href="https://discord.gg/VCWyuhF" class="btn btn--discord"><i class="fab fa-fw fa-discord" aria-hidden="true"></i><span> Join Discord Channel</span></a>


[1]: https://github.com/aderusha/HASwitchPlate
[2]: https://lvgl.io/
[3]: https://littlevgl.com/themes
[4]: https://github.com/fvanroie/HMI-Font-Pack/releases
[5]: https://fontawesome.com/cheatsheet/
[6]: https://discord.gg/VCWyuhF