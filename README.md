# Pygate
Pygate with chirpstack gateway bridge

This repository aims at providing the tools necesary to create a LoRaWAN Gateway using the chirptack platform

## Hardware Needed

* Raspberry Pi 3.0 with SD Card (> 8GB) (if chirpstack-gateway-bridge at the gateway side)
* PyGate avec PoE (if powered / Ethernet conection)
* WiPy, LoPy4 or GPy (tested with LoPy4)
* LoRa Antenna

## Software Requirements

* Chripstack Gateway Bridge
* Pycom firmware (for PyGate and WiPy / LoPy4 / GPy)
* Pymakr plugin in Atom or VS Code 

## Install

There are two options to set up our Pygate LoRa Gateway, we can either let the chirpstack stack (application and network servers, as well as the chirpstack geteway bridge) on a single site or we can implement the chirpstack gateway bridge on a raspberry pi. 
For the former, we shall follow the first 4 steps, and for the latter all the steps.

### 1. Pycom firmware

To update the firmware we need to install the Firmware Updater Tool : 

1.1. Download and install from : [Pycom](https://software.pycom.io/downloads/linux-1.16.5.html) 

1.2. Insert the module (WiPy / LoPy4 / GPy) and the PoE Ethernet into the Pygate

1.3. Attach the antenna to the Pygate (make sure there is nothig attached to the module)

1.4. Run the Firmware tool with ` pycom-fwtool ` on a linux terminal with the pygate connected through USB 

1.5. Select the corresponding port, usually ` ttyACM0 `

1.6. Select on type ` pygate ` and make sure not to select the Pybytes options

1.7. If everithing goes well, we are good to go.

### 2. Create a ` config.json ` file as the one in this repository

2.1 Modify: 

2.1.1. ` "gateway_ID": "XXXXXXXXXXXXXXXX" ` put the GW identifier 

2.1.2. ` "server_address": "outils.plido.net", ` put the corresponding domain or ip of the network server, or `localhost` if the chirpstack-gateway-bridge is installed in the raspberry pi.

2.1.3. We could also put multiple servers, the pygate will forward all the messages to each one of the servers.

2.1.3. Upload it to the pycom module.

### 3. Create a ` main.py ` file as the one in this repository

3.1 Configure the internet connection, it can either be wifi or ethernet.

3.1.2. For the wifi conection, put the coresponding values on line 32: `wlan.connect(ssid='XXXX', auth=(WLAN.WPA2, "XXXX")) `

3.1.1. For the ethernet conection, make sure the line `from network import ETH` is uncommented.

3.1.2. For the ethernet conection, uncomment lines 42 to 52.

3.1 Upload `main.py` to the module, if everithing goes ok, our Pygate is ready to send and receive LoRaWAN packets to the network server

### 4. Configure and send LoRaWAN packets on a pycom End Device.

4.1 Simply get the join-plido.py and put it into a pycom lopy module from `https://github.com/MarinoMtz/Roaming-ED`
