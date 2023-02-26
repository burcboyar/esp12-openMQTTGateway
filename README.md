# A step by step guide for wiring and flashing ESP-12 with openMQTTGateway with CC1101 radio module.

openMQTTGateway is a great project which aims to create a single firmware that can read data from BLE, LoRa, RF, GSM, GPRS and infrared devices and then publish it over MQTT. (https://docs.openmqttgateway.com/)

Heard about this project from this video (https://www.youtube.com/watch?v=_gdXR1uklaY) of the Andreas Spiess (AKA the guy with the Swiss accent) and wanted to give it a try. I'm not exactly sure why but things didn't go smooth as on the video and took almost my 2 days to make it work, so I decided to create a step by step guide for the people who wants to create a bare ESP-12 based openMQTTGateway using CC1101 radio module.

Hope it works for you.

### Material List

- ESP8266 (I used an ESP-12)

![](https://github.com/burcboyar/esp12-openMQTTGateway/blob/main/pics/esp12.png)

- ESP8266 Development Board (https://www.aliexpress.com/item/1005004609383559.html)

This is a great board that can let you program ESP-01, ESP-12 and ESP32.

![](https://github.com/burcboyar/esp12-openMQTTGateway/blob/main/pics/Programmer.png)

- CC1101 module

I had this one in my stock, so I used it but it is very tiny and not breadboard friendly, so you may consider buying other CC1101 modules, since they have the same pinouts.

![](https://github.com/burcboyar/esp12-openMQTTGateway/blob/main/pics/cc1101.png)

### Wiring

I tried the CC1101 wiring from the openMQTTGateway site (https://docs.openmqttgateway.com/setitup/rf.html#pinout) and also tried LSatan's wiring (https://github.com/LSatan/SmartRC-CC1101-Driver-Lib#wiring) but none of them worked for me so I decided to make my own. I strongly suggest you to follow this wiring because even if you make the necessary changes in the code, sometimes the radio is not working with different GPIO's because of the states of the pins of the ESP-12. 

| CC1101         | ESP-12        | 
| :------------: |:-------------:|
| VCC            | VCC (3.3 V)   |
| GRD            | GRD           |
| GDO2 (Receiver)| GPIO4         |
| GDO1 (MISO)    | GPIO12        |
| MOSI           | GPIO13        |
| SCK            | GPIO14        |
| CSN            | GPIO15        |
| GDO0 (Emmiter) | GPIO2         |

### Code changes

openMQTTGateway site offers 3 options for uploading the code; uploading from the web, uploading ready to go binaries and uploading your own configurations. I succesfully flashed the chip with 1st and 2nd option but when I use nodemcuv2-rf-cc1101, nodemcuv2-rf2-cc1101 or nodemcuv2-somfy-cc1101 firmwares, they failed to create the wifi access point, only a wifi network with the chip name (like ESP12F) created and it cannot be connected. I didn't had such problem with other nodemcu firmwares, the always created wifi access point with the name OpenMQTTGateway but this time the radio didn't work. So, I had to select the 3rd way andgo with my own configuration.
