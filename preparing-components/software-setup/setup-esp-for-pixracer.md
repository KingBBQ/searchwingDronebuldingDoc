# Setup ESP for Pixracer

## Flash MAVESP8266

* Use hints from [https://ardupilot.org/copter/docs/common-esp8266-telemetry.html](https://ardupilot.org/copter/docs/common-esp8266-telemetry.html)

## Configure 

* connect from your PC to the wifi access point \(initial access point ID is “ArduPilot”, and password is “ardupilot”\)
* open a browser to [192.168.4.1](http://192.168.4.1/) and a simple web interface will appear 
* click on the “Setup” link
* set config 
  * AP SSID := dronenameRacer
  * AP Password := cassandra
  * baudrate := 912600
* push the “Save” button and reboot the device

## Install it to the pixracer

* Insert the esp as seen below into the pixracer

![](../../.gitbook/assets/image%20%284%29%20%282%29.png)



