---
title: "First Setup"
permalink: /docs/first-setup/
excerpt: "Instructions and suggestions for upgrading the theme."
last_modified_at: 2018-11-25T19:38:20-05:00
toc: true
---

At first boot or when no wifi setup is found, the device will create an initial Access Point for configuring the device:
- Use the touchscreen -if available- to enter your SSD and password
- Connect to the temporary Access Point remotely:
  - Scan the QR on the display, if available and complete the setup on your mobile device
  - or Check the serial log for the SSID and password to connect
- Browse to http://192.168.4.1
- Enter your the SSID and password for joining your own wireless network
- Click Save Settings
- The device will automatically reboot and connect to your wireless LAN

**Note:** To skip this step, wifi credentials can be saved into the .bin file when you compile the firmware yourself.
{: .notice--info}
