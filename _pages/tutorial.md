---
defaults:
  # _pages
title: "Tutorial"
layout: splash
permalink: /tutorial/
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/LiningerGauge_DSC2135_NEF_embedded_modified.jpg
  #actions:
  #  - label: "Download"
  #    url: "https://github.com/mmistakes/minimal-mistakes/"
  caption: "Installing a stream gauge in Boulder County, Colorado, with
            members of the [Rapid Assessment of Rivers at Risk (RARR) team](http://www.rapidriverassessment.org/about.html).
            Left to right: [Dr. Natalie Kramer Anderson](https://nettleus.wixsite.com/natkrameranderson), [Prof. Katherine Linninger](https://www.colorado.edu/geography/katherine-lininger), and [Dr. Alice Hill](https://cires.colorado.edu/alice-f-hill). *Photo: A. Wickert.*"
excerpt: "**Set up the Arduino IDE, attach the sensors, and compile and
          upload some C++ code. Then off to the field!**<br>
          *Wishing you had a fancy graphical interface?<br>
          No such luck! It's an open-source project ;)*<br>
          But no worries either.
          ***This guide aims to carry you through.***"

---

*We know that this tutorial is terse! Don't worry: expanding it is on our to-do list. But we still weclome emails to prod -- or better, to help!*

# Overview

1. [Install requisite software](#step-1-install-software-packages-and-libraries)
    * Arduino IDE
    * Northern Widget libraries and dependencies
    * Northern Widget board and microcontroller definitions
    * (If needed for sensors) third-party microcontroller definitions
2. [Program your data logger and (if needed) sensor(s)](#step-2-programming)
    * Bootload the data logger (ICSP)
    * Burn firmware to sensors (ICSP)
    * Upload code to data logger (USB)
3. [Test and download/view data](#step-3-test-logging)
4. [Assemble the field housing and sensor mount](#step-4-field-assembly)
    * Enclosure
        * Drill holes for wires
        * Affix logger + batteries
    * Sensor mounting (posts, hose clamps, pipe, ...)
5. [Deploy](#step-5-deployment)

While superceded by more recent data-logger models, the [ALog
README](https://github.com/NorthernWidget/ALog) has some of our most complete
documentation. We're going to reuse some of it as we build this page, but want
to give you early go-getters a link to start you out.

# Step 1: Install software packages and libraries

## Arduino software, libraries, and boards definitions

### Download and install the Arduino IDE

The Arduino IDE (Integrated Development Environment) is the current programming
environment we use to write and upload programs to the ALog. (Other options
exist, but this is the most beginner-friendly.) We haven't yet tested the
brand-new web editor, so we'll be suggesting an old-fashioned download. And if
you're deploying these in the field, you'll need the downloaded version! Go to
[https://www.arduino.cc/en/Main/Software](https://www.arduino.cc/en/Main/Software).
(Windows users: go for the standard download, not the "app".) Get it, install
it, go.

### Set up the Northern Widget boards definitions

***This step is required only if you are using a Northern Widget data logger (Margay or Resnik). You may skip this step if you are using a standard Arduino or other board for which you already have support through the Arduino IDE.***

The Northern Widget boards are "third-party" Arduino boards, so you'll have to
set up support for these boards yourself. We've made a pretty thorough
walkthrough that you can view here at
[https://github.com/NorthernWidget/Arduino_Boards](https://github.com/NorthernWidget/Arduino_Boards).

### Add boards definitins for the ATTiny microcontrollers

***This step is required only if you have to upload firmware to Northern Widget sensors.***

Follow the [instructions to download and install ATTinyCore microcontroller
support](https://github.com/SpenceKonde/ATTinyCore) in the Arduino IDE.

### Install all Northern Widget libraries and their dependencies

We have a set of custom software libraries designed to make your life easier.
The only step that you have to take is to install them. Go to
[https://github.com/NorthernWidget/NorthernWidget-libraries] and follow the
instructions in the README to add these to your `libraries` folder.

# Step 2: Programming

# Step 3: Test logging

# Step 4: Field assembly

# Step 5: Deployment
