---
layout: default
title: Sensoren
parent: SP 2 Randvoorwaarden IoT systeem
has_children: true
nav_order: 2
has_toc: true
---

# Sensoren

## Beschikbare sensoren
- Omgevingssensor (environmental sensor)
- Geluidsniveausensor (sound level sensor)
- Drukknopsensor (button sensor)
- Vermogen-/lichtsensor (power/light sensor)

## Sensorgegevens lezen
Er zijn twee benaderingen om sensorgegevens te lezen.

Tijdens de configuratie kunt u kiezen voor [polling](./../../SP4/what-is-polling.md) en/of [interrupt-gebaseerde](./../SP4/what-are-thresholds.md) communicatie.
De eerste wordt gebruikt wanneer u periodiek gegevens van het sensorbord wilt ophalen.
De laatste kan worden gebruikt wanneer u alleen wilt weten of de meting van belang boven of onder een vooraf ingestelde drempelwaarde ligt.

| Sensortype | Aantal | Onderbroken of polling-gebaseerde communicatie? | 
| ------------- |:-------------:|:-------------:| 
| Geluidsniveau sensor | 5 (varieert per school) | Interrupt en polling |
| Omgevingssensor | 5 (varieert per school) | Interrupt en polling |
| Drukknopsensor | 5 (varieert per school) | Interrupt |
| Stroomvoorziening | 10 (varieert per school) | Interrupt en polling |

In de tabel hieronder vindt u de minimum en maximum waarden die `TL` en `TH` kunnen aannemen, voor elke fysieke grootheid en elke sensor.

| Sensor type | Fysieke grootheid | minimum | maximum |
| ------------- |:-------------:|:-------------:|:-------------:| 
| Geluidsniveau sensor | Geluidsniveau (dB) | 65 | 120 |
| Omgevingssensor | Temperatuur (&deg;C) | -40 | 100 |
| Omgevingssensor | Luchtdruk (hPa) | 0 | 65000 |
| Milieusensor | Vochtigheid (%) 0 | 100 |
| Milieusensor | Luchtkwaliteit (geen eenheid) | 0 | 600 |
| Knopsensor | - (geen drempel) | - (geen drempel) | - (geen drempel) |
| Lichtsensor | Verlichtingssterkte (lux) | 0 | 65535 |
| Stroom | Batterijspanning (V) | 0 | 4.20 |

__Pas op!__ Door de manier waarop de geluidsniveaus worden berekend, is het gemeten geluidsniveau altijd ten minste 50 dB. 
Daarom heeft het geen zin om te proberen 'stille' geluiden te meten.
Het is ook niet toegestaan om drempels lager dan 65 dB in te stellen, omdat dit zal leiden tot constante datatransmissie, wat veel stroom verbruikt en de batterij leeg zal trekken.

