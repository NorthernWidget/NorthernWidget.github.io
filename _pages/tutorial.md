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

## Helpful external Arduino tutorials and documentation

We use Arduino because it is a popular system with a large user base, mature software libraries, and extensive support! The information here is tailored a bit more to our sensors and data loggers, but is not as extensive as help available elsewhere on the internet. Here are some curated links to guides:

**Adafruit: *Learn Arduino***
* [Lesson 0](https://learn.adafruit.com/ladyadas-learn-arduino-lesson-number-0)
* [Lesson 1](https://learn.adafruit.com/ladyadas-learn-arduino-lesson-number-1)
* [Lesson 2](https://learn.adafruit.com/ladyadas-learn-arduino-lesson-number-2)

**[Official Arduino programming reference](https://www.arduino.cc/reference/en)**

**[Adafruit: *Adding Third-Party Boards*](https://learn.adafruit.com/add-boards-arduino-v164)**

## Arduino software, libraries, and boards definitions

*Arduino is an open-source electronic hardware development platform. For more information on Arduino, go to https://www.arduino.cc/.*

### Download and install the Arduino IDE

The Arduino IDE (Integrated Development Environment) is the current programming
environment we use to write and upload programs to the Northern Widget sensors
and data loggers. (Other options exist, but this is the most beginner-friendly.)
We haven't yet tested the brand-new web editor, so we'll be suggesting an
old-fashioned download. And if you're deploying these in the field, you'll need
the downloaded version! Go to
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

We have a set of custom firmware libraries designed to make your life easier.
The only step that you have to take is to install them. Go to
[https://github.com/NorthernWidget/NorthernWidget-libraries] and follow the
instructions in the README to add these to your `libraries` folder.

# Step 2: Programming

Materials needed:
* [Arduino](https://www.arduino.cc/)-compatible device
* A programming cable, which can be:
  * A USB cable that can attach to this device (current Northern Widget data loggers use a USB A to micro-B cable, similar to all but the newest Android smartphones)
  * An in-system programmer that attaches to a 6-pin header on the board

If you are just programming an Arduino board or data logger, which already has a bootloader installed (if you don't know what this is, it probably has it), then all you need is the board and the USB cable.

## The basics of uploading programs

Arduino programs, often called "sketches", are how you tell An Arduino device what to do. Here is some information to get you started.

### Definitions

* **Microcontroller**: A computer chip that integrates a processor, memory, and methods to take electrical inputs and send electrical signals.
* **Software**: A program that involves active changes and interactions. This typically exists on a computer and runs within an operating system. An example here is the Arduino IDE.
* **Firmware**: A program that is uploaded once to a computer or microcontroller and then executes the same set of commands. Any code that you upload to an Arduino-compatible device is an example of firmware.
* **Sketch**: The Arduino name for the C++ source code in which you write a program
* **Bootloader**: A small piece of firmware that is installed in a specific portion of the microcontroller's memory. In the case of Arduino-compatible devices, this is almost always to allow the device to be programmed via USB.
* **Function**: A defined section of code that completes some task and optionally returns output
* **Class**: A container that holds functions and variables. An **object** is a particular instance of a class (e.g., the class is Cap'n Crunch (or pick another ceral or item); my box of Cap'n Crunch is an object).
* **Library**: A piece of pre-written code that you can `#include` within a program (such as an Arduino *sketch*) in order to use its functions. This typically helps to shorten the length of your sketches by hiding a lot of complicated code and exposing it as functions that can be called in just a single line of code.

### A new program

When you open the Arduino IDE, you will see a default blank "sketch":
```c++
void setup() {
  // put your setup code here, to run once:

}

void loop() {
  // put your main code here, to run repeatedly:

}
```

`setup()` and `loop()` are both **functions**. These are specific sets of code that are executed when their names are called in the code. These two functions are special in that:

1.  Every Arduino program much have them.
2.  They do not need to be called by code that you write: Arduino automatically interprets and, indeed, requires that these be included.
  *   Everything inside the curly braces after `setup()` is run once, when the data logger starts running
  *   Everything inside the curly braces after `loop()` is run continuously, after `setup()`, until the Arduino device loses power.

In addition:
* You may include other code libraries and declare variables before these functions.
* You may include additional functions after these functions.

### Uploading code to the Arduino-compatible device

Once your code is written -- either as a copy/paste of this or as your own -- save your code. All Arduino sketches need to be within their own folder; the Arduino IDE will ensure that this happens. After saving, you can upload in one of two ways:

If you upload the above code to an Arduino device, it will do nothing, because the code contains no instructions.

#### USB

If you are programming the board via USB, hit the "upload" button (right arrow) to load the code to the board. (The check mark to the left will test if your code compiles.)

![Upload sketch (program) to board.](https://github.com/NorthernWidget/ALog/raw/master/doc/figures/ArduinoScreenshots/Uploading.png "Uploading sketch (program) to board.")

***Upload the Arduino sketch to the board.*** *(Pay no mind to the specific text; this comes from our old [ALog data logger](http://github.com/NorthernWidget/ALog).)*

#### In-system programmer

***Important note for Linux users:*** You must supply permissions to the Arduino IDE for it to be able to use the ICSP, or you will have to run it using `sudo`. The former option is better; the latter is easier in the moment.

Otherwise, you may be uploading via a special device called an "in-circuit system programmer" (or just "in-system programmer, or "ISP") that attaches to a 2x3 header, with either 2.54 mm (0.1") or 1.27 mm (0.05") spacing. In this case, you may be:
* uploading a bootloader, or
* uploading firmware for a sensor.

Many devices exist to upload bootloaders or firmware, including:
* The official [AVR ISP mkII](http://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-42093-AVR-ISP-mkII_UserGuide.pdf) (no longer produced but available used)
* Using an [Arduino as an ISP](https://www.arduino.cc/en/tutorial/arduinoISP)
* The versatile [Olimex AVR-ISP-MK2](https://www.olimex.com/Products/AVR/Programmers/AVR-ISP-MK2/open-source-hardware)
* The [Adafruit USBtinyISP](https://www.adafruit.com/product/46)

In either case, you follow these two steps:

1. Plug your ISP of choice into your computer (via a USB cable) and onto the 6-pin header. There are two ways to place it on; the header is aligned such that the ribbon cable should be facing away from the board while programming. If this fails without being able to upload, try flipping the header around. This should both power the board and provide communications.
2. Go to Tools --> Programmer and select the appropriate programmer based on what you are using.

If you are uploading firmware using the programmer, you then go to Sketch --> Upload Using Programmer. After several seconds, you learn whether you succeeded or failed. Hopefully it worked!

![Upload using programmer](https://media.githubusercontent.com/media/NorthernWidget-Skunkworks/Project-Symbiont-LiDAR/master/Documentation/images/UploadUsingProgrammer.png)

Otherwise, if you are uploading a bootloader, you go to Tools --> Burn Bootloader. If you are doing this on an Arduino or data-logger board, you may have to plug in the USB cable to supply enough power and to go to Tools --> Port and select the proper serial port for your device. (It is not programmed via the serial port though, so I (Wickert) do not understand why you sometimes have to do this.)

In either case, lights should flash on the programmer and board and a message should appear in the Arduino IDE that tells you whether or not you have succeeded. If it fails, try these approaches in order:
1. Try flipping around the ISP (also called "ICSP") attachment,
2. Make sure that all of your USB-cable connections are secure,
3. Desperate internet searching.

## Programming Northern Widget sensors

We include specific instructions for uploading firmware (or, rarely, a bootloader) to Northern Widget sensors on the `README.md` pages that appear in our repositories on GitHub. Those that include this information include:
* [Project Haar](https://github.com/NorthernWidget-Skunkworks/Project-Haar): ruggedized and waterproof atmospheric temperature, pressure, and relative-humidity sensor
* [Project Walrus](https://github.com/NorthernWidget-Skunkworks/Project-Walrus): submersible and waterproof sensor to measure pressure and temperature; typically used for water level but can also provide atmospheric conditions.
* [Project Symbiont](https://github.com/NorthernWidget-Skunkworks/Project-Symbiont-LiDAR): LiDAR interface for distance and orientation measurements.


# Step 3: Test logging

# Step 4: Field assembly

# Step 5: Deployment
