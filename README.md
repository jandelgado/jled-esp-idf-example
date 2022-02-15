# JLed ESP-IDF example (ESP32)

[![test compile](https://github.com/jandelgado/jled-esp-idf-example/actions/workflows/test.yml/badge.svg)](https://github.com/jandelgado/jled-esp-idf-example/actions/workflows/test.yml)

This example shows how to use the embedded [JLed](https://github.com/jandelgado/jled) library 
with the ESP-IDF framework.

![JLed in action](.images/jled.gif)

```c++
#include <jled.h>

extern "C" void app_main(void);

void app_main(void)
{
    auto led = JLed(LED_PIN).Breathe(1500).Forever();

    while(1) {
        led.Update();
    }
}
```

## Project Structure

* [main/](main/)  - example sketch with the program entry point
* [components/](components) - Library dependencies - contains `JLed` as git submodule
* `build/` - build artefacts

## Build

* Prerequisite: install and activate ESP-IDF SDK from
  https://github.com/espressif/esp-idf 
* make sure to check out this repo with submodules by using e.g.
  `git clone --recursive https://github.com/jandelgado/jled-esp-idf-example`
* Inspect the [CMakeLists.txt](CMakeLists.txt) file and adjust the `LED_PIN`
  `#define` to your needs (GPIO where a LED is connected, e.g. `2` for the
  builtin LED of the ESP-WROOM-32 board).

The following commands are used to configure, build and flash the image:
* run `idf.py build` to compile the example
* run `idf.py flash` to flash the example on an ESP32
* optionally run `idf.py menuconfig` to configure the image (see
  (sdkconfig)[sdkconfig])
* run `idf.py clean` to clean up intermediary files

## Author and License

(C) Copyright 2022 by Jan Delgado, License: MIT

