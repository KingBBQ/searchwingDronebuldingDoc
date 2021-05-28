---
description: 'To connect different components, special cables have to be produced.'
---

# Producing special cables



#### Time required

* **Building:** 30 minutes

#### Tools required

* soldering iron
* heat shrink tube

#### Parts required

* 


## Power-Module -&gt; Raspberry Pi Zero & DHT22

This cable connects the power from the power module to the 2 Raspberry Pi Zeros. This cable also connects the DHT22 sensor \(humidity and temperature\) to one pi.

## Power Switch -&gt; Power Module

## PixRacer -&gt; Raspberry Pi

This cable connects the PixRacer and the two Pi's. Furthermore there is a power supply cable for the Pi's to be built. Therefore you need STECKER UND KABEL NAMEN EINFUEGEN. 

Start with building the power supply for the two Pi's. Use the NAME DES CONNECTORS and the NAME DES KABELS and put it together. There is a +5V supply on pin 1&2 and ground on pin 3&4. Make sure that every Pi gets a +5V and a ground supply and twist the cables like shown in the pictrue below.

![Pi power supply](../../.gitbook/assets/pi-powersupply.jpg)

The next step is to build the cable for the connection between Pixracer and Pis. Therefore the NAME DES CONNECTORS UND KABELS is needed. Moreover you need a wire, because each Pi needs to be connected to the PixRacer. There need to be 3 wires in the STECKERNAME. Two of them, those which are in pin 1 and 5, need to be shorted like shown in the picture. 

![](../../.gitbook/assets/pi-pixracer-connection-cable-1.jpg)

You also need four cables made out of a wire of your choice. The length is shown in the picture below. 

![](../../.gitbook/assets/pi-pixracer-connection-cable-2.jpg)

The last step of building the connector cable between the Pi and PixRacer is to solder the previously shortened cables and use a heat shrink tube to isolate them. Don't forget to use two cables \(the green ones in the picture\) for each shortened cable on the connector.

![](../../.gitbook/assets/pi-pixracer-connection-cable-3.jpg)

## PixRacer -&gt; RC-Receiver 

The cable connects receiver in the plane \([FrSky R-XSR](../../parts/list-of-parts-and-where-to-buy.md#receiver)\) to 2 ports ob the PixRacer: **RCIN** and **FRS**.

![All cables needed](../../.gitbook/assets/frsky-receiver-cable-needed-cables.jpg)

You need:

* From FrSky-Receiver:
  * Plug with 5 cables
  * Remove the white one
* From PixRacer:
  * JST-5 connections \(fitting the RCIN connection\)

    JST-4 connections \(fitting the FRS connection\)

![](../../.gitbook/assets/frsky-receiver-cable-wiring.png)

![](../../.gitbook/assets/frsky-receiver-cable.jpg)

#### How to test

* connect to PixRacer
* connect to receiver
* [bind the remote control to receiver](../software-setup/receiver-software.md#bind-the-receiver-the-the-rc)
* check connection
* check telemetry 
  * Long Press on "PAGE"
  * See the telemetry from the PixRacer

## Telemetrie -&gt; PixRacer



## Finalization & Testing



* [ ] Connect Pixracer, Pis and Power Module 
* [ ] Pi receives messages from pixracer 
* [ ] Pi measures DHT22 humidity
* [ ] * [ ] 
