---
description: Test all internal components for correct hardware connectivity
---

# Setup and testing \(open box\)

## Preparation

* Add battery to the powermodule connector

## Powerboard

* [ ] Test: Powerswitch
  * Press the switch to turn on the plane internals
  * The Lights of the GPS module should light up

## Pixracer

* [ ] Test: Does it work
  * Connect USB Cable
  * Start QGC and check if the pixracer connects

## Telemetry

* [ ] Test: RFD Connection to QGC



* Check: Start QGC and check if it connects to the Pixracer
* Test: ESP-Telemetry Connection to QGC
* Check: Start System, Search for ESP WiFi \(insert name here\)
* Motor
* Test: is Rotating in correct direction
* Check: Using RC-Control
* add a piece of tape to the motor shaft to see the rotationdirection
* disable all safty checks
* arm vehicle 
* throttle up 
* check rotation of motor: Looking from the back of the plane to the motor, the rotation should be clock-wise
* If not correct, switch a pair of cables
* enable all safty checks again
* * Servos:
* Test: Rotation in correct direction
* Check: Switch system into manual mode, use RC Controller to check rotation direction
* check ailerons:
* aileron stick left -&gt; aileron left up, aileron right down
* check vtails:
* elevator stick up -&gt; elevator down
* ruder stic left -&gt; right ruder up, left ruder down
* * Camera-Payload
* Test: Camera: Removed camera protection
* Check: Ensure that protection film is removed
* Test: Camera: PI Can do camera images
* Check: Check Test in \[link to pi camera test\]
* Test: RX Telemetry / PI Receive Mavlink
* Check: Check Test in \[link to pi camera test\]
* Test: TX Telemetry / PI Send Mavlink
* Check: Check Test in \[link to pi camera test\]
* or
* Check: Check if preflight check msgs in QGC are received
* Test: PI - DHT22 Working
* Check: Check Test in \[link to pi camera test\]
* 
## Step 1: PixRacer setup



{% hint style="info" %}
Give special instrucktion... 
{% endhint %}

## Step 2: Bind the Remote Control





## Finalization & Testing



* [ ] check this
* [ ] and that...

