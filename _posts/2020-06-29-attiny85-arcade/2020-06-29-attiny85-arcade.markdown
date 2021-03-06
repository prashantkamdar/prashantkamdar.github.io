---
layout: post
title:  "ATTiny85 Arcade"
date:   2020-06-29 13:29:00 +0530
#categories: attiny85 maker
---

![attiny85_game_console]({{site.baseurl}}/assets/images/attiny85-arcade/00.final.jpg)

<br><br>
A small, teeny-tiny console to play simple games using a microcontroller chip.

The ATTiny85 chip is small but powerful enough for this purpose.

It has 6 programmable IO pins, 512 Bytes of memory as well as RAM and runs off of a coin cell battery!

While this might not seem like a lot, it is plenty of juice to run simple programs including games with buttons.

I followed the following simple circuit diagram found on the internet.

![circuit_diagram]({{site.baseurl}}/assets/images/attiny85-arcade/circuit_diagram.jpg)

<br>
Now on to building this.

<br><br>
**Step 1:
Gather the components**  

![components]({{site.baseurl}}/assets/images/attiny85-arcade/01.components.jpg)

<br><br>
**Step 2:
Have the necessary tools around**

![tools]({{site.baseurl}}/assets/images/attiny85-arcade/02.required_tools.jpg)

<br><br>
**Step 3:
Write the code**

For this, I used an existing repo and made the changes as required.

![code]({{site.baseurl}}/assets/images/attiny85-arcade/03.coding_in_arduino.jpg)

<br><br>
**Step 4:
Wire the ATTiny85 with Arduino UNO**

There is no direct way to "upload" the code to the chip.

Hence, this is done via Arduino UNO board.

![wiring]({{site.baseurl}}/assets/images/attiny85-arcade/04.programming_attiny85_via_arduino_uno.jpg)

<br><br>
**Step 5:
Upload the code**

Once the wiring is done, you can choose the right settings in the Arduino UNO and upload the code.

![uploading_code]({{site.baseurl}}/assets/images/attiny85-arcade/05.uploading_code.jpg)

<br><br>
**Step 6:
Testing on breadboard**

Now that the code is uploaded, test everything on a breadboard before making the circuit final.

I had to repeat steps 3 to 6 multiple times to get this right.

![testing]({{site.baseurl}}/assets/images/attiny85-arcade/06.actual_testing.jpg)

<br><br>
**Step 7:
Prepping the perfboard**

Cutting the perf board to size you would need to make the circuit more permanent.

![perfobard]({{site.baseurl}}/assets/images/attiny85-arcade/07.perfboard_size.jpeg)

<br><br>
**Step 8:
Soldering**

Place all the components in its place on the perfboard and solder them down.

![soldered]({{site.baseurl}}/assets/images/attiny85-arcade/08.basic_components_soldered.jpeg)

<br><br>
**Step 9:
Solder the interconnections**

Seems a lot complicated, but if you follow the circuit layout, should be straightforward

![all_soldered]({{site.baseurl}}/assets/images/attiny85-arcade/09.messy_soldering.jpeg)

<br><br>
**Step 11:
Install the battery**

![battery]({{site.baseurl}}/assets/images/attiny85-arcade/10.almost_there.jpg)

<br><br>
**Step 11:
Enjoy!**

<video width="768" height="512" controls poster="/assets/images/attiny85-arcade/attiny85-poster.jpg">
  <source src="/assets/images/attiny85-arcade/demo.mp4" type="video/mp4">
    Your browser does not support HTML video.
</video>

<br><br>
References:

<https://create.arduino.cc/projecthub/arjun/programming-attiny85-with-arduino-uno-afb829>

<https://circuitomaker.com/attiny-arcade/>

<https://github.com/webboggles/AttinyArcade>

<https://github.com/andyhighnumber/Attiny-Arduino-Games>