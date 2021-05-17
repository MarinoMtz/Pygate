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

## Install

There are two option to set up our Pygate LoRa Gateway, we can either let the chirpstack stack (application and network servers, as well as the chirpstack geteway bridge) on a single site or we can implement the chirpstack gateway bridge on a raspberry. 
