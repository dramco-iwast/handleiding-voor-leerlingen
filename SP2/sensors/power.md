---
layout: default
title: Vermogen- / lichtsensor
parent: Sensoren
grand_parent: SP 2 Randvoorwaarden IoT systeem
nav_order: 4
has_toc: true
---

# Vermogen- / Lichtsensor

![](./../../assets/images/power-sensor.jpg)

De vermogen- / lichtsensor meet het volgende:
- Verlichtingssterkte (lux)
- Batterijspanning (V)

De vermogenmodule kan worden gebruikt om het hele systeem van energie te voorzien. 
De module bestaat uit op een batterij waarvan de spanning wordt omgezet in een stabiele uitgangsspanning.
De module omvat een fotovoltaïsch paneel met een MPPT-algoritme om op efficiënte wijze microwatts tot milliwatts vermogen uit het zonnepaneel te halen en de batterij op te laden.

## Opladen van de batterij via USB
Wanneer de batterij uiteindelijk toch leeg raakt, wordt deze automatisch losgekoppeld van het systeem. 
De batterij kan ook via USB worden opgeladen. Bij het inpluggen via USB gaan een groen en rood lampje branden. Het opladen is voltooid wanneer het rode lampje uitgaat en alleen het groene lampje blijft branden.

__Let op! De batterij laadt niet op als de vermogenmodule via het moederbord aan een laptop is aangesloten.__ De batterij laadt enkel op via het zonnepaneel (traag) of wanneer de vermogenmodule rechtstreeks via USB is aangesloten aan een laptop of adapter (sneller).

## Meten van invallend licht
Deze module bevat een LDR (Light Dependent Resistor) waarvan de uitgangspanning wordt omgezet in een verlichtingssterkte. Een meting wordt aangegeven door een blauw lampje.

### Verlichtingssterkte

Verlichtingssterkte is een maat voor de hoeveelheid invallend licht die een bepaald oppervlak verlicht. 

| Verlichtingsconditie | Van (lux) | Tot (lux) | Gemiddelde waarde (lux) |
|--------------------|------------|----------|------------------|
| Pikzwart | 0 | 10 |  5 |
| Zeer donker | 11 | 50 | 30 |
| Donker Binnenshuis | 51 | 200 | 125 |
| Donker Binnen | 201 | 400 | 300 |
| Normaal Binnen | 401 | 1000 | 700 |
| Lichte Binnenlucht | 1001 | 5000 | 3000 | 
| Buiten | 5001 | 10.000 | 7500 |
| Bewolkt Buiten | 10.001 | 30.000 | 20.000 |
| Direct zonlicht | 30.001 | 100.000 | 65.000 |

## Batterijspanning meten

De powermodule maakt gebruik van een Lithium Polymeer (LiPo) batterij die kan worden gebruikt om het hele systeem van stroom te voorzien. Door de chemische samenstelling van de batterij is de spanning niet lineair gerelateerd aan de resterende capaciteit, maar de batterijspanning kan wel een goede indicatie geven van de laadtoestand. Een meting wordt aangegeven door een blauw lampje.

## Toepassingen
- Bewaking van weersomstandigheden
	* bv. signalering wanneer de zon schijnt / wanneer het bewolkt is
	* bv. dag - nacht volgen
- Bewaking van de energieopbrengst van het zonnepaneel
	* bv. hoeveel energie wordt door het zonnepaneel geleverd?
- Bewaken van de laadtoestand
	* bv. bepalen hoeveel langer het systeem kan meten
