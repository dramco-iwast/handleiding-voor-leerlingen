---
layout: default
title: Configuratie
has_children: true
parent: SP 4 Onderzoeksopzet
nav_order: 3
has_toc: true
---

# Configuratie

## Sensorgegevens lezen
Er zijn twee benaderingen om sensorgegevens te lezen.
Tijdens de configuratie kunt u kiezen om periodieke en/of drempel-gebaseerde communicatie te gebruiken.
De eerste methode wordt gebruikt wanneer u periodiek gegevens van het sensorbord wilt opvragen.
De tweede methode kan worden gebruikt wanneer u alleen wilt weten of de meting van belang boven of onder een vooraf ingestelde drempelwaarde ligt.

Periodieke communicatie en drempelcommunicatie kunnen ook worden gecombineerd. 
Indien gecombineerd, worden gegevens verzonden telkens wanneer de geselecteerde drempelwaarden worden overschreden (drempel-gebaseerd) EN er worden ook periodiek gegevens verzonden (periodiek-gebaseerde communicatie).

### Drempelgebaseerde communicatie
Bij communicatie op basis van drempels wekt de sensor het moederbord wanneer de sensor gegevens heeft.
Vervolgens leest het moederbord de gegevens van de sensor.
Bij communicatie op basis van drempels slaapt het moederbord tussen de datatransmissies van de sensor in, wetende dat het zal worden onderbroken door de sensor wanneer dat nodig is.

### Periodieke communicatie
In tegenstelling tot op interrupt gebaseerde communicatie, zal het moederbord de sensor actief pollen om de data op te vragen.
Als gevolg daarvan moet het moederbord periodiek wakker worden wanneer het de sensor wil uitlezen. 
Het is te verwachten dat het stroomverbruik in dit geval hoger zal zijn, en dat u dus uw batterij of powerbank eerder zult moeten opladen dan bij drempel-gebaseerde communicatie.

## Configuratie hulpprogramma
Zie [hier](./configuration-tool.html).