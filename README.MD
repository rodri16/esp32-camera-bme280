TTGO-Camera
=====================

![pic](image/1.jpg)

- Now Arduino officially supports the camera, you need to update the Arduino to the latest, see [arduino-esp32](https://github.com/espressif/arduino-esp32/releases) for details.I am using the `1.0.1rc2` version when writing this code.
  
- In order to support BME280, I will use [Adafruit_BME280_Library](https://github.com/adafruit/Adafruit_BME280_Library), but this library conflicts with <esp_camera.h> and enters [Adafruit_BME280_Library](https://github.com/adafruit/Adafruit_BME280_Library) In Adafruit_BME280_Library change <Adafruit_BME280.h> --> 29 lines comment #include <Adafruit_Sensor.h>, BME280 this library does not use this header file, so comment out and no problem

- OLED requires [esp8266-oled-ssd1306](https://github.com/ThingPulse/esp8266-oled-ssd1306) library support
  
- Buttons require [OneButton](https://github.com/mathertel/OneButton) library support

## TTGO CAM PINS
| Name  | Num    |
| ----- | ------ |
| Y9    | 39     |
| Y8    | 36     |
| Y7    | 23     |
| Y6    | 18     |
| Y5    | 15     |
| Y4    | 4      |
| Y3    | 14     |
| Y2    | 5      |
| VSNC  | 27     |
| HREF  | 25     |
| PCLK  | 19     |
| PWD   | 26     |
| XCLK  | 32     |
| SIOD  | 13     |
| SIOC  | 12     |
| RESET | No use |

## Sensor & OLED
| Name | Num |
| ---- | --- |
| SDA  | 21  |
| SCL  | 22  |

## Other
| Name   | Num |
| ------ | --- |
| Button | 34  |
| PIR    | 33  |

* BUTTON Click: Reverse camera ~~Currently the camera reverse color will not be normal, see [issues#9](https://github.com/espressif/esp32-camera/issues/9)~~

* BUTTON LongPress : Enter sleep Mode , Sleep current ~6.9mA
  
* RESET BUTTON: When the battery is powered, click to turn on the power

* PIR: Detecting human motion and will display the first screen

## Companion projects 
If you are interested in controlling addressable Leds with ESP32 and launching animations with short UDP commands check out our project [Remora](https://github.com/martinberlin/Remora)


## Test Video
[YouTube](https://www.youtube.com/watch?v=CibcsmurTbo)
