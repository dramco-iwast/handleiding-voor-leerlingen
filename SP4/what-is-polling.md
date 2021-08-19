---
layout: default
title: Periodieke communicatie
parent: Configuratie
grand_parent: SP 4 Onderzoeksopzet
nav_order: 2
---

# Periodieke communicatie

Sommige sensoren kunnen polled worden.
Dit betekent dat het moederbord periodiek naar de actuele status van de sensor vraagt.
De periodiciteit kan worden geconfigureerd met de configuratietool.
Om het stroomverbruik van het IoT-systeem te verminderen, stellen we voor om een drempel-gebaseerde communicatie te gebruiken in plaats van een periodiek-gebaseerde communicatie.
Het snelste dat je een sensor kan pollen is elke vijf minuten.

Een polling interval van 0 geeft aan dat polling is uitgeschakeld, en dat dus alleen drempelwaarde wordt gebruikt om te bepalen wanneer gegevens moeten worden verzonden.
