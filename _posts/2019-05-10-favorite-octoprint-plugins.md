---
title: Favorite Octoprint Plugins
author: fvanroie
date: 2019-05-10 16:05
image: http://place-hold.it/900x300
images_url: assets/images/2019/favorite-octoprint-plugins/
lead: 
categories:
- 3D Printing
tags:
- Octoprint
---

{% include toc.html %}

List
---------

{:class="table table-bordered"}
| Plugin Name | Version | Description							| Link |
|-----------------------|---------|---------------------------------------|------|
| Detailed Progress		| 0.1.4		| Display estimated End time and time Left on the printer display.
| FileManager			| 0.1.3		| Organize, move, rename, delete gcode files stored in Octiprint.
| Firmware Updater		| 1.3.1		| Easily update the firmware of the printer from Octoprint.
| FloatingNavbar		| 0.3.0		| Simple plugin that makes the navbar float and always display on top.
| ipOnConnect			| 0.2.2		| Display the IP address of Octoprint on the printer display.
| LayerDisplay			| 0.4.1		| 
| M73-Progress-Plugin	| 0.1.0		| Update the Progressbar on the printer display when using USB print via Octoprint.
| MQTT					| 0.8.1		| An OctoPrint Plugin that adds support for MQTT to OctoPrint.
| MQTT Publish			| 0.5.0		| Plugin to send MQTT command from button in navbar.
| Navbar Temperature	| 0.11		| Displays temperatures on navigation bar.
| Octolapse				| 0.3.4		| Make beautiful timelapses of your prints.
| PortLister			| 0.1.8		| AutoConnects to the printer in Octoprint after the printer comes online, so you don't have to click the Connect button each time.
| PrintTimeGenius		| 1.3		| Use a gcode pre-analysis to provide better print time estimation
| Tasmota-MQTT			| 0.3.1		| Control tasmota smart plugs with MQTT from within Octoprint.
| Themeify				| 1.2.0		| Control the layout and theme of Octiprint.
| TouchUI				| 0.3.12	| A touch friendly interface for a small TFT modules and or phones.
| Webcam Tab			| 0.1.2		| Unclutter the control tab by moving the webcam view into a separate tab.
{:.table-striped}

PortLister
----------

Make sure you set the correct fixed baud rate in OctoPrint instead of using AUTO for the baudrate.
PortLister uses this value to probe for the printer port. If you set it to AUTO in Octoprint, PortLister will not function correctly.

You can set the interval to check in the config.yaml file:
```
plugins:
  portlister:
    autoconnect_delay: 5
```


Bill of Materials
-----------------

