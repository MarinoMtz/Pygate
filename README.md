# Pygate
Pygate with chirpstack gateway bridge

This repository aims at providing the tools necesary to create a LoRaWAN Gateway using the chirptack platform

## Hardware Needed

* Raspberry Pi 3.0 with SD Card (> 8GB) (if chirpstack-gateway-bridge at the gateway side)
* PyGate avec PoE (if powered / Ethernet conection)
* WiPy, LoPy4 or GPy (tested with LoPy4)

## Software Requirements

* Chripstack Gateway Bridge
* Pycom firmware (for PyGate and WiPy / LoPy4 / GPy)
* Pymakr plugin in Atom or VS Code 

## Install

There are two options to set up our Pygate LoRa Gateway, we can either let the chirpstack stack (application and network servers, as well as the chirpstack geteway bridge) on a single site or we can implement the chirpstack gateway bridge on a raspberry pi. 
For the former, we shall follow the first XXX steps, and for the latter all the steps.

### 1. Pycom firmware

To update the firmware we need to install the Firmware Updater Tool : 

1. Download and install from : [Pycom](https://software.pycom.io/downloads/linux-1.16.5.html) 

2. Insert the module (WiPy / LoPy4 / GPy) and the PoE Ethernet into the Pygate

2. Conect the antenna to the Pygate (make sure there is nothig attached to the module)

3. Run the Firmware tool with ` pycom-fwtool ` on a linux terminal with the pygate connected through USB 

4. Select the corresponding port, usually ` ttyACM0 `

5. Select on type ` pygate ` and make sure ot to select the Pybytes options

6. If everithing goes we are good to go.

### 2. Creating new project on Pymakr



