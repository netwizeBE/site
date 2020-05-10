---
title: "Reflow Oven"
author: fvanroie
date: 2019-07-21 18:13
excerpt: "Convert a small toaster oven into an electronics reflow oven."
header:
  image: /assets/images/foo-bar-identity.jpg
  teaser: https://via.placeholder.com/350x250.png?text=Visit+WhoIsHostingThis.com+Buyers+Guide
sidebar:
  - title: "Role"
    image: https://via.placeholder.com/350x250.png?text=Visit+WhoIsHostingThis.com+Buyers+Guide
    image_alt: "logo"
    text: "Designer, Front-End Developer"
  - title: "Responsibilities"
    text: "Reuters try PR stupid commenters should isn't a business model"
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
categories:
- Electronics
tags:
- ESP 8266
- SMD Soldering
- Home Electronics
---

## Gallery
{% include gallery caption="This is a sample gallery to go along with this case study." %}

Bill of Materials
----------

### Mini Oven

{:class="table table-bordered"}
| Qty | Description                                                                                         | Supplier |
|----:|-----------------------------------------------------------------------------------------------------|----------|
|  1  | Small electrical Oven: 15L Silvercrest SGB 1380W A1 or B2                                           | [E-bay](https://www.ebay.de/sch/i.html?_nkw=mini+oven+sgb+1380)
|  1  | Heating Cartridge 220V Air Heater Element 12x120mm 350W/450W/580W                                   | [AliExpress](https://www.aliexpress.com/item/32850664010.html)
|  2  | Hook or eye bolts 12mm inner diameter (for heating cartridge)                                       | Hardware Store
|  1  | High Temperature Silicon                                                                            | Hardware Store
|  1  | Glassfiber Insulation                                                                               |
|  1  | Fire Blanket
|  1   | Kapton Tape                                                                                        | [AliExpress](https://www.aliexpress.com/item/33046071835.html)
| 5m  | 5cm x 5m Reflective Gold Foil High Temperature Insulation Thermal Tape                              | [AliExpress](https://www.aliexpress.com/item/32913230761.html)
|  1  | 20x60cm Self Adhesive Reflective Gold Foil High Temperature Insulation Thermal Sheet                | [AliExpress](https://www.aliexpress.com/item/32968199537.html)
{:.table-striped}

The main item to procure is a small electrical oven. A good guide on the selection of a suitable mini oven can be found on [this build site](https://whizoo.com/reflowoven).
We used a Silvercrest 15L SGB 1380W A1 or B1 model becaue it has a lot of power, a relatively small size and an internal convection fan. It worked out great!

The additional heating cartridge adds another 450W of power for quicker heating and this makes it easier to follow a reflow profile. It is held into place with 2 eye bolts.

Glassfiber Insulation is needed to keep the heat in as much as possible. Cheap ovens usually lack good insulation, so it must be added.
Also fill up any seems from which air can escape the heating chamber using a high temperature silicon filler.

A piece of fire blanket can be taped to the backside using kaptop tape for additional insulation of the back wall.

On the inside, a large sheet of reflective thermal tape is added to the sides. You can also use Thermal Tape on the inside of the door, but be sure to leave enough of the window open so you can still look inside.

### Custom Electronics

<div>
{% for image in site.static_files %}
  {% if image.path contains page.images_url %}
    {% unless image.path contains '-th.' %}
		{% assign pathParts = image.path | split: "/" %}
		{% assign length = pathParts.size | minus: 2 %}
		{% assign path = "" %}
		{% for c in (0..length) %}
			{% capture path %}{{ path }}/{{pathParts[c]}}{% endcapture %}
		{% endfor %}
      <a href="{{ image.path }}">
        <img src="{{ site.url }}{{ path }}/{{ image.basename | append: '-th' | append: image.extname }}" alt="">
      </a>
    {% endunless %}
  {% endif %}
{% endfor %}
</div>

{:class="table table-bordered"}
| Qty | Description                                                                                         | Supplier |
|----:|-----------------------------------------------------------------------------------------------------|----------|
|  1  | Rocker Switch with Light ON-OFF Three Feet Switch 15A 250V                                          | [AliExpress](https://www.aliexpress.com/item/32869269215.html)
|  1  | AC-DC 12V Power Supply
|  1  | Bare PCB with stencil or protoboard
|  1  | ESP 12F (E or S) or Wimos D1 mini
|  3  | Solid State Relay 12v 24v SSR-10VA SSR-25VA SSR-40VA (10A, 25A or 40A Relais) Regulator AC          | [AliExpress](https://www.aliexpress.com/item/32925988795.html)
|  1  | 1 or 2 Channel 5V DC Relay Module Solid State High Level SSR AVR DSP G3MB-202P Relay for Arduino    | [AliExpress](https://www.aliexpress.com/item/32736680428.html)
|  1  | MAX31855 MAX31855KASA                                                                               | [AliExpress](https://www.aliexpress.com/item/-/32919725381.html)
|  1  | K-type Wire Temperature Test Thermocouple Sensor Probe                                              | [AliExpress](https://www.aliexpress.com/item/32824318079.html)
|  1  | 3.5" Nextion HMI Touchscreen (or TJC)                                                               | [AliExpress](https://www.aliexpress.com/item/32684571300.html)
|  1  | 0603 array 8P4R 2*4P Network Resistor array 1K ohm
{:.table-striped}

### Optionals

{:class="table table-bordered"}
| Qty | Description                                                                                         | Supplier |
|----:|-----------------------------------------------------------------------------------------------------|----------|
|  2  | DC 5V USB 60mm 60x15mm Micro Radiator Motor Blower Cooling Fan                                      | [AliExpress](https://www.aliexpress.com/item/32815311688.html)
|  1  | Reed switch                                                                                         | [AliExpress](https://www.aliexpress.com/item/32993412700.html)
|  1  | Magnet                                                                                              | [AliExpress](https://www.aliexpress.com/item/32960460043.html)
|  1  | DC 12V Gear Reduction Motor 150RPM Turbo Worm Gear High Torque Geared Motor                         | [AliExpress](https://www.aliexpress.com/item/32922646219.html)
|  1  | L298N Stepper DC Motor Driver Shield for arduino                                                    | [AliExpress](https://www.aliexpress.com/item/32704610408.html)
|  1  | 150mm miniature linear rail slide MGN7 C linear guide+ with MGN7 C carriage                         | [AliExpress](https://www.aliexpress.com/item/32806622073.html)
{:.table-striped}

~~~ ruby
def what?
  42
end
~~~