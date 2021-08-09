# Setup RFD868+ radio

## Connect Radio

![](../../.gitbook/assets/image%20%285%29.png)

* install a jumper between pin 4 and 6
* Connect the modem to the computer 
  * using the provided USB-Serial adapter
  * OR: using the pin description above for your USB-Serial adapter

![Modem with the provided usb adapter connected](../../.gitbook/assets/image%20%286%29.png)

## Configure

* Connect to the modem using a serial console on your computer
  * Baudrate: 57600

```text
sudo minicom -D /dev/ttyUSB0 -b 57600
```

* Get into configuration mode
  * During startup press "+++"
  * "OK" should appear to be able to change the configuration
  * More info can be found in [https://www.hs-augsburg.de/homes/beckmanf/dokuwiki/doku.php?id=searchwing-rf-antenne](https://www.hs-augsburg.de/homes/beckmanf/dokuwiki/doku.php?id=searchwing-rf-antenne)
* Change parameters

<table>
  <thead>
    <tr>
      <th style="text-align:left">Command</th>
      <th style="text-align:left">Hint</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p></p>
        <p>AT&amp;F</p>
      </td>
      <td style="text-align:left">factory reset parameters</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p></p>
        <p>ATS4=20</p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>(PLANE) set txpower to 20dbm/100mW</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">ATS4=30</td>
      <td style="text-align:left">(GROUNDSTATION) set txpower to 30dbm/1000mW</td>
    </tr>
    <tr>
      <td style="text-align:left">ATS6=1</td>
      <td style="text-align:left">set data protocol type to MAVLINK</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p></p>
        <p>AT&amp;W</p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>write current changes to EEPROM</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">ATZ</td>
      <td style="text-align:left">reboot</td>
    </tr>
    <tr>
      <td style="text-align:left">ATI5</td>
      <td style="text-align:left">check if changed values are set</td>
    </tr>
  </tbody>
</table>

Should look like this:

```text
Welcome to minicom 2.7.1

OPTIONS: I18n 
Compiled on Aug 13 2017, 15:25:34.
Port /dev/ttyUSB0, 17:21:12

Press CTRL-A Z for help on special keys

OK
AT&F
OK
ATS4=20
OK
ATS6=1
OK
AT&W
OK
ATZOK
ATI5
S0:FORMAT=26
S1:SERIAL_SPEED=57
S2:AIR_SPEED=64
S3:NETID=25
S4:TXPOWER=20
S5:ECC=0
S6:MAVLINK=1
S7:OPPRESEND=0
S8:MIN_FREQ=868000
S9:MAX_FREQ=869000
S10:NUM_CHANNELS=10
S11:DUTY_CYCLE=100
S12:LBT_RSSI=0
S13:MANCHESTER=0
S14:RTSCTS=0
S15:MAX_WINDOW=131
S16:ENCRYPTION_LEVEL=0
```

