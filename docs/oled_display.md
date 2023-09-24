```py
from machine import Pin, I2C
from ssd1306 import SSD1306_I2C
WIDTH =128 
HEIGHT= 64
i2c=I2C(0,scl=Pin(17),sda=Pin(16),freq=200000)
oled = SSD1306_I2C(WIDTH,HEIGHT,i2c)
while True:
    oled.fill(0)
    oled.text("Hello Python", 0, 0)
    oled.show()
```