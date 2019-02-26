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

utils/CapacitiveSensor
-----------------
blahblah

BLE  PeripheralBase
-----------------
blahblah

BLEuart
-----------------
blahblah

Button
-----------------

**Button(*pin*, *pressedValue*)**: (constructor) Creates a button object with the *pin* it is connected to, and the *pressedValue* it will have when pressed (pressed = 0 or pressed = 1).

**begin()**: initializes the button-related ~~stuff~~. Sets the *pin* the button is connected to as an input.

**pressed(*timeout*)**: stops the program until the state of the button changes to *pressed*. It will wait up to *timeout* milliseconds, or forever if *timeout* is 0.

**released(*timeout*)**: stops the program until the state of the button changes to *released* (not pressed). It will wait up to *timeout* milliseconds, or forever if *timeout* is 0.

**doublePressed(*timeout*, *tolerance*)**: stops the program until the button has been pressed 2 times. It will wait up to *timeout* milliseconds for the first clicking (forever if *timeout* is 0), and *tolerance* milliseconds for the second pressing.

**isPressed()**: returns the state of the button, *true* if the button is pressed, *false* if it is released.

**checkPress(*timeout*, *requiredState*)**: checks if the button's state has changed from other state, to *requiredState* within *timeout* milliseconds.

**getState()**: returns the current state of the *pin* connected to the button.

ButtonGroup
-----------------
**ButtonGroup()**: (constructor) Creates an object of a group of buttons to manage together (Up to 10).

**begin(*length*, *buttons[]*, *pressedValue*)**: Initializes the basic variables related to the group of buttons, with *length* as the amount of buttons in that group (no more than 10), in pins *button[]*, with *pressedValue* as the status of the pins when the buttons are pressed (pressed = 0 or pressed = 1).

**pressed(*timeout*)**: stops the program until the state of any of the buttons changes to *pressed* and returns the number of that button. It will wait up to *timeout* milliseconds (forever if *timeout* is 0), and if no button was pressed during this time, it will return -1.

**checkPressed(*timeout*, *requiredValue*)**: stops the program until the state of any of the buttons' state changes to *requiredValue* and returns the number of that button. It will wait up to *timeout* milliseconds (forever if *timeout* is 0), and if no button was pressed during this time, it will return -1.

CapacitiveSwitch
-----------------
blahblah

IMU
-----------------
blahblah

IRarray
-----------------
**IRarray(*IR1*, *IR2*, *IR3*)**: (constructor) Creates an object of 3 IR sensors to manage together. The default threshold value (the value at which the percieved value changes from 0 to 1) is 380, when using Arduino 101 this threshold needs to be set to 530 (use *setThreshold()*).

**readBinary()**: returns the decimal value of a the black and white values the IR is reading.

**translateBinary()**: translates the binary number in *toBinary* and returns its decimal value.

**readLine()**: checks if the robot is following the line and erturns the value of the new speed for the wheels.

**calculateVelocity(*s*)**: given the sum of the readings of teh IR sensors, calculates and returns the new speed to give the wheels (if the robot is going out of the line).

**test()**: reads and prints on the Serial Monitor the values that each individual IR is reading.

**setThreshold(*t*)**: sets to *t* the value of the threshold to interpret when the sensors change from 0 to 1.

Joystick
-----------------
**Joystick(*x*, *y*)**: (constructor) Creates a joystick object which X coordinate is connected to *x* pin and Y coordinate to *y* pin.

**getX()**: returns the value of the X coordinate read by the joystick.

**getY()**: returns the value of the Y coordinate read by the joystick.

Knob
-----------------
**Knob(*pin*)**: (constructor) Creates a knob object, associated to pin *pin*.

**getValue()**: returns the value of the knob.

**setLevels(*levels*)**: sets the highest value to map the readings from the knob.

**getLevel()**: gets the value of the knob mapped between 0 and *levels*.

LED
-----------------
**LED(*pin*)**: (constructor) Creates an LED object, associated to pin *pin*.

**begin()**: initializes the LED pin as an input.

**on()**: lights up the LED.

**off()**: turns off the LED.

**blink(*speed*, *times*)**: turs the LED on for *speed* milliseconds, then off for another *speed* milliseconds, and repeats it *times* times.

LightSensor
-----------------
blahblah

Melody & pitches
-----------------
blahblah

Player
-----------------
blahblah

TiltSwitch
-----------------
blahblah

UltrasonicSensor
-----------------
**UltrasonicSensor(*trig*, *echo*)**: (constructor) Creates an Ultrasonic object, with the trigger connected to *trig* pin, and the echo connected to *echo* pin.

**getDistance()**: returnd the distance measured by the sensor.

VUMeter
-----------------
blahblah

Wheels
-----------------
blahblah

piezoKnockSensor
-----------------
blahblah
