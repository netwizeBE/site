---
title: "Wifi Setup"
permalink: /projects/hasp-lvgl/wifi-setup/
excerpt: "Setup the credentials for your wifi access point."
toc: true
---

At first boot, when no wifi setup is found, the device will create an initial Access Point for configuring the device.
If a display is connected, a QR code is displayed along the temporary SSID and password to connect.

<figure class="third">
    <a href="/site/assets/images/hasp/oobe_setup.png"><img src="/site/assets/images/hasp/oobe_seup.png"></a>
    <a href="/site/assets/images/hasp/wifi_setup.png"><img src="/site/assets/images/hasp/wifi_setup.png"></a>
	<figcaption>Out-Of-Box-Experience</figcaption>
</figure>

Use the touchscreen or a webbrowser to setup the credentials for your local wifi access point.

## Using Touchscreen

- Tap on the screen to start a Touch Calibration sequence:
  - Touch the 4 courners as indicated
- Use the touchscreen to enter your local SSID and password
- Tap on the Checkmark button in the lower righthand corner

The device will validate the entered credentials and reboot if they are correct.

## Using WiFi Access-Point

Connect to the temporary Access Point by scanning the QR on the display, if available.
Or Check the serial log for the SSID and password to connect.

- Browse to http://192.168.4.1
- Enter your the local SSID and password for joining your wireless network
- Click Save Settings
- The device will automatically reboot and connect to your wireless LAN

**Note:** To skip this step, wifi credentials can be saved into the .bin file when you compile the firmware yourself.
{: .notice--info}
