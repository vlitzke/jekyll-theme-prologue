### Set up the circuitry for the two to talk


Before any coding is to be done, we have to attach the hookup wires. So far I placed my Feather M4 Express and ADXl345 Accelerometer on my breadboard (both have been soddered):
- Wire the GND pin of the ADXL345 to the GND Pin on the Feather M4 Express.
- Wire the VCC pin of the ADXL345 to the 3v3 Pin on the Feather M4 Express.
- Wire the SCL pin of the ADXL345 to the SCL Pin on the Feather M4 Express.
- Wire the SDA pin of the ADXL345 to the SCL Pin on the Feather M4 Express.

### Import existing libraries
1. Open up Arduino IDE --> Sketch -> Include Library -> Manage Libraries. 
2. Search for and install both “Adafruit ADXL345 by Adafruit” and “Adafruit Unified Sensor” libraries. 

### Code
At the very top of a new file, enter the following to include libraries:
```
#include <Wire.h>
#include <Adafruit_Sensor.h>
#include <Adafruit_ADXL345_U.h>
```

“Wire” library: Arduino to communicate with the accelerometer using the i2C serial protocol.\
“Adafruit_Sensor”: base of ADXL345 library.\
“Adafruit_ADXL345”: handles all code for interacting with the accelerometer from the microcontroller (reads back acceleration data from the sensor).

```
Adafruit_ADXL345_Unified accel = Adafruit_ADXL345_Unified(); //instantiates the Adafruit ADXL345 library to the “accel” variable

void setup(void) // run automatically when the Arduino powers on
{
   Serial.begin(9600); // allows Arduino to send information over a serial connection. In this function, we pass the baud rate of 9600.
   // utilize the “accel” objects “begin()” function to start its connection to our ADXL345 accelerometer.
   if(!accel.begin()) //if there is no connection
   {
      Serial.println("No ADXL345 sensor detected."); //print an error 
      while(1); //run an infinite loop to ensure we never enter the main loop. To exit, restart Arduino.
   }
}

void loop(void) //automatically runs after the “setup()” function has finished executing
{
   sensors_event_t event; //create a variable called “event” that utilizes the “sensors_event_t” struct
   accel.getEvent(&event); //retrieve data from accelerometer and put it into the “event” variable
   
   //print X, Y and Z acceleration values stored in “event” variable.
   Serial.print("X: "); Serial.print(event.acceleration.x); Serial.print("  ");
   Serial.print("Y: "); Serial.print(event.acceleration.y); Serial.print("  ");
   Serial.print("Z: "); Serial.print(event.acceleration.z); Serial.print("  ");
   Serial.println("m/s^2");
   delay(500); //delay loop for 500m
}
```

### Testing 
1. To upload the code to the microcontroller, click “Verify”, then “Upload”.
2. You can now see that the accelerometer is feeding real-time measurements through the serial monitor (click "Tools", then "Serial Monitor"). You can also look at the serial plotter, although both windows cannot be opened at the same time.


This information was taken from [this source](https://pimylifeup.com/arduino-accelerometer-adxl345/).
