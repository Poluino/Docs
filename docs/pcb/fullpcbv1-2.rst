Full PCB V-1.2
==============


* This is the first complete version of the Weather Station PCB.

Getting Started
---------------

.. image:: /images/full_pcb_v1-2.png
    :alt: Full PCB 

This PCB Was Designed to be used with the **ESP32 SoC from Espressif Systems**. 
There are many versions of the Development Board which uses the ESP32, 
but this PCB Version is **ONLY** compatible with the *38 pin breadboard-friendly version*. 
You can find the Gerber files of this PCB at our *Github Page* `here <https://github.com/weatherstationproject/Kits>`_. 
The Open Source Electronics Design Software `KiCad <http://kicad-pcb.org/>`_ was used to design this PCB.
You can download it `here <https://kicad-pcb.org/download/>`_ if you wish to view/modify the source files.

PCB Attributes:
---------------

The PCB is designed to be used with a variety of **environmental sensors** 
which enables the user to effectively monitor their surroundings. 

The List of sensors include:

1. DHT11/22 Humidity and Temperature Sensor:
#########################################

The DHT11 / 22 Humidity and Temperature Sensor from Aosong is used in
the V 1.2 of the Weather Station PCB to measure the Relative Humidity 
of a Region. It is Directly embedded into the PCB along with the necessary 
passive components such as the 5K ohm Pull Up Resistors as well as a 100nF 
Ceramic Decoupling Capacitor. It is positioned in a way such that its measurements 
are not affected by the heat produced by other components.


.. image:: /images/dht22-digital-temperature-and-humidity-sensor-500x500.jpg
    :alt: DHT22 Sensor
    :width: 250

Datasheet: `<https://components101.com/sites/default/files/component_datasheet/DHT11-Temperature-Sensor.pdf>`_

2. BMP280 Pressure and Temperature Sensor:
##########################################

The BMP280 sensor from Bosch Sensortec is used to measure the Pressure and
Temperature. It has a wide range of measurement and a small footprint which
makes it apt for our use. It also has the synchronous, packet-switched,
single-ended I2C (InterIntegrated Circuit) serial communication which is an added
benefit.

.. image:: /images/BMP280_pic.jpg
    :alt: BMP280 Sensor
    :width: 250

Datasheet: `<https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bmp280-ds001.pdf>`_

3. MQ - 135 Air Quality Sensor:
###############################

The MQ – 135 from Winsen Electronics is used to measure the Air Quality.
It has a high sensitivity to ammonia gas, sulfide, benzene series, and steam,
also can monitor smoke and other toxic gases as well. It works on the TTL Logic
Level (0V – 5V)due to the integrated heater. This is converted to a more manageable
CMOS Logic Level (0V – 3.3V) using a MOSFET on the PCB.

.. image:: /images/MQ-135-Gas-Sensor.jpg
    :alt: MQ-135 Air Quality Sensor
    :width: 250

Datasheet: `<https://www.winsen-sensor.com/d/files/PDF/Semiconductor%20Gas%20Sensor/MQ135%20(Ver1.4)%20-%20Manual.pdf>`_

