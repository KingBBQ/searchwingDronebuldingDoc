# Setup Companion Computer

#### Time required

*  ****30 Minutes

#### Parts required

* 2x PI Zero
* 2x Micro SD Card 64 GB
* 1x Micro USB Cable \(for testing\)

## Flash image to board

*  Download image: [https://cloud.hs-augsburg.de/s/6cia2g5xpoCjjZX](https://cloud.hs-augsburg.de/s/6cia2g5xpoCjjZX)
*  Flash image to SD Card 
  * e.g. using Etcher Tool [https://www.balena.io/etcher/](https://www.balena.io/etcher/)
  * or using dd in \*NIX systems [https://www.raspberrypi.org/documentation/installation/installing-images/linux.md](https://www.raspberrypi.org/documentation/installation/installing-images/linux.md)

## Configure

* Mount partition`/boot`
  * normally gets automounted in windows
  * otherwise mount by hand in \*NIX systems
* Set Accesspoint and NetworkHostname depending on left / right camera :
  *  Open the `/boot` partition \(which normally gets automounted in windows\)
    *  open the file `wpa_supplicant.conf`:
      *  Get info for AP names and passwords from [the network description.](https://www.hs-augsburg.de/homes/beckmanf/dokuwiki/doku.php?id=image-download-station)
      *  Write info in `wpa_supplicant.conf` :
        *  cam-r : `ssid=“AP1”`
        *  cam-l : `ssid=“AP2”`
        *  WIFI Password : `psk=“AP-Password”`
        * Multiple networks can be configured in here, by copying the corresponding block
    *  Open the file `unattended`:
      *  Replace the hostname of the drone according the name scheme: 
        * e.g. `DRONENAME-L/R` → `freddy-l`
* Unmount sd card
* Remove sd card

## Testing

### Login

* Insert sd card into Pi and power up using a micro USB cable
*  First bootup the filesystem of image \(~2Gb\) is enlarged to the SD-Card size \(64Gb\)
  *  Implemented by creating a `/data` partition where the image will be saved
  *  Takes ~3-5Minutes
  *  Afterwards filesystem resize the camera-capture & webserver service is started
*  You can access each camera via its hostname: 

```bash
$ ssh searchwing@perlman-l
```

or

```bash
$ ssh searchwing@perlman-l.local
```

### Camera image taking

* Check for new images using pi webserver
  * Open webbrowser
  * Go to`http:\\perlman-l`
  * Click on `0_latest.jpg@`
  * The most recent image should appear \(and can be refreshed using browser refresh / F5-key\)
  * You can also check if new images appear in the main list
* For debugging you check output of the image payload: 

```bash
$ journalctl -f -u searchwing-payloads-camera.service

-- Logs begin at Fri 2021-07-16 15:52:25 BST. --
Jul 16 15:59:25 perlman-l searchwing-payloads-camera.py[293]: [2021-07-16 15:59:25.980]-[DEBUG]:        [MAVLINK attitude msg]:(roll:  -30.05°, pitch:   -4.64°, yaw:  117.37°)
Jul 16 15:59:25 perlman-l searchwing-payloads-camera.py[293]: [2021-07-16 15:59:25.992]-[DEBUG]:        [HEARTBEAT msg]: Mode: 81, State: MAV_STATE_CRITICAL
Jul 16 15:59:26 perlman-l searchwing-payloads-camera.py[293]: [2021-07-16 15:59:26.051]-[DEBUG]:        [MAVLINK GPS msg]:(lat:0.0, lon:0.0, hdg:11.737°)
Jul 16 15:59:26 perlman-l searchwing-payloads-camera.py[293]: [2021-07-16 15:59:26.430]-[DEBUG]:        [SYSTEM_TIME] Pixracer time: 1970-01-01T01:00:00
Jul 16 15:59:26 perlman-l searchwing-payloads-camera.py[293]: [2021-07-16 15:59:26.439]-[DEBUG]:        [SYSTEM_TIME] Discard Pixracer timestamp as it is not valid (year < 2021!)
Jul 16 15:59:26 perlman-l searchwing-payloads-camera.py[293]: [2021-07-16 15:59:26.674]-[DEBUG]:        [MAVLINK attitude msg]:(roll:  -30.04°, pitch:   -4.65°, yaw:  117.34°)
Jul 16 15:59:26 perlman-l searchwing-payloads-camera.py[293]: [2021-07-16 15:59:26.734]-[DEBUG]:        [MAVLINK GPS msg]:(lat:0.0, lon:0.0, hdg:11.734°)

```

* If the progress is stopped, most probably the pi camera cable isnt working properly

### DHT22 

* Check output of dht22 payload:

```bash
$ journalctl -f -u searchwing-payloads-temp-humid.service

-- Logs begin at Fri 2021-07-16 15:51:32 BST. --
Jul 16 15:58:08 perlman-l searchwing-payloads-temp-humid.py[270]: [2021-07-16 15:58:08.109]-[INFO]:        [DHT-Temp °C]: 32.70
Jul 16 15:58:09 perlman-l searchwing-payloads-temp-humid.py[270]: [2021-07-16 15:58:09.127]-[INFO]:        [Pi-Core-Temp °C]: 73.44
Jul 16 15:58:09 perlman-l searchwing-payloads-temp-humid.py[270]: [2021-07-16 15:58:09.711]-[INFO]:        [DHT-Humidity %]: 72.10
Jul 16 15:58:09 perlman-l searchwing-payloads-temp-humid.py[270]: [2021-07-16 15:58:09.714]-[INFO]:        [DHT-Temp °C]: 32.70
Jul 16 15:58:10 perlman-l searchwing-payloads-temp-humid.py[270]: [2021-07-16 15:58:10.719]-[INFO]:        [Pi-Core-Temp °C]: 73.978
Jul 16 15:58:11 perlman-l searchwing-payloads-temp-humid.py[270]: [2021-07-16 15:58:11.254]-[INFO]:        [DHT-Humidity %]: 72.00

```

* You should see new temperature and humidity measurements live

### Flightcontroler / Pixracer Mavlink connection

* Connect to the flightcontroller via mavproxy

```bash
$ mavproxy.py --master=tcp:127.0.0.1:5760 --default-modules=mode
```

#### Receive Mavlink

* After a few seconds, the connection should be established

```bash
Connect tcp:127.0.0.1:5760 source_system=255
Log Directory: 
Telemetry log: mav.tlog
Waiting for heartbeat from tcp:127.0.0.1:5760
MAV> online system 1
RTL> Mode RTL
```

#### Transmit Mavlink

* On the Pi with RX/TX connected to the pixracer you can now test TX 
  * Set the plane to Manual Mode
  * Write `mode MANUAL`

```bash
RTL> mode MANUAL 
RTL> Got COMMAND_ACK: DO_SET_MODE: ACCEPTED 
MANUAL> Mode MANUAL
```

* The plane should be now in manual mode

#### Debugging

* using searchwing-pi repo / searchwing-payload-camera

  * set `LOGGER_LEVEL = "DEBUG"`in `/home/searchwing/searchwing-pi/configuration.toml`
  * restart: `sudo systemctl restart searchwing-payloads-camera.service`
  * Check output

  ```bash
  $ journalctl -f -u searchwing-payloads-camera.service
  ```

* using mavlink-router stats per port

  * enable mavlink-router stats printing in `/etc/mavlink-router/config.d/main.conf` 

  `[General]`

  **`ReportStats=true`**

  `MavlinkDialect=auto`

  * restart mavlink-router: `sudo systemctl restart mavlink-router.service`
  * Check output

  ```bash
  $ journalctl -f -u mavlink-router.service
  ```

