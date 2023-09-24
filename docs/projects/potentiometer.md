# What is a potentiometer 

* Okay, imagine you have a special knob on a toy or a radio. This knob lets you control how loud the music is or how bright the light is. You can turn it one way to make the music louder or the light brighter, and the other way to make it softer or dimmer. This special knob is like a potentiometer.

* But what's inside this knob that makes it work? Well, inside, there's a twisty wire or track, like a tiny path. When you turn the knob, a little metal thingy with a pointy end, like a tiny robot finger, moves along this path.

* Here's where the magic happens: depending on where that metal finger is on the path, it changes how much electricity can flow through it. When the finger is at one end, very little electricity can get through, so the music is quiet or the light is dim. When the finger is at the other end, lots of electricity can flow, so the music is loud or the light is bright.

* So, a potentiometer is like a magical knob that helps you control things like volume or brightness by changing how much electricity can go through it when you turn it. It's like a secret volume button for your toys and gadgets!

* Now lets get started and connect our potentiometer to our Pico and try to read the value of the potentiometer 

* Lets start by writing code 

```py
from machine import Pin,PWM
import utime
import random

analog_value = machine.ADC(28)
if __name__ == "__main__":
    while True:
        # range of random numbers
        value = analog_value.read_u16()
```

```python
from machine import Pin,PWM
import utime
import rando
```

```py
Led_R = PWM(Pin(2))
Led_G = PWM(Pin(3))
Led_B = PWM(Pin(4))
```

```py
analog_value = machine.ADC(28)

# Define the frequency 
Led_R.freq(2000)   
Led_G.freq(2000)   
Led_B.freq(2000)   
if __name__ == "__main__":
    while True:
        # range of random numbers
        value = analog_value.read_u16()
        R=value
        G=value
        B=value
        print(R,G,B)   
        Led_R.duty_u16(R)
        Led_G.duty_u16(G)
        Led_B.duty_u16(B) 
        utime.sleep_ms(100)
```
