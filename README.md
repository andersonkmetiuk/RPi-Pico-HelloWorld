# RPi-Pico-HelloWorld

## Initial development for Raspberry Pi Pico in Micropython

![Micropython](/assets/images/MicroPython.jpg)


![Pico Pinout](/assets/images/Pico-Pinout.PNG)

---

## Examples

Using [Thonny](https://thonny.org) IDE

### Branch: Blink

```
from machine import Pin, Timer

led = Pin(25, Pin.OUT)
LED_state = True
tim = Timer()

def tick(timer):
    global led, LED_state
    LED_state = not LED_state
    led.value(LED_state)

tim.init(freq=15, mode=Timer.PERIODIC, callback=tick)
```