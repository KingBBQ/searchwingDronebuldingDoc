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
  * add a piece of tape to the motor shaft to see the rotationdirection
  * disable all safty checks using QGC
  * arm vehicle using the rc-controler 
  * throttle up 
  * check rotation of motor: Looking from the back of the plane to the motor, the rotation should be clock-wise
  * If not correct, switch a pair of cables
  * enable all safty checks again using QGC

## Servos:

* [ ] Test: do they rotate in correct direction
  * Switch system into manual mode
  * use RC Controller to check rotation direction
    * check ailerons
      * aileron stick left -> aileron left up, aileron right down
    * check vtails:
      * elevator stick up -> elevator down
      * ruder stick left -> right ruder up, left ruder down

## Payload
* [ ] Test Camera: Removed camera lens protection
  * Ensure that the green protection film is removed
* [ ] Test Camera: PI Can do camera images
  * Check: Check Test in \[link to pi camera test\]
* [ ] Test Payload RX Telemetry / PI Receive Mavlink
  * Check: Check Test in \[link to pi camera test\]
* [ ] Test Payload RX Telemetry / PI Receive Mavlink
  * Check: Check Test in \[link to pi camera test\] - OR -
  * Check: Check if preflight check msgs in QGC are received
    * Open QGC
    * Wait 1 minute
    * Click "Trumpet" symbol at the top of QGC
    * Check if preflight check messages are received
* [ ] Test: DHT22 Working
  * Check: Check Test in \[link to pi camera test\]

## Finalization & Testing

* [ ] check this
* [ ] and that...

