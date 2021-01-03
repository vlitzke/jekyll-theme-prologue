
https://learn.adafruit.com/adxl345-digital-accelerometer

ADXL345 Digital Accelerometer
How it Works:
MEMS - Micro Electro-Mechanical Systems
The sensor consists of a micro-machined structure on a silicon wafer. The structure is suspended by polysilicon springs which allow it to deflect smoothly in any direction when subject to acceleration in the X, Y and/or Z axis. Deflection causes a change in capacitance between fixed plates and plates attached to the suspended structure. This change in capacitance on each axis is converted to an output voltage proportional to the acceleration on that axis.

I2C Wiring:
The ADXL345 Breakout has an I2C address of 0x53. It can share the I2C bus with other I2C devices as long as each device has a unique address. Only 4 connections are required for I2C communication:
GND->GND
VIN->+5v
SDA->SDA (Analog 4 on "Classic Arduinos")
SCL->SCL (Analog 5 on "Classic Arduinos")

I2C is a serial protocol for two-wire interface to connect low-speed devices like microcontrollers, EEPROMs, A/D and D/A converters, I/O interfaces and other similar peripherals in embedded systems (https://i2c.info/)


https://www.youtube.com/watch?v=KMhbV1p3MWk
https://forums.adafruit.com/viewtopic.php?f=45&t=76545
https://learn.adafruit.com/adafruit-ultimate-gps/resources
https://www.youtube.com/watch?v=fvOAbDMzoks
https://www.youtube.com/watch?v=p27rk7AyUJQ&feature=emb_logo
https://learn.adafruit.com/circuitpython-hardware-lis3dh-accelerometer/hardware

https://learn.adafruit.com/adafruit-feather-m4-express-atsamd51/setup
Arduino IDE Setup

The first thing you will need to do is to download the latest release of the Arduino IDE. You will need to be using version 1.8 or higher for this guide
After you have downloaded and installed the latest version of Arduino IDE, you will need to start the IDE and navigate to the Preferences menu. You can access it from the File menu in Windows 

We will be adding a URL to the new Additional Boards Manager URLs option. The list of URLs is comma separated, and you will only have to add each URL once. New Adafruit boards and updates to existing boards will automatically be picked up by the Board Manager each time it is opened. The URLs point to index files that the Board Manager uses to build the list of available & installed boards.

To find the most up to date list of URLs you can add, you can visit the list of third party board URLs on the Arduino IDE wiki. We will only need to add one URL to the IDE in this example, but you can add multiple URLS by separating them with commas. Copy and paste the link below into the Additional Boards Manager URLs option in the Arduino IDE preferences.

https://adafruit.github.io/arduino-board-index/package_adafruit_index.json
Here's a short description of each of the Adafruit supplied packages that will be available in the Board Manager when you add the URL:

Adafruit AVR Boards - Includes support for Flora, Gemma, Feather 32u4, Trinket, & Trinket Pro.
Adafruit SAMD Boards - Includes support for Feather M0 and M4, Metro M0 and M4, ItsyBitsy M0 and M4, Circuit Playground Express, Gemma M0 and Trinket M0
Arduino Leonardo & Micro MIDI-USB - This adds MIDI over USB support for the Flora, Feather 32u4, Micro and Leonardo using the arcore project.
If you have multiple boards you want to support, say ESP8266 and Adafruit, have both URLs in the text box separated by a comma (,)

Once done click OK to save the new preference settings. Next we will look at installing boards with the Board Manager.

Now continue to the next step to actually install the board support package!

https://learn.adafruit.com/adafruit-feather-m4-express-atsamd51/using-with-arduino-ide
The Feather/Metro/Gemma/QTPy/Trinket M0 and M4 use an ATSAMD21 or ATSAMD51 chip, and you can pretty easily get it working with the Arduino IDE. Most libraries (including the popular ones like NeoPixels and display) will work with the M0 and M4, especially devices & sensors that use I2C or SPI.

Now that you have added the appropriate URLs to the Arduino IDE preferences in the previous page, you can open the Boards Manager by navigating to the Tools->Board menu.
Install SAMD Support
First up, install the latest Arduino SAMD Boards (version 1.6.11 or later)

You can type Arduino SAMD in the top search bar, then when you see the entry, click Install

Install Adafruit SAMD
Next you can install the Adafruit SAMD package to add the board file definitions

Make sure you have Type All selected to the left of the Filter your search... box

You can type Adafruit SAMD in the top search bar, then when you see the entry, click Install

Even though in theory you don't need to - I recommend rebooting the IDE

Quit and reopen the Arduino IDE to ensure that all of the boards are properly installed. You should now be able to select and upload to the new boards listed in the Tools->Board menu.

Select the matching board,
