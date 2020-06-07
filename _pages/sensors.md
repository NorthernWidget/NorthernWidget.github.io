---
layout: splash
styles: wide
title: "Sensors"
permalink: /sensors/

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
excerpt: "From water level to solar radiation, Northern Widget develops
          field-capable sensors with software and firmware libraries that work with any Arduino-compatible device.<br>
          We also make sure that you can connect common and inexpensive third-party sensors to our systems.<br>
          ***Open-source versatility for field scientists.***"
---

# Northern Widget sensors

## Walrus

*Measure water levels (or atmospheric pressure) and temperature with this encapsulated sensor.*
[<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget-Skunkworks/Project-Walrus)

<img src="https://media.githubusercontent.com/media/NorthernWidget-Skunkworks/Project-Walrus/master/Documentation/images/Walrus_PTH_v000_with_enclosure_and_scale_cleaned_background_20200428.png" alt="Walrus" width="480"/>


## Haar

*Waterproof atmospheric temperature, pressure, and relative humidity sensor.*
[<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget-Skunkworks/Project-Haar)

<img src="https://media.githubusercontent.com/media/NorthernWidget-Skunkworks/Project-Haar/master/Documentation/images/Haar_v010_and_housing_exploded_20200228.png" alt="Haar" width="480"/>


## LiDAR Lite Symbiont

*Turn a raw Garmin LiDAR Lite sensor into an integrated tool to measure range and orientation.*
[<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget-Skunkworks/Project-Symbiont-LiDAR)

<img src="https://raw.githubusercontent.com/NorthernWidget-Skunkworks/Project-Symbiont-LiDAR/master/Documentation/images/PrototypeBoxAssembly_orig2019-09-05_20200501.jpg" alt="LiDAR Lite Symbiont" width="480"/>

Includes:
* 3-axis MEMS accelerometer to measure laser orientation
  * No need to position the sensor looking straight down to measure level: can trigonometrically coorect
  * Will record whether the sensor has been disturbed
* Power management and filtering for high current during laser shots
* Failsafes to reset the LiDAR Lite when its firmware locks, thus isolating the rest of your system from a potential failure mode.
* Full instructions for enclosure and mounting

<img src="https://github.com/NorthernWidget-Skunkworks/Project-Symbiont-LiDAR/blob/master/Documentation/images/Perspective_view_installed_2019-09-14_15.30.02.jpg?raw=true" alt="LiDAR Lite Symbiont Deployed" width="240"/>


## Dyson

*Long-wave and spectrally resolved short-wave radiation.* [<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget-Skunkworks/Project-Dyson)

<img src="/assets/images/DysonDeployed_Ecuador_2020-01-14_11.55.11_modified.jpg" alt="Dyson LW and SW Deployed" width="480"/>
<br/>
<br/>
<br/>


# Support for off-the-shelf sensors

* Tipping-bucket rain gauges
  * Reed switch or Hall-effect sensor
  * Project Tally (optional)
* T9602 temperature and relative humidity sensor (add library link)
* Decagon / METER soil moisture probes (do we even have a library, or just `AnalogRead()`?)
* Maxbotix ultrasonic rangefinders (library link)
* Thermistors (obviously -- mention on-board Vdiv)
* Kipp & Zonen solar-radiation sensors (mention instrumentation amp)
<br/>
<br/>
<br/>


# Northern Widget prototypes

The following sensors are still in earlier stages of development.

## Calypso

*Dual-mode turbidity sensor: measures both transmission and scattering.* [<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget-Skunkworks/Project-Calypso)

## ThermalStake

*Rugged subsurface temperature profiler: thermal conduction and fluid flow.* [<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget-Skunkworks/Project-ThermalStake)

# Licenses

All designs and documentation are licensed under Creative Commons Attribution Share-Alike v4.0.

All code is licensed under the GNU GPL v3.0.

[![License: CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/80x15.png)](https://creativecommons.org/licenses/by-sa/4.0/)

[![License: GNU GPL 3.0](https://www.gnu.org/graphics/gplv3-or-later-sm.png)](https://www.gnu.org/licenses/gpl-3.0.en.html)
