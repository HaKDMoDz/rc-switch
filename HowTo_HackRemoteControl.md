# Modification #

Open your remote control to take a look inside of it. There should be a encoder chip inside which is labeled with SC5262, HX2262 or PT2262. This chip generates a specific bit stream and sends it out to the transmitter part of the remote control through its DOUT (digital out) pin. What we want to do is to connect a Arduino instead of the built in encoder chip to the transmitter part.

The SC5262, HX2262 and PT2262 are compatible, so the DOUT pin is allways the 2nd pin from the upper right side

<img src='http://i5.instantgallery.de/s/su/sui/d554719426745.jpg' alt='' border='0'>


There is no need to physically replace the chip. It will do to solder a wire to that pin and connect it with any available I/O pin from the Arduino.<br>
<br>
Solder another wire to the positive pole (+) and the negative pole (-) of the battery holder. Altough a lot of transmitters were operated with a 12V battery they should also work with 5V, so I think it’s fine to power it directly from the Arduino (5V and GND pins).<br>
<br>
<br>
<h2>Additional Notes</h2>

In all remote controls (and yes, there is also one on the transmitter module - see attached image) there is actually a resistor between the controller chips digital out pin and the transmitter part.<br>
I know from users who hacked their remote controls and had problems with the range - it only worked on a distance of a couple of centimeters. The solution is to replace that resistor according to Ohm's law (there is a comment thread about that in the german version of the blog post):<br>
<br>
R(new) = U(new) x R(old) / U(old)<br>
<br>
So in a remote control which was powered with 12V before and having a 20k resistor it has to be replaced with a<br>
5V x 20k / 12V = 8,3k resistor.<br>
<br>
After all it might be neccessary to put a resistor between the arduino and the transmitter but I personally didn't encounter any problems without one using a couple of different transmitters.