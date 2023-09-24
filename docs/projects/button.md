# Button-controlled Built-in LED
## Objective: Control the built-in LED with a button using the Raspberry Pi Pico.

## Introduction to buttons
First, let's talk about what a button is. A button is like a tiny switch that you can press with your finger. When you press it, it can make something happen, like turning on a light or starting a game on your computer. There are some special parts inside a button that complete a circuit and complete the path for our electric friends to flow through.
It's like a magic doorbell for electronics!

## Pull up and pull down
Imagine you have a light switch in your room. When you turn the switch off, the light goes off, and when you turn it on, the light comes on, right? Now, think of electronic devices like your computer or phone. Inside them, there are tiny switches, just like your room's light switch. These switches help control how electricity flows.

Pull-up and pull-down resistors are like special helpers for these tiny switches inside electronics. They make sure that the switches have a definite state when you're not touching them. Let me explain how they work:

1. Pull-Up Resistor:

Think of a pull-up resistor like a tiny, invisible hand that gently pulls a switch towards turning it on (just like turning on your room's light). So, when you're not pressing the button or switch, the pull-up resistor makes sure it stays in the "on" state. 

2. Pull-Down Resistor:

Now, imagine a pull-down resistor as another tiny, invisible hand, but this time it gently pushes the switch toward turning it off (like turning off your room's light). So, when you're not pressing the button or switch, the pull-down resistor makes sure it stays in the "off" state.

In electronics, these resistors help prevent something called "floating." Floating is when the switch is in an uncertain state, like not knowing if your room's light is on or off when you haven't touched the switch. Pull-up and pull-down resistors make sure the switch has a clear and definite state when you're not using it.

So, pull-up and pull-down resistors are like little helpers that make sure electronic switches know whether to be "on" or "off" when you're not actively using them. They help keep things stable and prevent confusion in electronic circuits!

## Instructions:

* Set up the Raspberry Pi Pico on the breadboard.
* Connect one side of the push button to a GPIO pin (e.g., GPIO14) on the Pico.
* Connect the other side of the push button to GND (ground) on the Pico.
* Now lets write a Python program to read whether the buttton is pressed or not

* Step 1: Import Libraries
```python
import machine
import utime
```
We import the familiar libraries , these will help us connect to and control the pico
* Step 2: Now  we tell the pico that the button is connected to the GPIO pin 14 , notice how this time we are telling the Pico that it is an input device , remember the LED is an output device but an button is an input device.
```python
button = Pin(14, Pin.IN, Pin.PULL_DOWN)
```
* Now we will run the loop , and keep reading the value of the button , remember `0` means its off and `1` means the button is on

```python
while True:
    print(button.value())
    utime.sleep(0.1)
```

## What is an "if" Condition in Python:

Think of an "if" condition like a decision maker in your code. It's a way for your computer to make choices and take different actions based on certain conditions. Here's how it works in simple terms:

Imagine you have a robot friend, and you give them a rule: "If it's raining, take an umbrella. If it's not raining, leave the umbrella at home." Your robot friend follows this rule, and it's similar to how an "if" condition works in Python.

In Python, you can say something like this: "If a button is pressed, turn on the LED. If the button is not pressed, turn off the LED." The computer checks the button's condition (pressed or not pressed) and acts accordingly.
Imagine you have a magical button, and when you press it, a secret door opens. You want to write a program that controls a magical light (an LED) with this button.

Step 2 - Write the Code: Here's what your code might look like:

```python
Copy code
from machine import Pin
import time

# Create a button object and tell the computer where it's connected (e.g., pin 14)
button = Pin(14, Pin.IN, Pin.PULL_UP)
led = Pin(25, Pin.OUT)

while True:
    if button.value() == 0:  # If the button is pressed
        led.value(1)  # Turn on the LED
    else:
        led.value(0)  # If the button is not pressed, turn off the LED
    time.sleep(0.1)  # Wait for a moment
```
Step 3 - Try It Out: When you run this program, the LED will light up when you press the button and turn off when you release it. It's like controlling a magical light with your button!

Step 4 - Explore and Experiment: Now, you can start changing the code and making your own magical button adventures. Maybe the LED could change colors or blink in a pattern when you press the button. The "if" condition helps you make your computer do exciting things based on your button's actions!


