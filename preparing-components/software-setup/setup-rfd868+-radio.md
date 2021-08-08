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



