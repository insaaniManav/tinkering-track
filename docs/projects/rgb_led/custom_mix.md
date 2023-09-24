# Color Mixing Fun

Now lets have some fun by combining the values 

Here's how you can connect the components:

* Connect the common anode of the RGB LED to the 3.3V pin on the Raspberry Pi Pico.
* Connect each of the color pins (red, green, and blue) of the RGB LED to separate PWM pins on the Raspberry Pi Pico. In the provided code, the connections are as follows:
* Red to GPIO pin 2
* Green to GPIO pin 3
* Blue to GPIO pin 4
* Connect the potentiometer as follows:
* Connect one end of the potentiometer to 3.3V on the Raspberry Pi Pico.
* Connect the other end of the potentiometer to the ground (GND) on the Raspberry Pi Pico.
* Connect the middle pin (the wiper) of the potentiometer to GPIO pin 28 (analog input).
* Code Explanation:
Now, let's break down the Python code step by step:

Import necessary libraries:

```python
from machine import Pin, PWM
import utime
import random
```

* Create PWM objects for controlling the RGB LED:

```python
Led_R = PWM(Pin(2))
Led_G = PWM(Pin(3))
Led_B = PWM(Pin(4))
```

This code initializes PWM objects for the red, green, and blue pins of the RGB LED.

Initialize an ADC (Analog-to-Digital Converter) object for reading the potentiometer:

```python
analog_value = machine.ADC(28)
```
This sets up an ADC to read analog values from pin 28.

Set the PWM frequency for each color:

```python
Led_R.freq(2000)
Led_G.freq(2000)
Led_B.freq(2000)
```
This code sets the PWM frequency for the RGB LED to 2000 Hz.

Main loop:

```python
while True:
```
The following code inside the loop repeats indefinitely:

Read the analog value from the potentiometer:

```python
value = analog_value.read_u16()
```
Assign the same value to R, G, and B, effectively making them all the same, which results in a grayscale color:

```python
R = value
G = value
B = value
```
Print the current values of R, G, and B:

```python
print(R, G, B)
```
Set the PWM duty cycle for each color based on the values of R, G, and B:
 
```python
Led_R.duty_u16(R)
Led_G.duty_u16(G)
Led_B.duty_u16(B)
```
Pause for 100 milliseconds before repeating the loop:

```python
utime.sleep_ms(100)
```

In this code, the potentiometer's position controls the intensity of all three RGB colors simultaneously, creating different shades of grayscale. You can turn the potentiometer to mix the colors and create various shades of white, black, and gray on the RGB LED.

