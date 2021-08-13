---
layout: default
title: What are thresholds?
parent: Configuration
grand_parent: SP 4 Onderzoeksopzet 
nav_order: 3
---

# Threshold-based communication

Some sensors are able to generate an interupt when a certain metric value is exceeded.
When enabled, you will receive an update of the metric value if the threshold is exceeded.

We allow to define two thresholds, i.e., threshold low and threshold high: 
* When a metric value exceeds the `threshold high (TH)` an interrupt is generated.
* When a metric value goes below `threshold low (TL)` an interrupt is generated.
This allow us to get updates in three distinct manners.

In all cases an interrupt is generated when the metric value exceeds `TH` or when is falls below `TL`. 
When playing with the `TH` and `TL` configuration we can manipulate when we want an update.

In the figure below, dashed horizontal lines indicate when sensor data is transmitted to the gateway.

![](../assets/images/tl-th-thresholds.svg)

We describe the situations shown in the figure above:

1. Top figure: If we are interested to be notified when a value is higher than `TH` or lower than `TL`, we define: `TH` with a higher value as `TL`.
For example: if we want to get sensor data when a sound level exceeds 100 dB or when it is lower dan 80 dB, we set `TH=100` and `TL=80`.

2. Middle figure: If we are interested when a value enters the area between `TH` and `TL`,  `TL` has a higher value than `TH`.
For example: if we want to get sensor data when a sound level is between 80 and 100 dB, we set `TH=80` and `TL=100`.

3. Bottom figure: If we want to know when a metric value crosses a specific value, we can define `TH` equal to `TL`.
For example: if we want to get sensor data when a sound level crosses 85 dB, regardless if the sound level was higher or lower before, we set `TH=85` and `TL=85`.

In the table below you can find the minimum and maximum values `TL` and `TH` can take, for each physical quantity and each sensor.

| Sensor type   | Physical quantity     | minimum | maximum |
| ------------- |:-------------:|:-------------:|:-------------:| 
| Sound level sensor     | Sound level (dB) | 65 | 120 |
| Environmental sensor      | Temperature (&deg;C)  | -40  | 100 |
| Environmental sensor      | Air pressure (hPa)  | 0  |	65000 |
| Environmental sensor      |  Humidity (%) | 0  | 100	|
| Environmental sensor      | Air quality (no unit)  | 0  |	600 |
| Button sensor | - (no thresholding)  |  - (no thresholding) | - (no thresholding) |
| Light sensor      | Illuminance (lux) | 0  |	65535 |
| Power      | Battery voltage (V) | 0  |	4.20 |

Pay attention! Due to the manner in which sound levels are calculated, the measured sound level is always at least 50 dB. 
Therefore it does not make sense to try to measure 'quiet' sounds.
It is also not allowed to set thresholds lower than 65 dB, as this will lead to constant data transmission, which consume a lot of power and will drain the battery.
