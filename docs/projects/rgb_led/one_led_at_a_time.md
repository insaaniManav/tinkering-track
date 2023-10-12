# **Title: The Magic of RGB LEDs**

An **RGB LED** is like a colorful mini-light that can shine in many different colors. It's like having a tiny rainbow in your electronics!

**What's RGB?**

RGB stands for Red, Green, and Blue. These are the primary colors of light. An RGB LED has three tiny lights inside it – one for red, one for green, and one for blue.

**How does it make colors?**

By mixing these three colors together, you can create almost any color you can think of! For example, when you turn on the red and green lights, it makes yellow. Turn on the blue and green lights, and you get turquoise!

**Controlling the Colors**

To make the RGB LED show the color you want, you can use your Raspberry Pi Pico to send it special instructions. You can say, "Hey, shine red!" or "Show me some purple!"

**Fun with RGB LEDs**

RGB LEDs are used in lots of fun things. You can make a mood lamp that changes colors, create colorful displays, or even build a mini traffic light with red, green, and yellow colors.

**Why is it awesome?**

RGB LEDs let you bring a burst of color to your projects. They're like having a magic paintbrush in the world of electronics, letting you mix and match colors to create something truly dazzling!

**Let's make the LED Work**

* The LED we have in the box has a common positive terminal , it means that all the three LEDs connect to one positive terminal 


### What is a Common Anode RGB LED?
Imagine you have a special light that can shine in three different colors: red, green, and blue. This light is called an RGB LED. RGB stands for "Red, Green, Blue."

Now, a common anode RGB LED is a specific type of RGB LED. An "anode" is like the positive side of a battery. In this type of LED, the anode of all three color parts (red, green, and blue) are connected together, which makes it "common." This means that when you want to turn on a specific color, you send a signal to the common anode, and then you connect the individual color pins (red, green, and blue) to the ground (negative) to make that color light up. So, it's like you have a shared positive connection and you choose which color you want by turning on the corresponding color pins.

#### Connecting a Common Anode RGB LED to Raspberry Pi Pico 
To connect a common anode RGB LED to a Raspberry Pi Pico, you'll need the following components:

Here's how you can connect it:

Identify the pins: Your RGB LED should have four pins - one for common anode (usually the longest pin) and one for each color (red, green, and blue).

Connect common anode: Connect the common anode (longest pin) to the 3.3V pin on the Raspberry Pi Pico. This will provide power to the LED.

Connect color pins: Connect each of the color pins (red, green, and blue) to separate GPIO pins on the Raspberry Pi Pico. For example:

Red to GPIO pin 17
Green to GPIO pin 18
Blue to GPIO pin 19
Add resistors: Place a resistor (220-330 ohms) between the anode and the 3.3v line. Connect one end of each resistor to the respective color pin and the other end to the ground (GND) pin on the Raspberry Pi Pico. This will limit the current flowing through the LED, protecting it.

Ground connection: Connect a jumper wire from the Raspberry Pi Pico's GND (ground) pin to the breadboard's ground rail if you're using one. If not, connect it directly to the LED's common anode.

Now, you can write Python code to control the RGB LED using the GP IO pins you've connected to the individual colors. For example, to turn the LED red, you'd set the red GPIO pin to HIGH and the green and blue pins to LOW.