---
layout: default
title: Drukknopsensor
parent: Sensoren
grand_parent: SP 2 Randvoorwaarden IoT systeem
nav_order: 3
has_toc: true
---

# Drukknopsensor

![](./../../assets/images/button-sensor.jpg)

De drukknopsensor bevat vier knoppen.
Telkens wanneer een knop wordt ingedrukt, stuurt het moederbord een bericht naar de cloud waarin wordt gespecificeerd welke knop werd ingedrukt.

Deze sensor hoeft niet te worden geconfigureerd.

__Pas op!__ In het huidige systeem is er geen feedback loop! Het is mogelijk om gegevens van sensoren op te vragen en te analyseren, maar het zenden van signalen naar de sensorborden is (nog) niet mogelijk! Het is een eenrichtings communicatie: sensor boards kunnen data naar de gateway sturen, maar kunnen geen signalen of data ontvangen. (Dus b.v. een deur openen of een LED laten oplichten wanneer een drukknop wordt ingedrukt is momenteel onmogelijk!)

## Toepassingen
- Stemtoepassingen
	* bv. groepen leerlingen stemmen over het juiste antwoord op vragen van de leraar (bijna in real time)
	* bv., monitoren van tevredenheid van leerlingen over het eten in het schoolrestaurant (niet real time)
- Alarmtoepassingen
	* bv., in de gezondheidszorg: een verpleegster oproepen met een indicatie van urgentie
	* bv. valdetectie bij ouderen
