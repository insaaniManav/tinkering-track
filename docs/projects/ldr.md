# Building a night light

## What is an LDR?
An LDR is a special kind of electronic component called a resistor. A resistor limits the flow of electricity in a circuit. Most resistors have a fixed resistance, meaning they always limit the flow by the same amount. But an LDR is different - its resistance changes depending on how much light shines on it. That's why it's called a light dependent resistor!

## How does an LDR work?
An LDR is made of a material that increases its resistance when light shines on it. So when it's dark, the LDR has a low resistance and allows electricity to flow easily. But when light shines on it, the resistance increases and blocks more of the electric current.

It's like a water hose - when you squeeze the hose, less water can flow through. More light makes the LDR "squeeze" the electric flow to limit it.

## What is LDR used for?
The changing resistance of the LDR when light shines on it allows it to be used in all kinds of fun circuits and devices!

For example, you could use an LDR to make a nightlight that turns on automatically when it gets dark. Or you could use it to create an alarm that goes off if a light is turned on. Lots of electronic gadgets use LDRs to detect light levels and react.

So okay so now lets build this project out 

## Building the project 

Connecting an LDR to a Raspberry Pi Pico
First, we need to connect the LDR to the Raspberry Pi Pico.

## Connect LDR to pin GP15
```py
ldr = machine.ADC(pin=15)
```
This line sets up the LDR so that we can read its analog voltage value on pin GP15 of the Pico.

## We'll the Use the LED connected to the raspberry pi pico on pin 25 
```py
led = machine.Pin(25, machine.Pin.OUT)
```
Reading the LDR
Now we can read the analog voltage from the LDR:

## Read analog voltage from LDR  
ldr_value = ldr.read_u16()
This will give us a number between 0-65535 depending on how much light is hitting the LDR.

## Controlling the LED
We'll turn the LED on if it's dark (LDR voltage is low):

```py
if ldr_value < 1000:
  led.value(1) # Turn LED on
And off if it's bright (LDR voltage is high):
else:
  led.value(0) # Turn LED off
```
So by reading the LDR and controlling the LED, we can make a simple automatic nightlight!