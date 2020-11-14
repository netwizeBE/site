---
title: "Frequently Asked Questions"
permalink: /projects/hasp-lvgl/faq/
excerpt: "Frequently Asked Questions"
toc: true
---

## Command Reference

**page** [1-12]

Switches the display to show the objects from a diferent page.

**clearpage** [1-12,254]

Deletes all object from a given page. If no page number is specified, it clears the current page.

**dim** [0-100] (alias: `brightness`)

Sets the level of the backlight from 0 to 100%, where 0% is off and 100% is full brightness.

`dim 50` sets the display to half the brightness.

Tip: this can be used in conjunction with the idle event, e.g. to dim the backlight after a short period of inactivity.

** light ** (bool)

Switches the backlight on or off, independent of the set dim level.
Turning the backlight on will restore the brightness to the previous dim level.

`light on` acepted values: on/off, true/false, 0/1, yes/no

Tip: this can be used in conjunction with the idle event, e.g. to turn the backlight off after a long period of inactivity.

    Note: The `dim`and `light` command depends on a GPIO pin to be connected to control the the TFT_LED backlight via a transistor.

**wakeup**

Clears the idle state of the device and publishes an `state/idle = OFF` status message.
This is helpfull e.g. when you want to wake up the display when an external event has occured, like a PIR motion sensor.

**calibrate**

Start on-screen touch calibration.

Note: You need to issue a soft reboot command to save the new calibration settings. If you do a hard reset of the device, the calibration settings will be lost.

**screenshot**

Saves a picture of the current screen to the flash filesystem. You can retrieve it via http://<ip-address>/screenshot.bmp
This can be handy for error reporting.

The previous screenshot is overwritten.

**statusupdate**

Reports the status of the MCU. The response will be posted to the state topic:
```json
    "statusupdate": {
        "status": "available",
        "espVersion": "0.0.6",
        "espUptime": 124,
        "signalStrength": -72,
        "haspIP": "10.1.0.148",
        "heapFree": 5912,
        "heapFragmentation": 7,
        "espCore": "2_6_3"
    }
```

**reboot** (alias: `restart`)

Reboots the device.

**factoryreset**

Clears the filesystem and eeprom and reboot the device in its initial state.

Warning: There is no confirmation prompt!