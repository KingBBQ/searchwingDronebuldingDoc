---
description: Test all internal components for correct hardware connectivity
---

# Setup and testing \(open box\)

## Preparation

* Add battery to the powermodule connector

## Powerboard

* [ ] Test: Powerswitch
  * Press the switch to turn on the plane internals
  * The Lights of the GPS module should light up / the buzzer should be hearable

## Pixracer

* [ ] Test: Does it work
  * Connect USB Cable
  * Start QGC and check if the pixracer connects

## Telemetry

* [ ] Test: RFD Connection to QGC
  * Connect the RFD868+ via USB connector to your PC or the SearchWing-Tablet
  * Start QGC and check if it connects to the Pixracer
  * Disconnect RFD868+ modem if sucessful
* [ ] Test: ESP-Telemetry Connection to QGC
  * Connect via PC or SearchWing-Tablet to the drone accesspoint "dronenameRacer" - Password "cassandra"
  * Start QGC and check if it connects to the Pixracer

## Motor / RC-control

* [ ] Test: is it Rotating in correct direction / RC-Control is working
  * Add a piece of tape to the motor shaft to see the rotationdirection
  * Disable all safty checks using QGC
  * Arm vehicle using the rc-controler 
  * Throttle up 
  * Check rotation of motor: Looking from the back of the plane to the motor, the rotation should be clock-wise
  * If not correct, switch a pair of cables
  * Enable all safty checks again using QGC

## Servos

* [ ] Test: do they rotate in correct direction
  * Switch system into manual mode
  * Use RC Controller to check rotation direction
  * Check ailerons
  * aileron stick left -&gt; aileron left up, aileron right down
  * Check vtails:
  * elevator stick up -&gt; elevator down
  * ruder stick left -&gt; right ruder up, left ruder down

## GPS

* [ ] Test: Receive &gt; 10 Sats
  * Put box outside at clear open sky \(no building should obstruct the view\)
  * Start QGC
  * At least 10 sats should be visible

## IMU

* [ ] Test: Receive messages
  * Start QGC
  * Do dummy calibration to check if IMU messages can be received

## Payload

* [ ] Test Camera: Removed camera lens protection
  * Ensure that the green protection film is removed
* [ ] Test Camera: PI Can do camera images
  * Check: Check [Camera test](https://kidslab.gitbook.io/searchwing/preparing-components/software-setup/setup-companion-computer#camera-image-taking)
* [ ] Test Payload RX Telemetry / PI Receive Mavlink
  * Check: Check [receive mavlink test](https://kidslab.gitbook.io/searchwing/preparing-components/software-setup/setup-companion-computer#receive-mavlink)
* [ ] Test Payload TX Telemetry / PI Send Mavlink
  * Check: Check [transmit mavlink test](https://kidslab.gitbook.io/searchwing/preparing-components/software-setup/setup-companion-computer#transmit-mavlink) - OR -
  * Check: Check if preflight check msgs in QGC are received
  * Open QGC
  * Wait 1 minute
  * Click "Trumpet" symbol at the top of QGC
  * Check if preflight check messages are received
* [ ] Test: DHT22
  * Check: Check [DHT22 test](https://kidslab.gitbook.io/searchwing/preparing-components/software-setup/setup-companion-computer#dht22)

## ESC Calibration

{% hint style="warning" %}
ESC has to be calibrated before closing the box!
{% endhint %}

* Turn power off \(main switch\)
* connect PixRacer with USB to a computer
* Set to `manual` mode 
* Arm 
* raise throttle to max on the RC
* Turn power on \(main switch\) -&gt; ESC peeps \(with motor\)
* lower throttle to min -&gt; ESC peeps once
* Done.



{% embed url="https://ardupilot.org/plane/docs/guide-esc-calibration.html" %}



## Finalization & Testing

* [ ] check this
* [ ] and that...

