# Pre-Flight

## Plan your flight

* [ ] Determine the goal of the flight
* [ ] Plan flight sequence \(take-off, flight and mission, landing; which modes\)
* [ ] Plan and validate mission
  * [ ] If required: load offline maps into QGC Plan mission in QGC \(consider duration and range!\)
  * [ ] Set QGeoFence sensibly
  * [ ] Transfer mission to aircraft \(will only be verified during upload\)
  * [ ] Save verified mission
* [ ] Briefing
  * [ ] procedure/explain mission
  * [ ] abortion criteria
  * [ ] determine observer, protocol
* [ ] **Editing positions** \(coordinates\) in QGroundControl
  * [ ] Enter coordinates waypoint/pattern by clicking ☰ &gt; Edit position... \(right hand side\) or drag&drop
  * [ ] Set Altitude: 550 m
  * [ ] For a search pattern, click Pattern &gt; Survey &gt; Basic/Circular and edit values:
    * [ ] Trigger Distance \(for a camera, not used\)
    * [ ] Spacing: 1950 m \(theoretically 2068 m w/o overlap\)
    * [ ] You may want to Rotate Entry Point for a quicker start.

![](../.gitbook/assets/image%20%284%29.png)

## Upload your flight

## Checklist

* [ ] Battery charged \(16.8 V\)
* [ ] Tighten the screws in the wings
* [ ] Check for visual defects
  * [ ] Klappen Flügel \(noch fest?\)
  * [ ] Klappen V-Tails
  * [ ] Servohörner fest?
  * [ ] Kamera
  * [ ] Membran
  * [ ] Deckel auf Ladebuchse?
  * [ ] Antenne noch fest?
  * [ ] Turm noch fest?
  * [ ] Akku-Tüte zu?
* [ ] ‌Check M plugs \(connecting V tail servos with box\)
* [ ] ‌check barycentre \("schwerpunkt"\)
* [ ] ‌note weight
* [ ] ‌turn QGC, RC, UAV on
* [ ] Payload
  * [ ] Clean camera window with a tissue
  * [ ] Check preflight-selfcheck of payloads in QGC
    * [ ] All services are running \(camera + dht22 + mavlink-router\)
    * [ ] SD card got enough space for a 1h flight -  delete old images if necessary
    * [ ] Camera can take and save photos to SD Card
    * [ ] DHT22 humidity and temperature acceptable
    * [ ] PI CPU temperature acceptable
  * [ ] Check camera image quality in browser via wifi connection`http://droneName/0_latest.jpg`
* [ ] ‌AHRS \(Attitude Heading Reference System\) check 
* [ ] ‌Barometer, GPS check
* [ ] compass Check
* [ ] ‌Servo check \(RC and Autopilot\)
* [ ] Safety parameters?
* [ ] ‌Save parameter set
* [ ] Propeller 10x7" r installed \(font in direction of flight\) and locked
* [ ] test Motor \(-&gt; vibration is bad is inlay in propeller?\)



