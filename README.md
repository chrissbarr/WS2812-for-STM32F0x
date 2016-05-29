# WS2812 for STM32F0x

**Very** basic WS2812 implementation for STM32F0x microcontrollers. Mimics basic functionality from Adafruit's NeoPixel library.

This implementation is part of my first project using any STM32 microcontroller, and as such it's pretty rough. In particular, the timing for the output signal generation needs a lot of work - currently it's just a trial-and-errored wall of 'NOP' functions to get the appropriate delay. This seems to leave a lot of variation in the waveform, and under some circumstances (long wiring, noisy environment, etc) the LEDs may not respond correctly.

A better approach would include a timer/counter to control the outut periods - I had quick try at this, but the shortest delay I was able to manage with that method was too long to drive the LEDs. If anyone has any suggestions I'd love to hear them.

An even better approach would use the DMA to take care of writing a buffer out to the LEDs.

## Usage
See the included example file. Most any pin / port can be used to drive the LEDs (or at least, I am aware of no limitation).

## Handy References
* [WS2812B Datasheet](https://cdn-shop.adafruit.com/datasheets/WS2812B.pdf) (timing diagrams that I have blatantly ignored)
* [NeoPixel Library by Adafruit](https://github.com/adafruit/Adafruit_NeoPixel) (library this code was based on)
* [HAL GPIO Library by Tilen Majerle](http://stm32f4-discovery.net/2015/07/hal-library-1-5-gpio-library-for-stm32fxxx/) (used to figure out GPIO pin / port mapping)
