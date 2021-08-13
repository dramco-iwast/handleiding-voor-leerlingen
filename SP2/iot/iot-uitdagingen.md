---
layout: default
title: IoT uitdagingen
parent: Internet der Dingen
grand_parent: SP 2 Randvoorwaarden IoT systeem
nav_order: 3
has_toc: true
---

# Uitdagingen in IoT
In het bovenstaande beschreven we dat IoT een interessant en snel veranderend domein is met een oneindig aantal toepassingen. Maar natuurlijk zijn er ook een aantal uitdagingen: 
1. dataverkeer: het doorsturen van sensorgegevens leidt tot een enorme toename aan draadloos dataverkeer. 
2. energieverbruik: sensoren moeten gedurende lange tijd op een kleine batterij kunnen functioneren.

## Data-overdracht
Om de toekomstvisie van een slimme wereld mogelijk te maken, moeten sensoren continu een grote stroom aan informatie verwerken. Om even aan te tonen om hoeveel informatie het gaat: een camera die een hele dag filmt, resulteert in 2.4TB data per dag. Zelfs een microfoon die continu spraak opneemt produceert elke dag 2GB aan data.
Wie veel Youtube kijkt of ooit een groot bestand probeerde te downloaden weet dat dergelijke grootteordes van gegevensoverdracht tijd vragen. Beeld je nu in dat in de ideale IoT-wereld in elk huis, bedrijf, auto, … honderden van die sensoren constant data naar de cloud doorsturen. Het spreekt voor zich dat dit quasi onmogelijk is.

We moeten dus manieren vinden om de datastromen te beperken. Slimme wetenschappers aan universiteiten onderzoeken momenteel hoe we sensoren slimmer kunnen maken, zodat ze minder informatie continu moeten doorsturen. Eén van de pistes die daarbij onderzocht wordt, is ‘machine learning’: we leren apparaten, machines, … aan om zelf op een ‘slimme’ manier te beslissen welke gegevens belangrijk genoeg zijn om door te sturen.

Dat gaat te ver voor dit project. Binnen dit project gebruiken we twee manieren om de datastromen te beperken.
1. De eerste manier is door slechts op periodieke intervallen gegevens door te sturen. Zo kunnen we instellen dat een temperatuursensor in een klaslokaal slechts om de 5 minuten de gedetecteerde temperatuur moet doorsturen.
2. De tweede manier is door enkel relevante gegevens door te sturen. Zo kunnen we bv. zeggen dat een geluidsniveaumeter die gebruikt wordt om geluidsoverlast te monitoren, enkel het geluidsniveau moet doorsturen als een bepaalde geluidsniveau drempel overschreden wordt.

## Vermogenverbruik
De droom is dat IoT toepassingen in de achtergrond verdwijnen en veel handige functies in ons leven (denk maar aan de ‘slimme koelkast’) quasi onopgemerkt uitvoeren. Om dit doel werkelijk te bereiken moeten de sensoren autonoom (zelfstandig) opereren met minimaal menselijk ingrijpen. Dit houdt o.a. in dat de sensoren en de draadloze communicatie slechts heel weinig vermogen mogen verbruiken, zodat een gebruiker niet gedwongen wordt om om de twee dagen de batterijen van alle ‘slimme apparaten’ in huis te vervangen.
Het vermogenverbruik van een IoT systeem hangt o.a. af van de draadloze communicatietechniek en van de hoeveelheid data die doorgestuurd moet worden.
