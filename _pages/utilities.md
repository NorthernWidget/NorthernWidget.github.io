---
layout: splash
styles: wide
title: "Utilities"
permalink: /utilities/

header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/Pol-house-logger-prep_2020-02-20_19.42.46_modified.jpg
  actions:
    - label: <i class="fab fa-fw fa-github"></i> Designs
      url: "https://github.com/NorthernWidget"
    - label: <i class="fab fa-fw fa-github"></i> Skunkworks
      url: "https://github.com/NorthernWidget-Skunkworks"
  caption: "Pre-deployment chaos and daisy-chaining Heptapods. A. Wickert (left) and S. Penprase (right). Photo: someone in our group."
excerpt: "Boards with one job.<br>
          Firmware libraries.<br>
          ***Utilities.***"
---


# Northern Widget utility boards

## Instrumentation-Amp

*Variable-gain instrumentation amplifier, used by us with thermopile pyranometers.*
[<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget/Instrumentation-Amp)

## Maxbotix-Helper

*Breaks out the pins on a MaxBotix ultrasonic rangefinder into easy-connect screw terminals for the data logger and temperature correction.*
[<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget/Maxbotix-Helper)

| **Top** | **Bottom** |
| ------- | ---------- |
| <img src="https://raw.githubusercontent.com/NorthernWidget/MaxBotix-Helper/master/doc/OSHParkTop.png" width="280"> | <img src="https://raw.githubusercontent.com/NorthernWidget/MaxBotix-Helper/master/doc/OSHParkBottom.png" width="280"> |

<br>


# Skunkworks utility boards

*These boards are in active development.*

## Longbow

*Convert a RS-485 signal from a sensor (can travel up to 1 km) to an I2C signal that a standard logger or Arduino can read.*
[<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget-Skunkworks/Project-Longbow)

## Tally

*Counter that can debounce noisy signals (e.g., from reed switches) in analog circuitry. Good for anemometers and tipping-bucket rain gauges.*
[<i class="fab fa-fw fa-github"></i> Hardware](https://github.com/NorthernWidget-Skunkworks/Project-Tally)
&nbsp;|&nbsp;
[<i class="fab fa-fw fa-github"></i> Library](https://github.com/NorthernWidget-Skunkworks/Tally_Library)

![Tally](https://raw.githubusercontent.com/NorthernWidget-Skunkworks/Project-Tally/master/Tally_Top.png)

## Raven

*High-gain current amplifier.*
[<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget-Skunkworks/Project-Raven)

## Heptapod

*Screw terminals to connect additional sensors to the same bus.*
[<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget-Skunkworks/Project-Heptapod)

Connect 1 I2C connection, half-duplex RS-485 connection, or (with a design variant) full-duplex RS-485 connection to up to four connections.
Turns one connection into four connections, and 1+4 = Heptapod.

<br>


# Libraries for off-the-shelf hardware

We write and maintain Arduino libraries for sensors and chips we use in our designs.
These work independently of Northern Widget hardware too.

## Northern Widget libraries

*Stable libraries in the main NorthernWidget organization.*

| Library | What it's for |
| ------- | ------------- |
| [T9602](https://github.com/NorthernWidget/T9602_Library) | Temperature and relative humidity sensor |
| [MaxBotix](https://github.com/NorthernWidget/MaxBotix_Library) | Ultrasonic rangefinder with temperature correction |
| [BME](https://github.com/NorthernWidget/BME_Library) | Bosch BME280 temperature, pressure, and humidity |
| [DS3231](https://github.com/NorthernWidget/DS3231) | Real-time clock (used in NW data loggers) |
| [MS5803](https://github.com/NorthernWidget/MS5803) | High-resolution pressure sensor |
| [MCP3421](https://github.com/NorthernWidget/MCP3421) | 18-bit I2C ADC |

## Skunkworks libraries

*In active development.*

| Library | What it's for |
| ------- | ------------- |
| [ADS1115](https://github.com/NorthernWidget-Skunkworks/ADS1115_Library) | 16-bit I2C ADC |
| [MCP3221](https://github.com/NorthernWidget-Skunkworks/MCP3221) | 12-bit I2C ADC |
| [MCP4725](https://github.com/NorthernWidget-Skunkworks/MCP4725) | 12-bit I2C DAC |

<br>


# Open-source licenses

All designs and documentation are licensed under Creative Commons Attribution Share-Alike v4.0.

All code is licensed under the GNU GPL v3.0.

[![License: CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/80x15.png)](https://creativecommons.org/licenses/by-sa/4.0/)
[![License: GNU GPL 3.0](https://www.gnu.org/graphics/gplv3-or-later-sm.png)](https://www.gnu.org/licenses/gpl-3.0.en.html)
