# A step by step guide for wiring and flashing ESP-12 with openMQTTGateway and CC1101 radio module.

openMQTTGateway is a great project which aims to create a single firmware that can read data from BLE, LoRa, RF, GSM, GPRS and infrared devices and then publish it over MQTT. (https://docs.openmqttgateway.com/)

Heard about this project from this video (https://www.youtube.com/watch?v=_gdXR1uklaY) of the Andreas Spiess (AKA the guy with the Swiss accent) and wanted to give it a try. I'm not exactly sure why but things didn't go smooth as on the video and took almost my 2 days to make it work, so I decided to create a step by step guide for the people who wants to create a bare ESP-12 based openMQTTGateway using CC1101 radio module.

Hope you like it.



### Material List
- ESP8266 (I used an ESP-12)

![](https://github.com/burcboyar/esp12-openMQTTGateway/blob/main/pics/esp12.png)

- ESP8266 Development Board (https://www.aliexpress.com/item/1005004609383559.html)

This is a great board that can let you program ESP-01, ESP-12 and ESP32.

![](https://github.com/burcboyar/esp12-openMQTTGateway/blob/main/pics/Programmer.png)

- CC1101 module

I had this one in my stock, so I used it but it is very tiny and not breadboard friendly, so you may consider buying other CC1101 modules, they have the same pinouts.

![](https://github.com/burcboyar/esp12-openMQTTGateway/blob/main/pics/cc1101.png)
