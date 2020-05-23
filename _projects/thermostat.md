---
title: "OpenThermostat"
excerpt: "Open Hardware, Open Source 5-wire room thermostat."
categories:
- Electronics
tags:
- Home Electronics
- SMD Soldering
header:
  image: /assets/images/foo-bar-identity.jpg
  teaser: /assets/images/2020/thermostat-render.png
sidebar:
  - title: "3D Render"
    image: /assets/images/2020/thermostat-render.png
    image_alt: "logo"
    text: "Designer, Front-End Developer"
  - title: "Responsibilities"
    text: "Reuters try PR stupid commenters should isn't a business model"
gallery:
  - url: /assets/images/2020/20191027_190728.jpg
    image_path: /assets/images/2020/20191027_190728.jpg
    alt: "placeholder image 1"
  - url: /assets/images/2020/20191027_191925.jpg
    image_path: /assets/images/2020/20191027_191925.jpg
    alt: "placeholder image 2"
  - url: /assets/images/2020/20191028_003811.jpg
    image_path: /assets/images/2020/20191028_003811.jpg
    alt: "placeholder image 3"
classes: wide
mathjax: true
---

This build is an Open Thermostat for a 5-wire HVAC system. It requires 12-24V AC/DC input. It can operate
3 relays operating from this same power source to control Heat, Venticaltion and Cooling.

This thermostat uses an ESP32 as MCU, a commodity 3.5" or 4.0" touchscreen.

The interface will be implemented in Arduino and also use LittlevGL.
The firmware will also be open sourced once the project is tested and working properly.

## Demo Screens
{% include gallery caption="This is a sample gallery to go along with this case study." %}

Schematic
---------

{% include figure image_path="/assets/images/2020/thermostat-schematic.png" alt="Thermostat Schematic" caption="Conceptual design." %}

Bill of Materials
-----------------

### Power Circuit

{:class="table table-bordered"}
| Qty | Description                                                            | Footprint                  | Supplier |
|----:|------------------------------------------------------------------------|----------------------------|----------|
| Power Supply                                                                                                      ||||
|  1  | MB1S Bridge Rectifier 100V 0.5A                                        | SOIC-4                     | [AliExpress]()
|  1  | Capactitor                                                             | 6.3 x 7.7mm                | [AliExpress]()
|  1  | MC34063AD                                                              | SOIC-8 3.9x4.9mm P1.27mm   | [AliExpress]()
|  1  | Capacitor                                                              | 6.3 x 5.4mm                | [AliExpress]()
|  1  | Capacitor                                                              |                            | [AliExpress]()
|  1  | Resistor                                                               |                            | [AliExpress]()
|  1  | Resistor                                                               |                            | [AliExpress]()
|  1  | Resistor                                                               |                            | [AliExpress]()
|----:|-----------------------------------------------------------------------------------------------------|----------|
| Microcontroller                                                                                                   ||||
|----:|------------------------------------------------------------------------|----------------------------|----------|
|  1  | ESP-32 Wroom                                                           |                            | [AliExpress]()
|  1  | AMS 117-3.3V Voltage Regulator                                         | SOT-223                    | [AliExpress]()
|  1  | 10µF Capacitor                                                         | 0805                       | [AliExpress]()
|  1  | 22µF Capacitor                                                          | 0805                       | [AliExpress]()
|  1  | 0.1µF Capacitor                                                       | 0805                       | [AliExpress]()
|----:|-----------------------------------------------------------------------------------------------------|----------|
| Display                                                                                                   ||||
|----:|------------------------------------------------------------------------|----------------------------|----------|
|  1  | 14x02 Female Pinheader 2.54mm / 0.1" Pitch SMD                         |                            | [AliExpress]()
|  1  | 04x01 Female Pinheader 2.54mm / 0.1" Pitch SMD                         |                            | [AliExpress]()
|  1  | 2 Pin WAGO SMD Wire to Board connector                                 |                            | [AliExpress]()
|  1  | 3 Pin WAGO SMD Wire to Board connector                                 |                            | [AliExpress]()
|----:|------------------------------------------------------------------------|----------------------------|----------|
| Sensors|(optional)                                                                                                ||||
|----:|------------------------------------------------------------------------|----------------------------|----------|
|  1  | BME280 SMD                                                             |                            | [AliExpress]()
|  3  | 10k Ohm Resistor                                                       | 0805                       | [AliExpress]()
|  1  | 1µF Capacitor                                                          | 0805                       | [AliExpress]()
|  1  | 0.1µF Capacitor                                                        | 0805                       | [AliExpress]()
|  2  | JST SH I²C header                                                      | 4x1 JST SH                 | [AliExpress]()
|----:|------------------------------------------------------------------------|----------------------------|----------|
| USB Uart|(optional)                                                                                                   ||||
|----:|------------------------------------------------------------------------|----------------------------|----------|
|  1  | ESP-32 Wroom                                                           |                            | [AliExpress]()
|  1  | 14x02 Female Pinheader 2.54mm / 0.1" Pitch SMD                         |                            | [AliExpress]()
|  1  | 04x01 Female Pinheader 2.54mm / 0.1" Pitch SMD                         |                            | [AliExpress]()
|  1  | 2 Pin WAGO SMD Wire to Board connector                                 |                            | [AliExpress]()
|  1  | 3 Pin WAGO SMD Wire to Board connector                                 |                            | [AliExpress]()
|----:|------------------------------------------------------------------------|----------------------------|----------|
{:.table-striped}

## Power Circuit

Calculations as per EEV Blog #110

{% include video id="qGp82xhybs4" provider="youtube"%}

$$ {t_{on} \over t_{off}} = { {V_{out}+V_{f}}\over{V_{in}-V_{sat}-V_{out}} } = 0.200 $$

$$ {t_{on} + t_{off}} = { {1}\over{f}} = 33.33µs $$

## Cloning

Make sure to add the `--recursive` parameter when cloning the project. Otherwise git will not download the required submodules in the `/lib` subdirectory.

```bash
git clone --recursive https://github.com/fvanroie/hasp-lvgl
```

If you already cloned hasp-lvgl without the submodules, you can fetch the submodules seperately using:

```bash
git submodule update --init --recursive
```

To build a defierent branch use:

```bash
git clone --recursive https://github.com/fvanroie/hasp-lvgl
cd hasp-lvgl
git checkout 0.1.0-dev
git submodule update --init --recursive
```

## Getting Started

Check out the [wiki](https://github.com/fvanroie/hasp-lvgl/wiki) for how-to's, information and frequently asked questions.

