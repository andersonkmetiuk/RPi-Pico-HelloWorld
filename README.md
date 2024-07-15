# RPi-Pico-HelloWorld

## Initial development for Raspberry Pi Pico in Micropython

![Micropython](/assets/images/MicroPython.jpg)


![Pico Pinout](/assets/images/Pico-Pinout.PNG)

---
## Setup

Install [Thonny](https://thonny.org) IDE

Go in the `Tools> Options > Interpreter` and select `MicroPython (Raspberry Pi Pico)` option and also the `Board CDC` under Port option.

Remember to name the scripts that you send to the `Pico` as `main.py` so they are going to be interpreted right away as the default config for the board.

If you have trouble setting it up. Follow [this video](https://www.youtube.com/watch?v=zlKJ5hvfs6s)

## Examples

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