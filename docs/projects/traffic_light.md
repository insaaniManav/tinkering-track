# Having fun with more than one LED

* Now Let's pull out the traffic light and start having fun with more LEDS 
* Start with placing the traffic light into to the breadboard 
* Now connect the pin labelled GND on the traffic light to the ground rail on the breadboard
* Now connect the rest of the pins to pin numbers 31, 32 and 34 on the PICO


## Building on your own
* Now let's refer to the old guide that we used to blink an LED and try to blink the RED LED on our own , now change the code to blink the green and then the yellow LED 


Hints : Remember the code we just implemented for blinking the LED on the raspberry pi pico , in this case we are just blinking an LED connected to the Pico , well this is a similar LED just connected to a different Pin !!


## Now let's have fun with more LEDs
* Blink all the three LEDs together
* Turn on Red , make the Red turn off , now turn on the yellow , turn it off and then turn on the green , turn it off . Repeat

// TODO : Add this to the parents guide 
```python 
from machine import Pin
import utime

red_led = machine.Pin(28, machine.Pin.OUT)
yellow_led = machine.Pin(27, machine.Pin.OUT)
green_led = machine.Pin(26, machine.Pin.OUT)


while True:
    red_led.value(1)
    utime.sleep(0.5)
    red_led.value(0)
    utime.sleep(0.5)
    yellow_led.value(1)
    utime.sleep(0.5)
    yellow_led.value(0)
    utime.sleep(0.5)
    green_led.value(1)
    utime.sleep(0.5)
    green_led.value(0)
    utime.sleep(0.5)
```
