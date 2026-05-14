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
excerpt: "Field-capable sensors with software and firmware libraries.<br/>
          Designed to interface with any Arduino-compatible device.<br/>
          ***Open-source field science.***"
---

# Northern Widget sensors

## Apis

*Measure range and orientation with a Garmin LiDAR Lite — power management, firmware watchdog, and MEMS accelerometer onboard.*
[<i class="fab fa-fw fa-github"></i> Hardware](https://github.com/NorthernWidget/Project-Apis)
&nbsp;|&nbsp;
[<i class="fab fa-fw fa-github"></i> Library](https://github.com/NorthernWidget/Apis_Library)
&nbsp;|&nbsp;
[<i class="fas fa-fw fa-book"></i> API reference](https://docs.northernwidget.com/Apis_Library/)

<img src="https://raw.githubusercontent.com/NorthernWidget/Project-Apis/master/Documentation/images/SymbiontLiDAR_v010_top_annotated_20210408.png" alt="Apis board, annotated" width="480"/>

<img src="https://raw.githubusercontent.com/NorthernWidget/Project-Apis/master/Documentation/images/Perspective_view_installed_2019-09-14_15.30.02.jpg" alt="Apis installed in the field" width="480"/>

<br>


# Skunkworks sensors

*These sensors are in active development. They work, but documentation, packaging, and support are still catching up.*

## Walrus

*Measure water levels (or atmospheric pressure) and temperature with this encapsulated sensor.*
[<i class="fab fa-fw fa-github"></i> Hardware](https://github.com/NorthernWidget-Skunkworks/Project-Walrus)
&nbsp;|&nbsp;
[<i class="fab fa-fw fa-github"></i> Library](https://github.com/NorthernWidget-Skunkworks/Walrus_Library)

<img src="https://media.githubusercontent.com/media/NorthernWidget-Skunkworks/Project-Walrus/master/Documentation/images/Walrus_PTH_v000_with_enclosure_and_scale_cleaned_background_20200428.png" alt="Walrus" width="480"/>


## Haar

*Waterproof atmospheric temperature, pressure, and relative humidity sensor.*
[<i class="fab fa-fw fa-github"></i> Hardware](https://github.com/NorthernWidget-Skunkworks/Project-Haar)
&nbsp;|&nbsp;
[<i class="fab fa-fw fa-github"></i> Library](https://github.com/NorthernWidget-Skunkworks/Haar_Library)

<img src="https://media.githubusercontent.com/media/NorthernWidget-Skunkworks/Project-Haar/master/Documentation/images/Haar_v010_and_housing_exploded_20200228.png" alt="Haar" width="480"/>


## Libelle

*Spectrally resolved shortwave (solar) radiation sensor (pyranometer).*
[<i class="fab fa-fw fa-github"></i> Hardware](https://github.com/NorthernWidget-Skunkworks/Project-Libelle)
&nbsp;|&nbsp;
[<i class="fab fa-fw fa-github"></i> Library](https://github.com/NorthernWidget-Skunkworks/Libelle_Library)

<img src="/assets/images/DysonDeployed_Ecuador_2020-01-14_11.55.11_modified.jpg" alt="Libelle shortwave radiation sensor deployed in Ecuador" width="480"/>
<br/>
<br/>


## Liasis

*Longwave radiation sensor (pyrgeometer).*
[<i class="fab fa-fw fa-github"></i> Hardware](https://github.com/NorthernWidget-Skunkworks/Project-Liasis)
&nbsp;|&nbsp;
[<i class="fab fa-fw fa-github"></i> Library](https://github.com/NorthernWidget-Skunkworks/Liasis_Library)

<br/>
<br/>
<br/>


# Northern Widget prototypes

*The following sensors are still in earlier stages of development.*

## Calypso

*Dual-mode turbidity sensor: measures both transmission and scattering.* [<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget-Skunkworks/Project-Calypso)

## ThermalStake

*Rugged subsurface temperature profiler: thermal conduction and fluid flow.* [<i class="fab fa-fw fa-github"></i>](https://github.com/NorthernWidget-Skunkworks/Project-ThermalStake)


# I2C address reference

When connecting multiple sensors to a shared I2C bus, each device must have a unique address.
The table below lists the host-visible I2C address for every Northern Widget sensor.
*Last verified: 2026-05-14. Update this table whenever a sensor is added or a firmware default changes.*

| Device | Default address | Configurable? | Notes |
|--------|----------------|:-------------:|-------|
| [Apis](https://github.com/NorthernWidget/Project-Apis) | `0x50` | Yes | Write new address to register `0x0C`; firmware saves to EEPROM |
| [Haar](https://github.com/NorthernWidget-Skunkworks/Project-Haar) | `0x42` | No | Hardcoded in ATtiny firmware |
| [Libelle](https://github.com/NorthernWidget-Skunkworks/Project-Libelle) | `0x40` / `0x41` | Hardware | `0x40` face up; `0x41` face down |
| [Liasis](https://github.com/NorthernWidget-Skunkworks/Project-Liasis) | `0x4A` | No | Fixed by ADS1115 ADDR pin tied to GND |
| [T9602](https://github.com/NorthernWidget/T9602_Library) | `0x28` | No | Fixed chip address |
| [Tally](https://github.com/NorthernWidget-Skunkworks/Project-Tally) | `0x33` | Yes | Configurable via library |
| [Walrus](https://github.com/NorthernWidget-Skunkworks/Project-Walrus) | `0x4D` | In development | EEPROM-based configuration being added to I2C firmware |

The [Longbow](https://github.com/NorthernWidget-Skunkworks/Project-Longbow) RS-485-to-I2C bridge
takes a user-assigned address and is not listed above.

# Licenses

All designs and documentation are licensed under Creative Commons Attribution Share-Alike v4.0.

All code is licensed under the GNU GPL v3.0.

[![License: CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/80x15.png)](https://creativecommons.org/licenses/by-sa/4.0/)

[![License: GNU GPL 3.0](https://www.gnu.org/graphics/gplv3-or-later-sm.png)](https://www.gnu.org/licenses/gpl-3.0.en.html)
