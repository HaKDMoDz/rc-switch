# What kind of switch #

There are generally three common kinds of outlet switches. The first one is configured with a 10 pole DIP switch the other one is configured with two rotary (or sliding) switches with four setting possibilities each.

## Type A: 10 pole DIP switches ##

![http://rc-switch.googlecode.com/svn/wiki_images/typeA.png](http://rc-switch.googlecode.com/svn/wiki_images/typeA.png)

RCSwitch::switchOn("11001", "01000");

The first parameter represents the setting of the first 5 DIP switches. In this example it's ON-ON-OFF-OFF-ON.

The second parameter represents the setting of the last 5 DIP switches.  In this example the last 5 DIP switches are OFF-ON-OFF-OFF-OFF.

```
#include <RCSwitch.h>

RCSwitch mySwitch = RCSwitch();

void setup() {

  // Transmitter is connected to Arduino Pin #10  
  mySwitch.enableTransmit(10);
  
}

void loop() {

  mySwitch.switchOn("11001", "01000");

  // Wait a second
  delay(1000);
  
  // Switch off
  mySwitch.switchOff("11001", "01000");
  
  // Wait another second
  delay(1000);
  
}
```

## Type B: Two rotary/sliding switches ##

<img src='http://i9.instantgallery.de/s/su/sui/b0d5c19446819.png' alt='' border='0'>

RCSwitch::switchOn(4, 2);<br>
<br>
The first parameter represents the setting of the first rotary switch. In this example it's switched to "4" or "D" or "IV".<br>
<br>
The second parameter represents the setting of the second rotary switch. In this example it's switched to "2" or "B" or "II".<br>
<br>
<pre><code>#include &lt;RCSwitch.h&gt;<br>
<br>
RCSwitch mySwitch = RCSwitch();<br>
<br>
void setup() {<br>
<br>
  // Transmitter is connected to Arduino Pin #10  <br>
  mySwitch.enableTransmit(10);<br>
  <br>
}<br>
<br>
void loop() {<br>
<br>
  mySwitch.switchOn(4, 2);<br>
<br>
  // Wait a second<br>
  delay(1000);<br>
  <br>
  // Switch off<br>
  mySwitch.switchOff(4, 2);<br>
  <br>
  // Wait another second<br>
  delay(1000);<br>
  <br>
}<br>
</code></pre>

<h2>Type C: Intertechno</h2>

RCSwitch::switchOn('a', 1, 2);