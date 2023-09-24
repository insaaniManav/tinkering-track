# How does a piezo buzzer work

A piezo buzzer is a tiny sound-making device, like a little musical instrument. Here's how it works:

### Magic Crystal:
Inside the buzzer, there's a special crystal that can change its shape when you give it electricity. Think of it like a crystal that can grow and shrink really, really fast.

### Shaking and Vibrating: 
When you connect the buzzer to batteries or a circuit and turn it on, it's like waking up the crystal. It starts to shake and vibrate super, super fast, like a leaf in the wind.

### Making Sound: 
These super-fast shakes create wiggles in the air around the buzzer. These wiggles are like invisible waves, just like when you throw a pebble into a pond, and it makes ripples. These invisible waves are actually sound!

### Hearing the Sound: 
When these invisible sound waves reach your ears, they make your eardrums wobble a little bit. Your brain is like a super-smart detective that can understand these wobbles and tells you that you're hearing a sound.

So, the piezo buzzer is like a little magician. It uses a special crystal to shake and make invisible sound waves, and your ears and brain work together to turn those invisible waves into the sounds you hear. It's like having a tiny musical instrument that can play different tunes when you tell it to!

```python
from machine import Pin, PWM
from utime import sleep

analog_value = machine.ADC(28)
buzzer = PWM(Pin(15))

while True:
    value = analog_value.read_u16()
    buzzer.freq(int(value/14.0))
    print(value)
    buzzer.duty_u16(1000)
    sleep(0.1)
    buzzer.duty_u16(0)
```