[← Übersicht](../README.md)

# Draußen & Nässe

Festivals heißt: Regen, Tau am Morgen, Staub, Matsch. Was davon was aushält:

## Schutzarten (IP) kurz erklärt

| IP | Bedeutung | Wo bei uns |
|---|---|---|
| IP20 | kein Wasserschutz | nur innen, z. B. Netzteil *in* der Box |
| IP44 | Spritzwasser | überdachte Bereiche |
| IP65 | Strahlwasser | draußen, Regen von allen Seiten |
| IP67 / IP68 | zeitweises / dauerhaftes Untertauchen | Kabelverbindungen am Boden, Pfützen |

## Unsere Komponenten

| Teil | Schutz | Hinweis |
|---|---|---|
| [LP16-Stecker](stecker-lp16.md) | **IP68 – nur gesteckt!** | Offene Buchsen immer mit der **Schutzkappe** verschließen. Offene Stecker nicht in den Matsch legen. |
| [H05RN-F-Kabel](kabel.md) | für draußen geeignet | Gummimantel verträgt Nässe, Kälte und Dreck. |
| LED-Streifen | je nach Variante | Für draußen **IP65 (Silikonbeschichtung) oder IP67 (Silikonschlauch)** bestellen. Lötstellen und offene Enden mit Schrumpfschlauch mit Kleber abdichten. |
| Mean Well **LRS**-Netzteil | IP20 | **Nur in einer geschlossenen Box.** Braucht Luft zum Kühlen – nicht luftdicht einpacken. |
| Controllerbox | je nach Gehäuse | Kabel nur über [PG-Verschraubungen](kabel.md#verschraubungen-gehäuse-durchführungen) einführen, Kabel **von unten** reinführen, damit kein Wasser reinläuft. |

## Netzteil für draußen

Wenn ein Netzteil direkt am Element draußen sitzen soll (z. B. beim [Nachspeisen](stromversorgung.md#was-tun-bei-langen-strecken)), lieber ein vergossenes, wasserdichtes Netzteil nehmen statt ein LRS in eine dichte Box zu packen:

| Serie | Schutz | Typisch für |
|---|---|---|
| Mean Well **ELG** | IP67 | gutes Preis-Leistungs-Verhältnis für draußen |
| Mean Well **HLG** | IP67 | robuster, höhere Lebensdauer, teurer |

Beide gibt es mit 12 V und 24 V in vielen Leistungsstufen. Bei der Bestellung auf die **Spannungsvariante** achten (bei HLG/ELG steht die Spannung am Ende der Typbezeichnung, z. B. `-12`).

## Checkliste vor dem Aufbau

- [ ] Alle offenen Buchsen mit Kappe zu
- [ ] Steckverbindungen nicht in Senken oder Pfützen
- [ ] Controllerbox erhöht und überdacht aufstellen, Lüftungsöffnungen nach unten
- [ ] 230-V-Zuleitung über FI/RCD
- [ ] Kabel so verlegen, dass niemand drüber stolpert und kein Fahrzeug drüber fährt
