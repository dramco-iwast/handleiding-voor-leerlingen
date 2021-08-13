---
layout: default
title: Configuration
has_children: true
parent: SP 4 Onderzoeksopzet
nav_order: 3
has_toc: true
---

# Configuration

## Reading Sensor Data
There are two approaches to read sensor data.
During the configuration, you can opt to use periodic and/or threshold-based communication.
The former is used when you want to periodically retrieve data from the sensor bord.
The latter can be used when you only want to know whether the measurement of interest is above or below a preset threshold.

Periodic-based and threshold-based communication can be combined as wel. 
If combined, data is transmitted every time the selected thresholds are exceeded 
(threshold-based) AND data is also transmitted periodically (periodic-based communication).

### Threshold-based Communication
In case of threshold-based communication, the sensor wakes up the motherboard when the sensor has data.
Then, the motherboard reads the data from the sensor.
With threshold-based communication the motherboard sleep in between sensor data transmissions, knowing it will be interrupted by the sensor when needed.

### Periodic-based Communication
In contrast to interrupt-based communication, the motherboard will actively poll the sensor to request the data.
As a result the motherboard needs to periodically wake up when it wants to read-out the sensor. 
It is to be expected that power consumption will be higher in this case, and therefore you will need to recharge your battery or power bank sooner than with threshold-based communication.

## Configuration Tool
See [here](./configuration-tool.html).