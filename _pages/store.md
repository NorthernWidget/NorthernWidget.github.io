---
layout: splash
styles: wide
title: "Store"
permalink: /store/

header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/MiddleWS_2020-02-23_19.59.52_modified.jpg
  actions:
    - label: <i class="fab fa-fw fa-github"></i> Designs
      url: "https://github.com/NorthernWidget"
    - label: <i class="fab fa-fw fa-github"></i> Skunkworks
      url: "https://github.com/NorthernWidget-Skunkworks"
  caption: "Left to Right: Shanti Penprase, Max van Wyk de Vries, and Gioachino Roberti. Perito Moreno Glacier. *Photo: A. Wickert*"
excerpt: "Purchase your own field instrumentation."
---

{% for product in site.products %}
 {% include product.html %}
{% endfor %}

# Licenses

All designs and documentation are licensed under Creative Commons Attribution Share-Alike v4.0.

All code is licensed under the GNU GPL v3.0.

[![License: CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/80x15.png)](https://creativecommons.org/licenses/by-sa/4.0/)

[![License: GNU GPL 3.0](https://www.gnu.org/graphics/gplv3-or-later-sm.png)](https://www.gnu.org/licenses/gpl-3.0.en.html)
