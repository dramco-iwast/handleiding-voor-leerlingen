---
layout: default
title: Toepassing
parent: Verdieping geluid
grand_parent: SP 2 Randvoorwaarden IoT systeem
nav_order: 5
---

# Toepassing: geluid meten op een concert

## Theoretische basis

### Geluidsnormen
Geluid afkomstig van muziekactiviteiten kan opgedeeld worden in drie categorieën die bepaald worden aan de hand van het equivalent continu geluidsniveau (L<sub>Aeq</sub>). 
Dit is het constante geluidsdrukniveau dat gedurende een tijdsduur T dezelfde energie levert als de werkelijk gemeten geluidsdrukniveaus gedurende die tijdsduur T. 
Dit kan bijvoorbeeld zeggen dat het geluid over een periode van 15 minuten gemeten wordt en het gemiddelde lager moet zijn dan 95 dB. 
De 3 categorieën met bijhorende voorwaarden zijn hieronder weergegeven.

- **Categorie 1**: geluidsniveau <85 dB(A)L<sub>Aeq, 15min</sub>
- **Categorie 2**: geluidsniveau > 85 dB(A)L<sub>Aeq, 15min</sub> en <= 95 dB(A)L<sub>Aeq, 15min</sub>
- **Categorie 3**: geluidsniveau > 95 dB(A)L<sub>Aeq, 15min</sub> en <= 100 dB(A)L<sub>Aeq, 60min</sub>

In theorie kan voor elke muziekactiviteit gekozen worden welke categorie van toepassing is. 
In de praktijk zijn de organisatoren echter vaak ook beperkt tot een maximale categorie omwille van omgevingsfactoren zoals bijvoorbeeld de buren. 

### Geluidsoverdracht in open lucht vs in een kamer
Soms kunnen we zeggen dat geluid afkomstig is van een *puntbron*.
Een puntbron is een in een punt geconcentreerd gedachte trillingsbron, bijvoorbeeld van geluid, licht, of van watergolven, waarvandaan de energie zich in alle richtingen gelijkelijk uitbreidt.
In open lucht en met een luidspreker of bron die geluid in alle richtingen uitsturen kunnen we de geluidsbron min of meer voorstellen als een puntbron. 
Het geluid zal zich gelijkwaardig in alle richtingen voortplanten.
De ontvanger ontvangt enkel geluid rechtstreeks afkomstig van de geluidsbron.
De verzwakking van het geluid is afhankelijk van de afstand tot de geluidsbron.
Als je de afstand tussen de geluidsbron en de ontvanger (bv. de microfoon) kent, kan je berekenen wat het geluidsniveau ter hoogte van de geluidsbron ongeveer is.

In andere situaties kunnen we de geluidsbron niet voorstellen als een puntbron. 
Bijvoorbeeld binnen in een kamer treden er reflecties op: het geluid afkomstig van de geluidsbron plant weerkaatst op de muren en objecten.
Bij de ontvanger komt het geluid van de geluidsbron meerdere keren toe: enerzijds zien we de rechtstreekse component, rechtstreeks afkomstig van de geluidsbron.
Anderzijds komen ook de geluidsgolven afkomstig van de geluidsbron die reflecteren op de muren en andere voorwerpen, bij de ontvanger toe.
We noemen dit een multipad-omgeving: het geluid volgt meerdere paden (rechtstreeks en via reflectie) van de zender (geluidsbron) naar de ontvanger.
Naast de verzwakking door afstand tussen bron en ontvanger, kan het ook zijn dat die verschillende geluidsgolven bij de ontvanger elkaar *versterken* (het geluid klinkt luider), of *verzwakken* (je hoort het geluid bijna of helemaal niet meer).
Het gedrag van geluid in een multipad-omgeving is moeilijk te modelleren: het hangt af van de precieze vorm van de kamer, welke voorwerpen in de kamer staan, de onderlinge positie van geluidsbron en -ontvanger, ...
De effecten die optreden in een multipad-omgeving kan je daarom het beste experimenteel onderzoeken.

## Praktische uitvoering

Formuleer nauwkeurig je onderzoeksvraag: wat wil je precies meten en wat wil je hieruit besluiten?
Bv: wordt het toegestane geluidsniveau overschreden tijdens het vrijpodium georganiseerd op de speelplaats van onze school?
Hiervoor moet je weten wat het toegestane geluidsniveau is!

### Configuratie van de IWAST-microfoon

- Ga na of je geluid wilt opmeten via interrupt-gebaseerde communicatie of via polling.
- Ga na welke parameters je wilt gebruiken:
-- Voor polling: om de hoeveel tijd wil je het geluidsniveau opvragen?
-- Voor interrupt-gebaseerde communicatie: welke drempelwaarde wil je gebruiken? 
Mogelijks moet je hier een correctie invoeren voor de verzwakking die optreedt omwille van de afstand tussen de *geluidsbron* en de *sensor*.
In een multipad omgeving moet je mogelijks nog extra corrigeren, maar dit moet je onderzoeken voor de concrete ruimte waarin je het geluidsniveau wilt testen.
- Open de configuratie-tool en volg de stappen [hier](./../../SP4/configuration-tool.html).
- Installeer het moederbord en de geluidssensor op een geschikte plek (dicht genoeg bij de geluidsbron). 
Maak indien nodig de set-up waterdicht.

### Geluidsinformatie opmeten met IWAST

Ga naar het [webplatform](./../../SP5/Platform/platform.html) en download de data.

### IWAST data analyseren om geluidsoverlast vast te stellen

Analyseer de data met een computerprogramma naar keuze.
Documentatie voor analyse in Excel en Python vind je [hier](./../../SP5/analyse.md).
