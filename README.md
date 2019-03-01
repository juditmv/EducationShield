Education Shield for Arduino 101
========

The EducationShield library is intended to be used with the Education Shield provided in the CTC kit. It presents the necessary functions to interact with 3 and 4 pin connectors used in many sensors and actuators. Furthermore, it includes the functionality of SD-Card Reader and audio jack.

![alt tag](/EducationShield.jpg)

CTC101 Project
===========

CTC 101 is a modular STEAM program consisting of a toolbox with more than 25 projects and easy to assemble experiments, an online platform, and guided educators support.
The library is an educational project carried by Arduino LLC in Malmo. It is a collection of exercises commissioned by the Center of Resources for Education at Castilla La Mancha to be tried out in the classrooms during the Spring 2013. If you want to collaborate by adding translations to this collection of exercises, just send us a note to d.cuartielles AT arduino.cc.

Credits
===========

X. Yang, M. Johansson, C. Leivas, T. Hansson, L. Balboa, K. Engdahl, T. Pham , A. Goransson , D. Cuartielles 

Reference
==========

Reference section which explains the functions and constants defined in the library.


- [CapacitiveSensor](#capacitivesensor)
- [BLE PeripheralBase](#ble-peripheralbase)
- [BLEuart](#bleuart)
- [Button](#button)
- [ButtonGroup](#buttongroup)
- [CapacitiveSwitch](#capacitiveswitch)
- [IMU](#imu)
- [IRarray](#irarray)
- [Joystick](#joystick)
- [Knob](#knob)
- [LED](#led)
- [LightSensor](#lightsensor)
- [Melody and pitches](#melody-and-pitches)
- [Player](#player)
- [TiltSwitch](#tiltswitch)
- [UltrasonicSensor](#ultrasonicsensor)
- [VUMeter](#vumeter)
- [Wheels](#wheels)
- [PiezoKnockSensor](#piezoknocksensor)


## CapacitiveSensor

 **CapacitiveSwitch( *senderPin*, *receiverPin* )**: (constructor) Creates a CapacitiveSwitch object, where *senderPin* is the digital pin that acts as the sender (the same *senderPin* can be used as sender for several capacitive sensors), and *receiverPin* is the digital pin that acts as the receiver (each different sensor must have a different *receiverPin*).

 **config( *threshold* )**: If the capacitive sensor is to be used as a switch, this function can be used to configure the *threshold* (value for the capacitive switch to register a press). **test()** can be used to check the sensor readings first in order to decide the *threshold* value.

 **pressed( *timeout* )**: stops the program until the state of the sensor changes to *pressed*. It will wait up to *timeout* milliseconds, or forever if *timeout* is 0. Returns 1 if the sensor has been *pressed*, 0 if it's not.
 
 **released( *timeout* )**: stops the program until the state of the sensor changes to *released*. It will wait up to *timeout* milliseconds, or forever if *timeout* is 0. Returns 1 if the sensor has been *released*, 0 if it's not.
 
 
## BLE PeripheralBase


 **BLEPeripheralBase()**: (constructor) Creates a BLE objec in ordet to interact with the BLE characteristics.

 **setName(*name*)**: changes the name of the BLE to *name*.

 **searchCentral()**: returns true if the connection to the central is active, false otherwise.

 **connected()**: returnd true if the device is connected, false otherwise.


## BLEuart

blahblah

## Button


  **Button(*pin*, *pressedValue*)**: (constructor) Creates a button object with the *pin* it is connected to, and the *pressedValue* it will have when pressed (pressed = 0 or pressed = 1).

  **begin()**: initializes the button-related variables. Sets the *pin* the button is connected to as an input.

  **pressed(*timeout*)**: stops the program until the state of the button changes to *pressed*. It will wait up to *timeout* milliseconds, or forever if *timeout* is 0.

  **released(*timeout*)**: stops the program until the state of the button changes to *released* (not pressed). It will wait up to *timeout* milliseconds, or forever if *timeout* is 0.

  **doublePressed(*timeout*, *tolerance*)**: stops the program until the button has been pressed 2 times. It will wait up to *timeout* milliseconds for the first clicking (forever if *timeout* is 0), and *tolerance* milliseconds for the second pressing.

  **isPressed()**: returns the state of the button, *true* if the button is pressed, *false* if it is released.

  **checkPress(*timeout*, *requiredState*)**: checks if the button's state has changed from other state, to *requiredState* within *timeout* milliseconds.

  **getState()**: returns the current state of the *pin* connected to the button.

## ButtonGroup


  **ButtonGroup()**: (constructor) Creates an object of a group of buttons to manage together (Up to 10).

  **begin(*length*, *buttons[]*, *pressedValue*)**: Initializes the basic variables related to the group of buttons, with *length* as the amount of buttons in that group (no more than 10), in pins *button[]*, with *pressedValue* as the status of the pins when the buttons are pressed (pressed = 0 or pressed = 1).

  **pressed(*timeout*)**: stops the program until the state of any of the buttons changes to *pressed* and returns the number of that button. It will wait up to *timeout* milliseconds (forever if *timeout* is 0), and if no button was pressed during this time, it will return -1.

  **checkPressed(*timeout*, *requiredValue*)**: stops the program until the state of any of the buttons' state changes to *requiredValue* and returns the number of that button. It will wait up to *timeout* milliseconds (forever if *timeout* is 0), and if no button was pressed during this time, it will return -1.

## CapacitiveSwitch

**CapacitiveSwitch(*pin_in*, *pin*)**: (constructor) Creates an object of 3 IR sensors to manage together. The default threshold value (the value at which the percieved value changes from 0 to 1) is 380, w

**config(*threshold*)**:

**test()**:

**getValue(*min*)**:

**getState()**:

## IMU

blahblah

## IRarray


  **IRarray(*IR1*, *IR2*, *IR3*)**: (constructor) Creates an object of the 3 IR sensors connected to *IR1*, *IR2* and *IR3* to manage together. The default threshold value (the value at which the percieved value changes from 0 to 1) is 380, when using Arduino 101 this threshold needs to be set to 530 (use *setThreshold()*).

  **readBinary()**: returns the decimal value of a the black and white values the IR is reading.

  **translateBinary()**: translates the binary number in *toBinary* and returns its decimal value.

  **readLine()**: checks if the robot is following the line and erturns the value of the new speed for the wheels.

  **calculateVelocity(*s*)**: given the sum of the readings of teh IR sensors, calculates and returns the new speed to give the wheels (if the robot is going out of the line).

  **test()**: reads and prints on the Serial Monitor the values that each individual IR is reading.

  **setThreshold(*t*)**: sets to *t* the value of the threshold to interpret when the sensors change from 0 to 1.

## Joystick


  **Joystick(*x*, *y*)**: (constructor) Creates a joystick object which X coordinate is connected to *x* pin and Y coordinate to *y* pin.

  **getX()**: returns the value of the X coordinate read by the joystick.

  **getY()**: returns the value of the Y coordinate read by the joystick.

## Knob


  **Knob(*pin*)**: (constructor) Creates a knob object, associated to pin *pin*.

  **getValue()**: returns the value of the knob.

  **setLevels(*levels*)**: sets the highest value to map the readings from the knob.

  **getLevel()**: gets the value of the knob mapped between 0 and *levels*.

## LED


  **LED(*pin*)**: (constructor) Creates an LED object, associated to pin *pin*.

  **begin()**: initializes the LED pin as an input.

  **on()**: lights up the LED.

  **off()**: turns off the LED.

  **blink(*speed*, *times*)**: turs the LED on for *speed* milliseconds, then off for another *speed* milliseconds, and repeats it *times* times.

## LightSensor

  **LighSensor(*pin*)**: (constructor) Creates a LightSensor object connected to *pin*.

  **calibrate(*t*)**: uses the values obtained during *t* milliseconds to set the values of the base (highest value measured), and the threshold that will set where is teh line between measuring a 0 and a 1.

  **config(*basevalue*, *threshold*)**: allows to change the default values of the base and threshold manually.

  **showConfig()**: prints to the serial monitor the current configuration values of the sensor. Needs the Serial communication to be enabled (*Serial.begin* on the setup).

 **test()**: sends to the serial monitor the raw values received by the sensor. Useful in order to check the base and threshold valules. Needs the Serial communication to be enabled (*Serial.begin* on the setup).

 **getState()**: returns 0 if the measured value is between base and threshold, and 1 otherwise.

## Melody and pitches

In *pitches.h* there is a wide list with notes and their own frequency, useful whn playing melidies with the buzzer / piezo.

 **Melody(*pin*)**: (constructor) Creates a melody object, where the piezo / buzzer is connected to *pin* pin.

 **play(*length*, *notes[]*, *duration[]*, *speed*)**: plays the amount (*length*) of *notes* during their corresponding *duration* milliseconds, then pausing for some time depending on the*speed* (1 for normal speed, 0.5 to double the speed, etc).

  **beep(*note*, *length*)**: beeps the *note* during some ammount of time depending ont the *length*.

 **playTone(*note*, *length*)**: plays the *note* for *length* milliseconds.

 **effect_win()**: plays a happy, winning melody.

 **effect_gameover()**: plays a sad, game over melody.

 **effect_score()**: plays a short melody, great when scoring points/goals.

## Player

Uses pins 0, 1 (Serial communication), 3 (PWM for the jack connector), 4 and 10 (SD card reader).

  **Player()**: (constructor) Creates a player object.

  **begin()**: Initializes the player's tools: jack and SD card reader components (already inlcuded in the Education Shield board).

  **initPlayer()**: initializes pin 3.

  **initSD()**: initializes pins 4 and 10 and prepares the cadr to be read. Prints an error in case there is one.

  **printDirectory(*dir*, *numTabs*)**: prints in the Serial Monitor the names of the files and directories inside the *dir* directory of the SD card.

  **play(*name*)**: plays the file *name* through the jack connector. While it is playing it, the SErial monitor will print dots until the file is finished, when *"End of file. Thank you for listening!"* will be printed.

## TiltSwitch

 **TiltSwitch( *pin*, *pressedValue*)**: creates a TiltSwitch object, connected to *pin*, and the *pressedValue* it will have when upright (upright = 0 or upright = 1).

## UltrasonicSensor


  **UltrasonicSensor(*trig*, *echo*)**: (constructor) Creates an Ultrasonic object, with the trigger connected to *trig* pin, and the echo connected to *echo* pin.

  **getDistance()**: returnd the distance measured by the sensor.

## VUMeter


 **VUMeter()**: (constructor) Creates an VUMeter object with its LEDs connected to pins 2 to 6 (by default).

 **config(*length*, *pins[]*)**: allows to configure the amount of pins, *length*, connected to *pins[]* in the VUMeter.

 **begin()**: initializaes the VUMeter. Sets all the pins as outputs. Should be called in Setup.

 **on(*index*)**: turns on the LED in *index* position.

 **off(*index*)**: turns off the LED in *index* position.

 **scrollLeft(*speed*, *startIndex*)**:  from rigth to left and one a t a time, the LEDs will turn on for *speed* milliseconds then off.

 **scrollLeft(*speed*, *startIndex*)**:  from left to right and one a t a time, the LEDs will turn on for *speed* milliseconds then off.

 **fillFrom(*leftIndex*, *rightIndex*)**: will turn all LEDs off, then turn on just the ones from *leftIndex* to *rightIndex*.

 **fill(*lenght*):** will turn on *length* LEDs, starting from the 1st one (index 0).

 **blink(*index*, *speed*, *times*)**: will turn on the the LED in *index* position during *speed* milliseconds, then off during *speed* milliseconds.

 **blinkAll(*speed*, *times*)**: will turn on all LEDs during *speed* milliseconds, then off during *speed* milliseconds.

  **test()**: sends to the serial monitor the pin number of those used for the VUMete. Useful in order to check if the pins ans LEDs are connected correctly. Needs the Serial communication to be enabled (*Serial.begin* on the setup).

  **blinkOnce(*index*, *onTime*, *offTime*)**: turns the LED in *index* position on for *onTime* milliseconds, then off for *offTime* milliseconds.

  **clear()**: turns off all LEDs.

## Wheels


  **Wheels(*lpin*, *rpin*)**: (constructor) Creates an wheels object, with the left wheel connected to *lpin* and the right wheel connected to *rpin*.

  **begin()**: initializes the object, and should be called in setup. Sets the highest *top* speed, the lowest *low* speed, and the *still* (stoped) speed to their default values (120, 90 and 60).

  **go(*tl*, *tr*)**: gradually speeds up or slows down the robot from the previous speed to *tl* speed in the left wheel, and the *tr* speed on the rigth wheel.

  **goForward()**: gradually sets the corresponding speed on the wheels for the robot to move forward.

  **goBackwards()**: gradually sets the coresponding speed on the wheels for the robot to move backwards.

  **turnLeft()**: gradually sets the coresponding speed on the wheels for the robot to turn left.

  **turnRight()**: gradually sets the coresponding speed on the wheels for the robot to turn right.

  **standStill()**: gradually stops the wheels.

  **follow(*d*)**: changes the speed of the motors *d* units. Useful for the linefollower, where *d* would be the error when reading the line (how far away to the sides the robot is going), positive when the robot is diverting to the right of the line, 0 if it is on the line, and negative when it's diverting to the left.

## PiezoKnockSensor

  **PiezoKnockSensor(*pin*)**: (constructor) Creates an piezoKnockSensor object, connected to *pin*.

  **config(*threshold*, *debouceTime*)**: allows to change the default values of the *threshold* (value at which the board value changes from 0 to 1), and *debounceTime* to wait in order not to read the same knocking several times.

  **knocked(*timeout*)**: stops the program until the sensor is knocked or *timeout* milliseconds pass.

  **test()**: sends to the serial monitor the raw values received by the sensor. Useful in order to check the threshold and debouce time. Needs the Serial communication to be enabled (*Serial.begin* on the setup).
