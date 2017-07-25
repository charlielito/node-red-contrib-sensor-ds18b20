# DS18B20 Sensor Node-RED node for Raspberry Pi

![example screenshot](https://dl.dropboxusercontent.com/u/3189942/pics/ds18b20_nodered_node.png)

This Node-RED node is working only with DS18B20 sensors connected to a Raspberry Pi.
It can't be used as a "general" node for communication with the sensor.
The [underlying library](https://www.npmjs.com/package/ds18b20) is a npm module, which can read a data from a DS18B20 sensors connected to a Raspberry Pi and it is used by the node.

## Requirements

On the Linux system where your Node-RED is running and where your sensors are connected to, make sure you have loaded all the kernel modules needed for working with 1-Wire devices, what the DS1820 sensor is.
Thus, you need to active or have activated the 1-Wire Interface on the Rpi. To do this just go to the Raspi-Configuration page with:

```
sudo raspi-config
```

Go to `Interfaces` and then to `1-Wire` and `enable` it and reboot the device. You are done.


## Installation

Run the following command in the root directory of your Node-RED install

```
npm install node-red-contrib-sensor-ds18b20
```

Or just use the `package manager`(or manage pallette) from the Node-Red Interface to search for this module and install it manually.


## Features

* You can select a 1-wire device/sensor from a dropdown list in the configuration dialog of the node
* Configurable time interval of the sensor sampling
* Periodic sensor sampling can be disabled, and sample temperature only when an external message arrives.
