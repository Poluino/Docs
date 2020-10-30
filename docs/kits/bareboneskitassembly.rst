Barebones Kit Assembly
======================

.. image:: ./docs/images/barebones_comp_top.png
    :alt: Barebones Kit Assembeled

**Thank You** for purchasing our kit and supporting our project.

The Weather Station Project's Barebones Kit is the most basic kit avaliable.

It collects the data of **3** basic environmental features, namely;
 
#. Humidity
#. Temperature
#. Air Pressure

If you have purchased the Pre-Built version, go ahead and skip Steps 1 - 4

Step 1 - Opening the Package:
-----------------------------

First things first, open up the ziplock bags and sort the components. You should have the following :

#. 1x Barebones PCB
#. 1x 38P ESP32 Development board
#. 1x BME280 Environmental Sensor
#. 1x 4P – 6P Male Pin Header
#. 2x 19 Female Pin Sockets
#. 1x 4P Female Pin Sockets
#. 1x DC to USB Cable

Sort these into manageable portions for ease of retrival.

.. image:: ../docs/images/sorted_top.png
    :alt: Barebones Kit Sorted

Step 2 - Soldering the ESP32 Pin Sockets:
-----------------------------------------

Insert the included **2x 19 Pin Female Pin Sockets** onto the **ESP32**. This is helpful while soldering as it keeps them **straight and aligned**.

Use the below image as a reference:

.. image:: ../docs/images/hand_held_esp32.png
    :alt: Reference ESP32 image

Place the ESP32 and the Pin Sockets into the provided *Plated* Holes on the PCB. 

With the text upright, make sure the **Antenna** of the ESP32 is facing towards your **right**.

There is a text *"Antenna"* on the PCB to help you with alignment.

Use the below image as a reference:

.. image:: ../docs/images/esp32_alignment.png
    :alt: Alignment Reference Image

Turn the whole affair over and start soldering! 

Make sure each pin gets adequate solder. No more and certainly No less.

.. image:: ../docs/images/esp32_soldering.png
    :alt: ESP32 Soldering Reference

New To Soldering? No Problem! Our friends over at Adafruit Industries have an amazing tutorial on soldering the perfect joint.

Link to their post is here: `<https://learn.adafruit.com/adafruit-guide-excellent-soldering/making-a-good-solder-joint>`_

After soldering the pins, you can remove the ESP32 and keep it aside. 

**Caution: The ESP32's pins may be hot right after soldering. It is advised to keep it aside to cool for a few minutes and then proceed**

Step 3 - Soldering the other components:
----------------------------------------

Now you will need to solder the Barrel Jack and the 4 pin Female Pin Header for the Bosch Sensortec BME280 Environmental Sensor.

For a better understanding, lets break it down into two parts.

Part A - Soldering the Barrel Jack:
###################################

.. image:: ../docs/images/barrel_jack_soldering.png
    :alt: Barrel Jack Soldering Guide

Place the Barrel Jack on the PCB and start soldering the pins. 

*Word of Advice: The pins on the barrel jack are larger than the pins on the headers. This means you need to keep your soldering iron on the for a bit longer*

Part B - Soldering the Pin Header of the BME280 Sensor:
#######################################################

.. image:: ../docs/images/bme280_close.png
    :alt: BME280 Close

This is **VERY** important so read thoroughly.

If you intend to power your setup via a microUSB Cable (Standard Phone Charger), do the following:

#. Place the short end of the pins so that they go through the sensor's breakout board.
#. The letters **"GYBMEP"** should be on **top** and the long pins to the **bottom**.
#. The **"VIN"** pin should be the closest to the ESP32

This will give you room to fit the microUSB Cable and the BME280 sensor.

If you intend to use a Barrel Jack to USB cable, do the following:

#. Place the short end of the pins so that they go through the sensor's breakout board.
#. The words **"BME/BMP280"** should be on the **top** and the long pins to the **bottom**.
#. Essentially, the orientation of the Breakout board should be flipped but the **"VIN"** pin should be the closest to the ESP32 in both cases.

Part C - Soldering the Pin Socket:
##################################

Solder the 4 pin Female pin socket for the Bosch Sensortec BME280 Environmental Sensor in place using the same method used to solder the ESP32. 

Make sure the socket is seated well and is soldered on straight.

Step 4 - Final Inspection:
--------------------------
.. image:: ../docs/images/barebones_pcb_soldered.png
    :alt: Barebones Kit PCB Soldered

The PCB Should look like this after successful completion of the above steps.

Step 5 - Final Assembly:
------------------------

This step is common to both the Unassembeled Kit and the Pre-Built Kit.

* Place the ESP32 on to the PCB. With the text upright, make sure the **Antenna** of the ESP32 is facing towards your **right**. There is a text *"Antenna"* on the PCB to help you with alignment.

* Place the BME280 sensor on the 4 pin connector keeping in mind that the **VIN/3V3** pin is the closest to the ESP32.

The final result should look like this:

.. image:: ../docs/images/Front-White-Edited_3.png
    :alt: Assembled kit

Assembly is done! Give yourself a pat on the back! Now lets move on to coding. 

Visit the `</bareboneskitcoding>`_ to continue.