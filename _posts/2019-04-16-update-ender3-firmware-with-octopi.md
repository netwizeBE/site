---
published: true
title: Update the Ender 3 Firmware With OctoPi
author: fvanroie
date: 2019-04-16 23:19
image: http://place-hold.it/900x300
lead: In this post we will replace the default printer firmware of the Ender 3 and install stock Marlin. A bootloader will be installed first to make future firmware updates much easier. Additionally we install the Firmware Updater plugin for OctoPi to upload the new firmware.
categories:
- 3D Printing
tags:
- Ender 3
- Marlin Firmware
- Octopi
- Octoprint
- Raspberry Pi
---

Warning
> This post will explain how to replace the stock firmware on your Ender 3 printer. Doing so will completely erase the flash on the printer and replace it with the latest Marlin build. This post is a general step-by-step explenation of how to achieve this. If you are not confident to perform these actions, please ask help before attempting the firmware replacement."
{: .notice--warning}

## TOC

- Install avrdude on OctoPi

Connect to your OctoPi via SSH.

In the terminal type this command to install avrdude:
```bash
sudo apt-get install avrdude
```

Check that avrdude is installed:
```bash
avrdude -v
```

Copy the configuration file to your local profile folder:
```bash
cp /etc/avrdude.conf ~/avrdude.conf 
```


- Connect the printer to Raspberry Pi

Test that the gpio connection to the printer is working:
```bash
sudo avrdude -p atmega1284p -C ~/avrdude_gpio.conf -c pi_1 –v
```

You should receive a message saying the device is ready to accept instrustions.

- Flash the bootloader

First download the sanguino board binaries, incuding the bootloader:
```bash
git clone 
```

```bash
sudo avrdude -p atmega1284p -C ~/avrdude.conf -c pi_1 -U flash:w:bootloader.hex:i
```

- Flash the firmware via USB

```bash
sudo avrdude -p atmega1284p -C ~/avrdude.conf 
```

- Install Firmware-Update plugin
- Configure Firmware-Update plugin
- Upload Marlin firmware