---
layout: default
title: Draadloze communicatie
has_children: true
parent: SP 2 Randvoorwaarden IoT systeem
nav_order: 5
has_toc: true
---


# Draadloze communicatie
De moederborden bevatten een LoRaWAN modem om een draadloze verbinding tot stand te brengen.
LoRaWAN is een Low-Power Wide-Area Network technologie die het mogelijk maakt om draadloos kleine hoeveelheden data over een groot bereik te verzenden.

Een dergelijk netwerk bestaat uit eindapparaten (zoals onze moederborden) die communiceren met gateways. Deze gateways sturen de berichten door naar de cloud:
![](https://www.thethingsnetwork.org/docs/network/overview.png)

In dit project gebruiken we het [The Things Network](https://www.thethingsnetwork.org/) (TTN) systeem.
Iedereen kan gateways toevoegen aan dit netwerk om zo het netwerk uit te breiden.
Als er geen dekking is door het TTN, zorgen we voor een LoRaWAN-netwerk.
Je kunt de actieve gateways bekijken op de [TTN map](https://www.thethingsnetwork.org/map).
Zorg ervoor dat er een gateway aanwezig is binnen een bereik van minimaal 1km van uw apparaten.


## Beperkingen
Ons systeem wordt door twee regels beperkt in het aantal berichten dat we kunnen versturen.

We zijn beperkt door hoe snel we berichten achter elkaar kunnen verzenden en door het totaal aantal berichten per dag. 

Maximum aantal berichten per sensor in het slechtste en het beste geval:

| Sensor | Periodiciteit /uur | # Berichten /24u |
|----------------------|:-----------------:|:---------------:|
| Geluidssensor | 48.6 / 0.9 | 1165 / 22 |
| Omgevingssensor | 40.5 / 0.8 | 972 / 20 |
| Knopsensor | 48.6 / 0.9 | 1165 / 22 |

Het beste geval is wanneer het apparaat zich fysiek dicht bij de gateway bevindt, wat het geval is als de gateway zich in dezelfde kamer als de nodes bevindt. 
In het slechtste geval, wanneer we een slechte verbinding hebben, zijn we beperkt tot 20 berichten over 24 uur en mogen we niet vaker dan één bericht per uur verzenden. Nadat de nodes op hun definitieve locatie zijn gezet, kunt u ons vragen naar de kwaliteit van de verbinding van de nodes met de gateway.

### Beperking van de duty cycle
Wij zenden in een vergunningsvrije band wat betekent dat iedereen in deze band mag zenden als hij zich aan de voorschriften houdt. Deze regelgeving beperkt apparaten in het continu zenden. De apparaten hebben een duty cycle-beperking en kunnen pas zenden na een vooraf bepaalde tijd stil te zijn geweest.
Raadpleeg voor meer informatie de [TTN documentatie](https://www.thethingsnetwork.org/docs/lorawan/duty-cycle.html#maximum-duty-cycle).

### Beleid inzake eerlijke toegang
Bovenop de duty cycle limitatie, wordt de totale air time (d.w.z. hoe lang we berichten verzenden) beperkt tot 30 seconden per dag om de load op de gateways van de TTN te verlagen. 
