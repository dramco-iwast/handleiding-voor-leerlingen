---
layout: default
title: F.A.Q.
has_children: false
has_toc: true
nav_order: 9
---

# F.A.Q.


## Moederbord

###	Hoe groot is het geheugen (voor de sensordata) van het moederbord? Is het mogelijk om via interrupts (bv met de stemknoppen) gedurende bv. een halfuur veel input door te sturen als je daarna 24 uur stil ligt, of zal de data dan toch gedropt worden?
De grootte van het RAM-geheugen van het moederbord bedraagt 32 kB en het flashgeheugen bedraagt 256 kB. 
The things network en de LoRa chip hebben systemen ingebouwd die de hoeveelheid aan verzonden data zullen limiteren. 
Zo is het bijvoorbeeld niet mogelijk om meer dan 3 keer kort na elkaar data door te sturen naar the things network. 
Indien je toch een 4e keer wilt sturen zal je mogelijks ongeveer 1 à 3 minuten moeten wachten.  
Wanneer je te snel achtereen data zal verzenden, zullen er mogelijks berichten verloren gaan. 
Hierbij zijn we gelimiteerd door the things network en LoRa.

###	Kan je data rechtstreeks uitlezen van moederbord naar computer? Bv. om na te gaan hoe vaak je interrupts genereert met een bepaalde instelling voor de thresholds?
Dit is momenteel niet mogelijk met de huidige firmware op het moederbord. We bekijken of het gewenst is om deze feature toe te voegen.

## Batterij

### Kan je het batterijniveau vanop afstand uitlezen? Of een signaal sturen als het batterijniveau onder een bepaalde threshold zakt?
Dit is niet mogelijk met de huidige hardwareversie van het moederbord: het batterijniveau kan je voorlopig nog niet op afstand uitlezen. 
Er wordt nergens gemeten wat het batterijniveau is waardoor het dus ook niet mogelijk is om een signaal te genereren op het moment dat het batterijniveau zakt onder een bepaalde drempel. 
Dit sluit niet uit dat deze feature niet in een volgende versie kan voorzien worden.
Voorlopig is het uitvallen/onzichtbaar worden op het platform van de node de enige indicator voor een lege batterij.

## Geluidsensor

### Hoe wordt het geluidsniveau bepaald? 
Het geluidsniveau wordt bepaald aan de hand van een algoritme dat zich baseert op amplitudes van de geluidsgolven. 
Er wordt geen DFT uitgevoerd op de chip van de geluidsmodule, noch van het moederbord. 

###	Welk tijdsinterval wordt gebruikt om het geluidsniveau te bepalen?
Het tijdsinterval tussen elke meting bedraagt 1 seconde waarna er telkens 400 samples genomen worden met een sample frequentie van 20 kHz. 
De intensiteit wordt met andere woorden bepaald op basis van geluidsopnames van 20 ms.

###	Hoe kan het dat je 0dB kan opmeten? Fysisch verwacht je toch steeds minstens 10-20 dB op te meten?
De reden waarom de berekening 0 dB uitkomt is inderdaad niet correct. 
Van zodra het opgemeten signaal te klein wordt, wordt het hier naar 0 afgeleid. 
Dat komt omdat de ruis in het circuit laag is en de microfoon onvoldoende sensitief waardoor de Analoog naar digitaal converter (ADC) geen spanning opmeet. 
Met andere woorden indien een geluid lager is dan 50 dB ongeveer zal er 0 dB verschijnen op het platform aangezien er dan wel degelijk voor alle samples een 0 is ingelezen. 
Dit zouden we kunnen wegwerken door de versterkingsfactor te doen toenemen. Anderzijds zal dit als resultaat hebben dat we luide signalen niet meer juist zouden kunnen opmeten. 
Je kan er van uitgaan dat de gemeten waarden boven de 60 dB correcte en representatieve resultaten zijn.

