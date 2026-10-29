[← Übersicht](../README.md)

# LEDs

Die Controller sind **nicht an einen LED-Typ gebunden**. Sie treiben adressierbare Pixel-LEDs mit einer einzelnen Datenleitung, also das übliche WS281x-Protokoll. Welche LEDs du nimmst, hängt vom Projekt ab: Spannung, Pixeldichte, Länge der Leitungen, Budget.

> **L300-Standard:** Wir bauen fast alles mit **WS2815 auf 12 V**. Wer mit unseren Kabeln und Controllerboxen kompatibel bleiben will, nimmt die auch.

## Gängige Typen im Vergleich

| Typ | Spannung | Backup-Datenleitung | Gut für … |
|---|:---:|:---:|---|
| **WS2815** ⭐ | 12 V | ✅ ja | **unser Standard** – lange Strecken, wenig Spannungsabfall, ein defektes Pixel legt die Kette nicht lahm |
| WS2811 (12 V) | 12 V | – | günstige Pixelstrings und Module, 1 IC steuert mehrere LEDs (Pixelgruppen) |
| WS2813 | 5 V | ✅ ja | kurze, dichte Strecken mit Ausfallsicherheit |
| WS2812B | 5 V | – | Matrizen, kleine Objekte, kurze Strecken |
| SK6812 (RGB) | 5 V | – | wie WS2812B |

**Faustregeln**
- **12 V statt 5 V**, sobald die Strecke länger als ein paar Meter wird: bei gleicher Leistung fließt nur gut 40 % des Stroms → weniger Spannungsabfall, dünnere Kabel reichen.
- **Backup-Datenleitung** (WS2815/WS2813): fällt ein Pixel aus, läuft der Rest trotzdem weiter. Auf der Bühne Gold wert.
- **RGBW-LEDs** (z. B. SK6812 RGBW) unterstützt die aktuelle Firmware des neuen Controllers nicht – sie arbeitet mit 3 Kanälen (RGB) pro Pixel.

## Unser Standard: WS2815, 12 V

| | |
|---|---|
| Protokoll | WS2815 (WS281x-kompatibel, mit Backup-Datenleitung) |
| Spannung | 12 V |
| Max. Stromstärke pro LED | 15 mA |
| Bezugsquelle | [AliExpress (BST Xnbada LED Strip Store)](https://de.aliexpress.com/item/1005004289391906.html) – dort **„WS2815 DC12V“** auswählen, dazu Pixeldichte und Schutzart |

## Anschließen an unseren Standard

Egal welche LED: Am Element kommt unser **4-poliger LP16-Anschluss** dran (siehe [Stecker](stecker-lp16.md) und [Kabel](kabel.md)).
LEDs ohne Backup-Datenleitung lassen **Pin 1 (Backup)** einfach frei.

Für 5-V-LEDs gilt: Unsere 12-V-Controllerboxen liefern 12 V auf die Kabel – **5-V-LEDs dort nie einstecken!** 5-V-Elemente brauchen eine eigene Einspeisung und sollten deutlich markiert sein.
