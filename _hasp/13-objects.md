---
title: "Objects"
permalink: /projects/hasp-lvgl/objects/
excerpt: "Suggestions and Front Matter defaults for working with pages."
toc: true
---

## Common Properties

These are the common properties shared among all objects:

<style>
table th:first-of-type {
    width: 12%;
}
table th:nth-of-type(2) {
    width: 12%;
}
table th:nth-of-type(3) {
    width: 12%;
}
table th:nth-of-type(4) {
    width: 12%;
}
table th:last-of-type {
    width: 48%;
}
</style>

| Property | Value      | Required | Default | Description |
|:---------|:----------:|:--------:|:-------:|:------------|
| id       | 0-255      | yes      | n/a     | ID of the object on this page |
| objid    | 0-255      | yes      | n/a     | ID of the object type *(see below)* |
| page     | 0-255      | no       | n/a     | ID of the page the object appears on |
| x        | int16      | no       | 0       | horizontal position on the page |
| y        | int16      | no       | 0       | vertical position on the page |
| w        | int16      | no       | 0       | width of the object |
| h        | int16      | no       | 0       | height of the object |
| enabled  | true/false | no       | true    | object is clickable |
| hidden   | true/false | no       | false   | object is hidden |
| opacity  | 0-255      | no       | 255     | how much the the object is opaque |

If the `page` parameter is not present, the object is placed on the same page as the _previous object_. If `page` is not specified for the first object either, the _current page_ being displayed is used.

The maximum number of pages and objects is limited by the memory available in the MCU.

`"page":254` indicates that the object is visible on every page. It can be used for example to specify a static menu bar.
You can still hide the object on select pages if needed. Objects on this page appear on top of any objects on the underlying page.

## Comments
If any of the required `id` or `objid` properties are missing -*and the line is still valid json*- then it is interpreted as a comment. You can also use the `page` parameter in a comment to set the default page of objects without a `page` parameter.

Example 1: Add a comment on a single line that is ignored.
```json
{"comment":" ----------- Page 2 layout ------------"}
```

Example 2: Set the default `page` for next object(s) to `3` besides adding a comment.

```json
{"page":3,"comment":" ---- My Awesome Color Picker Layout ----"}
```

If you then omit the `page` parameter in the lines below the comment of example 2, those objects will appear on page `3`.

> Note: If the line is not valid json, the parsing of the rest of the file is also stopped.

## Blank Lines
Blank lines are allowed for readability and are ignored.

## Object Types

Each object type is an ID that indicates which object type that line represents.
Besides the common properties listed above, each object type can have specific properties.


### Button
**objid:10**

![lv_btn]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_btn_1.png){: .align-center}

| Property | Value      | Required | Default | Description
|----------|------------|----------|---------|--------------
| toggle   | boolean    | no       | true    | When enabled, creates a toggle-on/toggle-off button. If false, creates a normal button
| val      | int16      | no       | 0       | The value: 1 for toggled, 0 for untoggled
| txt      | string     | no       | ""      | The text of the label
| mode     | string     | no       | expand  | The wrapping mode of long text labels

Normal Switches send touch events out as they occor. The possible events are:

- DOWN: Occurs when a button goes from unpressed to being pressed
- SHORT: The button was release in a short time (short click)
- LONG: Event is send when the button is *still* being pressed after the threshold
- HOLD: The HOLD event is repeated every 400ms while the button is still pressed
- UP: The button is released
- LOST: The LOST event occurs when the object looses the focus while the screen is still being touched

Toggle Switches only send out their new value (0 or 1) when toggled.

Possible wrapping modes are: expand, break, dots, scroll and loop

### Checkbox
**objid:11**

![lv_checkbox]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_checkbox_1.png){: .align-center}

| Property | Value      | Required | Default    | Description
|----------|------------|----------|------------|--------------
| val      | int16      | no       | 0          | The value: 1 for checked, 0 for unchecked
| txt      | string     | no       | "Checkbox" | The label of the checkbox

### Text Label
**objid:12**

![lv_label]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_label_1.png){: .align-center}

| Property | Value      | Required | Default    | Description
|----------|------------|----------|------------|--------------
| txt      | string     | no       | "Text"     | The text of the label
| mode     | string     | no       | expand     | The wrapping mode of long text labels

Possible wrapping modes are: expand, break, dots, scroll and loop

