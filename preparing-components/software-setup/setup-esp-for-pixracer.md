# Setup ESP for Pixracer

## Flash MAVESP8266

* Use hints from [https://ardupilot.org/copter/docs/common-esp8266-telemetry.html](https://ardupilot.org/copter/docs/common-esp8266-telemetry.html)

## Configure 

* connect from your PC to the wifi access point \(initial access point ID is either “ArduPilot”  with password "ardupilot" or "Pixracer" with password “pixracer”\)
* open a browser to [192.168.4.1](http://192.168.4.1/) and a simple web interface will appear 
* click on the “Setup” link
* set config 
  * AP SSID := dronenameRacer \(replace "dronename" with your real drone name\)
  * AP Password := cassandra
  * baudrate := 921600
* push the “Save” button and reboot the device

## Install it to the pixracer

* Insert the esp as seen below into the pixracer

![](../../.gitbook/assets/image%20%284%29%20%282%29%20%282%29.png)



