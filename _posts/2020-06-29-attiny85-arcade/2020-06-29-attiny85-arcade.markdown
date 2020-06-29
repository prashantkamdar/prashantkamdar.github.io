---
layout: post
title:  "ATTiny85 Arcade"
date:   2020-06-29 13:29:00 +0530
#categories: attiny85 maker
---
A small, teeny-tiny console to play simple games using a microcontroller chip.

The ATTiny85 chip is small but powerful enough for this purpose.

It has 6 programmable IO pins, 512 Bytes of memory as well as RAM and runs off of a coin cell battery!

While this might not seem like a lot, it is plenty of juice to run simple programs including games with buttons.

Step 1:
Gather the components

![components]({{site.baseurl}}/assets/images/attiny85-arcade/01.components.JPG)

Step 2:
Have the necessary tools around

![tools]({{site.baseurl}}/assets/images/attiny85-arcade/02.required_tools.jpg)

Step 3:
Write the code

For this, I used an existing repo and made the changes as required.

![code]({{site.baseurl}}/assets/images/attiny85-arcade/03.coding_in_arduino.jpg)

Step 4:
Program the ATTiny85

There is no direct way to "upload" the code to the chip.

Hence, this is done via Arduino UNO board.

![upload_code]({{site.baseurl}}/assets/images/attiny85-arcade/04.programming_attiny85_via_arduino_uno.jpg)