```json
{"page":2,"id":1,"objid":12,"h":24,"w":120,"txt":"\ufe05 Icon Demo"}
```

### Arc
**objid:22**

![lv_arc]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_arc_1.png){: .align-center}

| Property  | Value      | Required | Default | Description
|-----------|------------|----------|---------|--------------
| min       | int16      | no       | 0       |
| max       | int16      | no       | 100     |
| val       | int16      | no       | 0       |
| rotation  | int16      | no       | 0       |
| type      | int16      | no       | normal  | normal, reverse, symetrical


### Spinner
**objid:21**

![lv_spinner]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_spinner_1.png){: .align-center}

| Property  | Value      | Required | Default | Description
|-----------|------------|----------|---------|--------------
| speed     | int16      | no       | 1000    | The time for 1 furn in ms
| direction | int16      | no       | 100     | 0 for clockwise, 1 for counter-clockwise
| thickness | int16      | no       | dep. on theme | The width of the arcline

### Colorpicker
**objid:20**

![lv_cpicker]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_cpicker_1.png){: .align-center}

| Property | Value      | Required | Default | Description
|----------|------------|----------|---------|--------------
| val      | uint16     | no       | 0       | The selected color in RBG565 format
| color    | hex string | no       | 0       | The selected color in html format #rrggbb
| rect     | boolean    | no       | false   | True if the color picker has a rectangular shape like a slider. False for a circular shape.


### Slider
**objid:30**

![lv_slider]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_slider_1.png){: .align-center}

| Property | Value      | Required | Default |
|----------|------------|----------|---------|
| min      | int16      | no       | 0       |
| max      | int16      | no       | 100     |
| val      | int16      | no       | 0       |

### Double Slider
**objid:30**

| Property | Value      | Required | Default |
|----------|------------|----------|---------|
| min      | int16      | no       | 0       |
| max      | int16      | no       | 100     |
| val      | int16      | no       | 0       |


### Gauge
**objid:31**

![lv_gauge]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_gauge_1.png){: .align-center}

| Property | Value      | Required | Default |
|----------|------------|----------|---------|
| min      | int16      | no       | 0       |
| max      | int16      | no       | 100     |
| val      | int16      | no       | 0       |


### Progressbar
**objid:32**

![lv_bar]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_bar_1.png){: .align-center}

| Property | Value      | Required | Default |
|----------|------------|----------|---------|
| min      | int16      | no       | 0       |
| max      | int16      | no       | 100     |
| val      | int16      | no       | 0       |


### Switch
**objid:40**

![lv_switch]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_switch_1.png){: .align-center}

| Property   | Value      | Required | Default | Description
|------------|------------|----------|---------|---------------
| val      | int16        | no       | 0       | The value: 1 for on, 0 for off

### LED Indicator
**objid:41**

![lv_led]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_led_1.png){: .align-center}

| Property   | Value      | Required | Default | Description
|------------|------------|----------|---------|---------------
| val        | byte       | no       | 0       | The brightness of the indicator 0-255

### Dropdown List
**objid:50**

![lv_dropdown]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_dropdown_1.png){: .align-center}

| Property | Value      | Required | Default | Description
|----------|------------|----------|---------|--------------------------
| options  | string     | no       | ""      | The items separated by \n
| val      | int16      | no       | 0       | The number of the selected item
| txt      | string     | no       | ""      | *Read-only* The text of the selected item

To change the currently selected item, use the `val` attribute.
To change the items in the list, use the `options` attribute.

When the item is changed both `val` and `txt` of the newly selected item are send out.


### Roller
**objid:51**

![lv_roller]({{ site.url }}{{ site.baseurl }}/assets/images/hasp/lv_ex_roller_1.png){: .align-center}

| Property | Value      | Required | Default | Description
|----------|------------|----------|---------|--------------------------
| options  | string     | no       | ""      | The items separated by \n
| val      | int16      | no       | 0       | The number of the selected item
| txt      | string     | no       | ""      | *Read-only* The text of the selected item
| rows     | int8       | no       | 3       | The number ow rows that are visible

Note: A roller does not use the `h` attribute to set its height, but uses the rows to set the visible number of rows instead.

To change the currently selected item, use the `val` attribute.
To change the items in the list, use the `options` attribute.

When the item is changed both `val` and `txt` of the newly selected item are send out.
