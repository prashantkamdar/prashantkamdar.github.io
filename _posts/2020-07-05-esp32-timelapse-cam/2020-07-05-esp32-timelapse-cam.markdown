---
layout: post
title:  "ESP32 Timelapse Camera"
date:   2020-07-05 15:29:00 +0530
#categories: attiny85 maker
---

![esp32_timelapse_camera]({{site.baseurl}}/assets/images/esp32-cam/00.jpg)

<br><br>
The ESP32 camera module is an interesting little development board as it comes with a camera as well as an SD card slot.

This immediately gave me an idea to use it as a time lapse camera which can be powered by a battery (or power bank in my case) and left outside for hours/days.

While the camera quality isn't very great, this is a great little maker project.

While searching across the interwebs, I came across [bitluni's site](https://bitluni.net/) which already had exactly the same project.

This made my task infinitely simpler.


<br>
Now on to building this.

<br><br>
**Step 1:
The board**

The board alongwith camera module is relatively cheap and can be had at around $6-$9.

I am using an extremely cheap 4GB SD card along with it.

![camera]({{site.baseurl}}/assets/images/esp32-cam/01.jpg)

<br><br>
**Step 2:
Have the necessary tools around**

You need the following-
<ol>
<li>Arduino UNO to program the ESP32 module</li>
<li>Jumper wires to wire everything up</li>
<li>Soldering station</li>
<li>Wire strippers though optional, makes work much faster</li>
</ol>

![tools]({{site.baseurl}}/assets/images/esp32-cam/02.jpg)

<br><br>
**Step 3:
Write the code**

Again, this step was made really simple due to [bitluni's excellent work](https://github.com/bitluni/ESP32CamTimeLapse).

I used his above code and made changes as I felt necessary.

![code]({{site.baseurl}}/assets/images/esp32-cam/03.png)

<br><br>
**Step 4:
Wire the ESP32 with Arduino UNO**

There is no direct way to "upload" the code to the ESP32.

Hence, this is done via Arduino UNO board.

There are plenty of good circuit diagrams out there; I followed this one:

![wiring]({{site.baseurl}}/assets/images/esp32-cam/esp32wiring.jpg)

<br><br>
**Step 5:
Connect it all up**

![connecting]({{site.baseurl}}/assets/images/esp32-cam/04.jpg)

<br><br>
**Step 6:
Upload the code**

Once the wiring is done, you can choose the right settings in the Arduino UNO and upload the code.
<ol>
<li>Board > ESP32 ”Wrover Module”</li>
<li>Flash Mode > QIO</li>
<li>Flash Frequency > 40MHZ</li>
<li>Partition Scheme > Huge App (3mb No OTA)</li>
<li>Upload speed > 115200</li>
<li>Programmer > AVR ISP</li>
</ol>

![uploading_code]({{site.baseurl}}/assets/images/esp32-cam/05.jpg)

<br><br>
**Step 7:
Testing?**

At this moment, the ESP32 should have already joined your wifi network and logs should start appearing in the Arduino UNO's serial monitor.

However, I started seeing the following error on the console.

While this error sometimes means that the board is defective, it is also sometimes an indication of the board not getting enough current.

The ESP32 needs a lot of current when it tries to join the wifi.

Since I was powering the ESP32 using my computer's USB port, I felt this could be one of the reasons why I am getting the error.

To remedy this, I decided to do the testing with an external power source.

But since the ESP32 doesn't have a micro usb port, this isn't as straightforward.

![error]({{site.baseurl}}/assets/images/esp32-cam/06.png)

<br><br>
**Step 8:
Find a cable**

I am sure everyone has some version of this container in their homes by now :)

![finding_cable]({{site.baseurl}}/assets/images/esp32-cam/07.jpg)

<br>
I found a small cable with good thickness

![cable_found]({{site.baseurl}}/assets/images/esp32-cam/08.jpg)

<br><br>
**Step 9:
Strip the cable**

![stripping]({{site.baseurl}}/assets/images/esp32-cam/09.jpg)

<br>
Using the wire strippers to strip the red & black insulation to expose the leads, you need to be very careful.

A trick I had learned a long time ago was to rather than using wire strippers here, you can simply burn off the insulation.

This isn't recommended where voltage or current demands are high as it might affect the copper badly, but for smaller projects like this one, it is ok.

![stripping_leads]({{site.baseurl}}/assets/images/esp32-cam/10.jpg)

<br><br>
**Step 10:
Soldering**

Gotta solder the USB cable with a jumper pin which can be connected to the ESP32 module.

![soldering]({{site.baseurl}}/assets/images/esp32-cam/11.jpg)

<br>
Use shrink tubing to ensure the solder joint doesn't come off easily.

![cable_done]({{site.baseurl}}/assets/images/esp32-cam/12.jpg)

Looks pretty!

<br><br>
**Step 10:
Testing the cable**

Testing the cable by using a power bank.

Ensure you are getting a constant 5 volts.

![testing_the_cable]({{site.baseurl}}/assets/images/esp32-cam/13.jpg)

<br><br>
**Step 11:
All ready!**

Connect the female jumper wires to the ESP32 5V and ground pins.

Don't mix up the polarity as that can fry your board!

I tested the polarity using a multimeter twice before I connected.

![all_connected]({{site.baseurl}}/assets/images/esp32-cam/14.jpg)

<br><br>
**Step 12:
Testing**

Since the board is no longer connected to your computer (via Arduino UNO), you cannot monitor the logs using the serial monitor to find the IP address of the board.

Hence, I went to my router's status page to see all the connected devices on my network to find the IP address of the board.

Once found, I keyed in the address in a browser and voila!

You can use this page to setup the different parameters of picture taking.

![testing]({{site.baseurl}}/assets/images/esp32-cam/15.jpg)

<br><br>
**Step13:
Movie creation**

I have set up the camera to take a picture every 4 seconds.

Once enough time is passed, you can take out the micro SD card from the module, and put it in your PC to see your results.

I took over 400 images for the demo

![images]({{site.baseurl}}/assets/images/esp32-cam/16.jpg)

<br>

To convert them, you can use a freeware tool called ffmpeg.

I settled on using 15 frames per second with medium quality video, but you can experiment with whatever settings works best for you.

![converting]({{site.baseurl}}/assets/images/esp32-cam/17.png)

<br><br>
**Demo timelapse movie**

<video controls>
  <source src="/assets/images/esp32-cam/demo.mp4" type="video/mp4">
    Your browser does not support HTML video.
</video>

<br><br>
References:

<https://bitluni.net/esp32camtimelapse>

<https://github.com/bitluni/ESP32CamTimeLapse>

<https://technoreview85.com/how-to-program-esp-32-cam-using-arduino-uno-board/>