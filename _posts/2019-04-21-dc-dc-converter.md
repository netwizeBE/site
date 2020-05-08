---
title: DC-DC Converter
author: fvanroie
date: 2019-04-21 19:44
image: http://place-hold.it/900x300
images_url: assets/images/2019/dc-dc-converter/
lead: 
categories:
- Electronics
tags:
- Home Electronics
- SMD Soldering
toc: true
classes: wide
---

{% include toc.html %}

Reference
---------

- [60V input to 5V – 3A output DC-DC Converter for Industrial and Automotive using TPS54360](http://www.electronics-lab.com/project/60v-input-5v-3a-output-dc-dc-converter-industrial-automotive/)
- [60V to 5V-2Amps USB Power Output DC-DC Converter for E-Vehicle](https://www.twovolt.com/2018/12/08/60v-to-5v-2amps-usb-power-output-dc-dc-converter-for-e-vehicle/)


Schematics
----------

<div>
        <img src="http://10.1.0.165:4000/assets/images/2019/dc-dc-converter/dc-dc-converter-schema.png" alt="Schema" class="img-responsive"/>
</div>

<div>
{% for image in site.static_files %}
  {% if image.path contains page.images_url %}
    {% unless image.path contains '-th.' %}
      <a href="{{ image.path }}">
        <img src="{{ image.basename | append: '-th' | append: image.extname }}" alt="">
      </a>
    {% endunless %}
  {% endif %}
{% endfor %}
</div>

Bill of Materials
-----------------

{:class="table table-bordered"}
|  # | Qty | Ref | Description							| Supplier |
|---:|:---:|--------------------------------------------|----------|
|  1 |  2  | J2	 | 4 Pin header Connector				| [AliExpress](https://www.aliexpress.com/item/32879595293.html)
|  2 |  1  | C1  | 0805 SMD Capacitor 0.1uF				| [AliExpress](https://www.aliexpress.com/item/737181119.html)
|  3 |  1  | C2-C3| 1210 SMD Capacitor 47uF/10V			| [AliExpress](https://www.aliexpress.com/item/32878849918.html)
|  4 |  1  | C4  | 1210 SMD Capacitor 10uF/80V			| [AliExpress](https://www.aliexpress.com/item/1605964555.html)
|  5 |  1  | C5  | Omit									| n/a
|  6 |  1  | C6  | 0805 SMD Capacitor 39pF				| [AliExpress](https://www.aliexpress.com/item/32848303008.html)
|  7 |  1  | C7  | 0805 SMD Capacitor 6K8pF				| [AliExpress](https://www.aliexpress.com/item/32853390788.html)
|  8 |  1  | D1  | MUR360 ON SEMI						| [AliExpress](https://www.aliexpress.com/item/32900566282.html)
|  9 |  1  | L1  | 8.2uH/3A SMD 12x12mm Inductor		| [AliExpress](https://www.aliexpress.com/item/32903931831.html)
| 10 |  1  | R1  | 0805 SMD Resistor 510K				| [AliExpress](https://www.aliexpress.com/item/32803541239.html)
| 11 |  1  | R2  | 0805 SMD Resistor 51K				| [AliExpress](https://www.aliexpress.com/item/32803541239.html)
| 12 |  1  | R3  | 0805 SMD Resistor 13K				| [AliExpress](https://www.aliexpress.com/item/32803541239.html)
| 13 |  1  | R4  | 0805 SMD Resistor 10.2K				| [AliExpress](https://www.aliexpress.com/item/32867286313.html)
| 14 |  1  | R5  | 0805 SMD Resistor 82K				| [AliExpress](https://www.aliexpress.com/item/32803541239.html)
| 15 |  1  | R6  | 0805 SMD Resistor 160K				| [AliExpress](https://www.aliexpress.com/item/32803541239.html)
| 16 |  1  | U1  | TPS54360DDAR SOP-8					| [AliExpress](https://www.aliexpress.com/item/32822788317.html)
{:.table-striped}


Protoboard
----------

PCB Design
----------

<div>
    <img src="http://10.1.0.165:4000/assets/images/2019/dc-dc-converter/dc-dc-converter-pcb.png" alt="Schema" class="img-responsive"/>
</div>

3D Render
---------

<div>
    <img src="http://10.1.0.165:4000/assets/images/2019/dc-dc-converter/dc-dc-converter-3d.png" alt="Schema" class="img-responsive"/>
</div>

<div class="sketchfab-embed-wrapper"><iframe width="640" height="480" src="https://sketchfab.com/models/8e6eee8087814fe586b035799ab8fe0c/embed" frameborder="0" allow="autoplay; fullscreen; vr" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
</div>

Result
------
