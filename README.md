# DS18B20 Sensor Node-RED node for Raspberry Pi

Node-RED node for working with [DS18B20 sensors](https://www.maximintegrated.com/en/products/analog/sensors-and-sensor-interface/DS18B20.html), inspired in this [library](https://github.com/stibi/node-red-contrib-ds18b20), but modified to behave slightly different with some extra functionalities.

![example screenshot](https://raw.githubusercontent.com/charlielito/node-red-contrib-sensor-ds18b20/master/icons/example.png)

It is compatible only with RaspberryPi hardware and it only reads the temperature values from sensors. The [base library](https://www.npmjs.com/package/ds18b20) is a npm module, which handles with the whole 1-Wire protocol with DS18B20 sensors (aka it does the magic).

### Physical Connection of sensor(s)
The DS18B20 sensors must be connected on GPIO4 (or physical pin #7) because this is the only pin that supports native 1-Wire protocol. The scheme of connection is typically the one on the image below.

![example screenshot](https://raw.githubusercontent.com/charlielito/node-red-contrib-sensor-ds18b20/master/icons/schema.png)

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
* Configurable time interval of the sensor sampling (in seconds)
* Periodic sensor sampling can be disabled, and sample temperature only when an external message arrives.

![example screenshot](https://raw.githubusercontent.com/charlielito/node-red-contrib-sensor-ds18b20/master/icons/example_interface.png)
