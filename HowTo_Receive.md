# Quick Start #

  * Connect a receiver to Pin #2 of your Arduino.
  * Upload the ReceiveDemo sketch which is provided in the libary.
  * Open the Serial Monitor (9600 baud)
  * Press any key on your remote

# Wiring #
![http://rc-switch.googlecode.com/svn/wiki_images/wiring_receiver2.png](http://rc-switch.googlecode.com/svn/wiki_images/wiring_receiver2.png)

(You can also use any other external interrupt pin of your Arduino instead of interrupt #0/Pin #2)

# How it works #

With the enableReceive method the Arduino will listen to incoming signals on the external interrupt (first parameter). Note that most boards have only two external interrupts: number 0 (on digital pin 2) and 1 (on digital pin 3) ([The Arduino Mega has some more](http://arduino.cc/en/Reference/AttachInterrupt)).

(... deprecated stuff removed here ...)

Please take a look at the ReceiveDemo examples which are delivered with the library.