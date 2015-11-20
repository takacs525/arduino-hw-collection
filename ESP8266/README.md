# ESP8266 / Serial Port WIFI Wireless Transceiver Module

## Images
![Image1](images/5400624-0.jpg?raw=true)
![Image2](images/5400624-1.jpg?raw=true)
![Image3](images/5400624-2.jpg?raw=true)
![Image4](images/5400624-4.jpg?raw=true)

## Features
* Support 3 modes: AP, STA, AP+STA
* Low price with good quality
* High efficiency AT commands, simple for your development

## Tutorials
<https://www.youtube.com/watch?v=9QZkCQSHnko>

<http://tomeko.net/other/ESP8266/>

## AT command 
<http://www.electrodragon.com/w/Wi07c>

<http://wiki.iteadstudio.com/ESP8266_Serial_WIFI_Module>

    AT+RST
    AT+GMR

    AT+CWMODE=1
    AT+CWLAP


    AT+CWJAP="SSID","password"
    AT+CWJAP?
    AT+CIFSR


    AT+CIPMUX=0 
    AT+CIPSTART="TCP","192.168.1.203",7778
    AT+CIPSEND=4
    AT+CIPCLOSE

    AT+CIPSTART="TCP","www.mirrorbox.hu", 80
    AT+CIPSEND=54
    GET http://www.mirrorbox.hu/index.php HTTP/1.0\r\n\r\n

    AT+CWQAP

    AT+CIOBAUD?
    AT+CIOBAUD=115200			//57600
