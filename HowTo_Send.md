

&lt;hr&gt;


If you intend to only operate some power sockets you should take a look at [this HowTo](http://code.google.com/p/rc-switch/wiki/HowTo_OperateLowCostOutlets).


&lt;hr&gt;



# Wiring #
![http://rc-switch.googlecode.com/svn/wiki_images/wiring_transmitter.png](http://rc-switch.googlecode.com/svn/wiki_images/wiring_transmitter.png)

(You can also use any other I/O Pin of your Arduino instead of Pin #10)
# Transmission methods #

There are three methods to send raw codes:

## Binary string ##

**send(string binaryCode)**

Sends the binary string.

```
#include <RCSwitch.h>

RCSwitch mySwitch = RCSwitch();

void setup() {
  mySwitch.enableTransmit(10);  // Using Pin #10
}

void loop() {
  mySwitch.send("000000000001010100010001");
  delay(1000);  
}
```

## Decimal value ##

**send(int decimalCode, int bitLength)**

Same as the first one but using the decimal value. The bit length is needed to zero-fill the binary code.

```
#include <RCSwitch.h>

RCSwitch mySwitch = RCSwitch();

void setup() {
  mySwitch.enableTransmit(10);  // Using Pin #10
}

void loop() {
  mySwitch.send(5393, 24);
  delay(1000);  
}
```

## Tri-state string ##

**sendTriState(string triStateCode)**

Tri-state codes are according to the data sheets of some encoding chips. Take a look at [this blogpost](http://sui77.wordpress.com/2011/04/12/163/) if you are interested in details.


```
#include <RCSwitch.h>

RCSwitch mySwitch = RCSwitch();

void setup() {
  mySwitch.enableTransmit(10);  // Using Pin #10
}

void loop() {
  mySwitch.sendTriState("00000FFF0F0F");
  delay(1000);  
}
```