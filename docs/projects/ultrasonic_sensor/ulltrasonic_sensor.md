## How Ultrasonic Sensors Work
You know how bats use squeaky sound waves to figure out where things are? Ultrasonic sensors work in a similar way!

An ultrasonic sensor has two important parts:

* An ultrasonic transmitter
* An ultrasonic receiver
* The transmitter sends out a very high frequency sound, called ultrasound, that humans can't hear. When the ultrasound hits an object, it bounces back to the sensor.

* The receiver listens for this reflected sound. By measuring how long it takes for the ultrasound to bounce back, the sensor can calculate how far away the object is!

* It's like how a bat sends out a squeak and listens for an echo to hunt insects in the dark. But ultrasonic sensors use super high-pitched sounds instead of bat squeaks.

So that's the basic idea - ultrasound is sent out and its echo is measured to detect objects and calculate distance. Pretty cool how sound can be used to "see" things just like bats do!

## The HCSR04 ultrasonic sensor 

If you look closely at the HC-SR04 sensor you will see that it has 2 pins apart from vdd and ground.

* The trig pin is the transmitter. We send a short pulse on this pin to trigger the sensor to send out an ultrasound burst.

* The echo pin is the receiver. It listens for the echo of the ultrasound coming back.

## Writing the code 

* Let's import the libraries that we will need
```py
from machine import Pin
import utime
```

* Next step is to setup the Pins , remember the trigger or the trig pin is the output pin but the echo pin which is going to read the reflected signal is the input pin 
```py
trigger = Pin(3, Pin.OUT)
echo = Pin(2, Pin.IN)
```
* Now , this is the tricky part , we start by turning on the trigger , first we set the trigger to low(turn it off), then we set it high(turn it on) , sleep for 5 micro-secs and then again set it low(turn it off), This way we send out the signal which we will then receive using the echo Pin
```py
while True:
   trigger.low()
   utime.sleep_us(2)
   trigger.high()
   utime.sleep_us(5)
   trigger.low()
```
Now we check the echo Value , if the value remains 0 that means the signal was not yet received , we record the value in microseconds for the time when the signal is turned off 
The second part is when the value becomes 1 which means the part where the sigtnal is received 
```py
   while echo.value() == 0:
       signaloff = utime.ticks_us()
   while echo.value() == 1:
       signalon = utime.ticks_us()
   timepassed = signalon - signaloff
```
```py
   distance = (timepassed * 0.0343) / 2
   print("The distance from object is ",distance,"cm")
   utime.sleep(1)

```