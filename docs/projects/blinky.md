# Blinking the Built-in LED
## Let's Make the built-in LED on the Raspberry Pi Pico blink on and off.

The raspberry pi pico has an LED built right into it so you don't have to do build a circuit and can get started quickly 

## Instructions:

* Insert the Raspberry Pi Pico into the breadboard.
* Step 1: Import Libraries
```python
import machine
import utime
```
Think of these lines as telling the computer to get ready for some special tasks. We're bringing in two friends, machine and utime, to help us. machine will help us control the Raspberry Pi Pico, and utime will help us with time-related things.

* Step 2: Setting up the LED Pin

```python
led = machine.Pin(25, machine.Pin.OUT)
```
Here, we're telling the Pico that we want to use one of its pins, called pin number 25, and we want to use it for "OUT," which means we can control it to make it turn on or off. Imagine this as choosing a switch that controls a light bulb.

* Step 3: Creating a Loop

```python
while True:
```
This line starts a loop, which is like a repeat button. It says, "Keep doing the things inside this loop forever."

* Step 4: Toggling the LED

```python
    led.toggle()
``` 
Inside the loop, we're telling the Pico to switch the LED on if it's off or off if it's on. It's like playing with a light switch – turning the light on and off. 
Here the led is an object , python has objects similar to how we have 

* Step 5: Sleeping (Waiting) for a Second

```python
    utime.sleep(1)
```
After we've switched the LED, we want to wait for 1 second before doing it again. This line is like telling the Pico to take a little nap for 1 second before repeating the loop. This is because if we dont tell the pico to take a nap , it will blink the LED so fast that we wont be able to see it 

And that's it! The code keeps making the LED blink on and off forever until you stop it.

You've just created a simple program to control the Raspberry Pi Pico's built-in LED. 








