---
layout: default
title: Wireless Communication
has_children: true
parent: SP 4 Onderzoeksopzet
nav_order: 3
has_toc: true
---

# Wireless Communication
The motherboards host a LoRaWAN modem to provide a wireless connection.
LoRaWAN is a Low-Power Wide-Area Network technology allowing to wirelessly transmit small amaount of data over a large range.

Such a network consist of end-devices (such as our motherboards) which communicate with gateways. These gateways relay the messages to the cloud:
![](https://www.thethingsnetwork.org/docs/network/overview.png)

In this project, we use the [The Things Network](https://www.thethingsnetwork.org/) (TTN) system.
Everyone can add gateways to this network in order to extend the network.
In case there is no coverage by the TTN, we will provide a LoRaWAN network.
You can view the active gateways on the [TTN map](https://www.thethingsnetwork.org/map).
Ensure there is a gateway present in at least a range of 1km of your devices.


## Limitations
Our system is limited by two regulations in the number of messages we can send.

We are limited by how fast we can transmit messages consecutively as well as by the total number of messages per day. 

Maximum number of messages per sensor in worst and best case:

| Sensor               | Periodicity /hour | # Messages /24h |
|----------------------|:-----------------:|:---------------:|
| Sound Sensor         |     48.6 / 0.9    |    1165 / 22    |
| Environmental Sensor |     40.5 / 0.8    |     972 / 20    |
| Button Sensor        |     48.6 / 0.9    |    1165 / 22    |

The best case is when the device is physically close to the gateway, which is the case if the gateway is in the same room as the nodes. 
In the worst case, when having a bad connection, we are limited to 20 messages over 24 hours and we are not allowed to transmit more frequently than one message per hour. After putting the nodes at their final location, you can ask us about the quality of the connection of the nodes to the gateway.

### Duty Cycle limitation
We are transmitting in an license-exempt band meaning that everyone can transmit in this band if they follow the regulations. These regulation limit devices in transmitting continuously. The devices are duty cycled limited and can only transmit after being silent for a predefined time duration.
For more information consult the [TTN documentation](https://www.thethingsnetwork.org/docs/lorawan/duty-cycle.html#maximum-duty-cycle).

### Fair Access Policy
On top of the duty cycle limitiation, the total air time (i.e., how long we transmit messages) is limited to 30 seconds per day to lower the laod on te gateways from the TTN. 


## LoRaWAN Gateway
In case there is no coverage by the TTN, we will provide a LoRaWAN Gateway.

### Network Access
To be able to use the gateway, the firewall needs to allow TCP communication over port 1700 to and from `router.eu.thethings.network`.

- TCP port: `1700` (up/down)
- Destination: `router.eu.thethings.network`



