[← Übersicht](../README.md)

# Controller V4 – ESP32-P4-NANO

> 🚧 **In Entwicklung.** Die Hardware wird gerade entworfen – die Daten unten sind der aktuelle Planungsstand und können sich noch ändern. Die Firmware läuft bereits.

Der neue Controller ist **bewusst offen** gebaut: Er funktioniert mit unserem L300-Standard (12 V, WS2815, LP16), lässt sich aber genauso mit anderen Spannungen, LED-Typen und Steckern betreiben.

## Geplante Eckdaten

| | |
|---|---|
| Mikrocontroller | ESP32-P4-NANO (Ethernet + WLAN) |
| Ausgänge | 4 auf der Hauptplatine, erweiterbar mit bis zu 3 Erweiterungsplatinen à 4 Ausgänge → **bis 16 Ausgänge** |
| Strom pro Ausgang | bis 10 A (in der Praxis meist 4 – 5 A) |
| Spannung | 12 V oder 24 V; **5 V** möglich (Spannungswandler unbestückt lassen, Lötbrücke schließen) |
| Einspeisung | Stromzonen: eine Einspeisung für je 2 Ausgänge |
| Absicherung | rückstellbare Flachsicherung pro Ausgang direkt auf der Platine (5 A oder 10 A, je nach Bedarf) |
| Datenleitung | max. 5 m bis zur ersten LED |
| WLED-Option | Auf der Rückseite kann ein zweiter ESP32 (DevKitC-Format) mit **WLED** stecken. Ein Schalter auf der Platine wählt, welcher ESP die Ausgänge treibt. |
| Größe Hauptplatine | max. 100 × 100 mm |

## Firmware

Die Firmware stammt von [shizotech](https://github.com/shizotech/esp32_p4_nano_led) und ist eine eigene Alternative zu WLED:

- Webinterface mit Segment-Editor, Animations- und Code-Editor
- WLAN und Ethernet
- Art-Net – funktioniert direkt mit Resolume & Co.
- Audioreaktiv
- Frei programmierbar und erweiterbar mit **Shizoscript**

**Installation:** über den Online-Flasher, verlinkt im [Firmware-Repo](https://github.com/shizotech/esp32_p4_nano_led#how-to-install).

## Ohne unseren Standard nutzen

Für den Controller selbst ist egal, was hinten dranhängt:
- **LEDs:** alle einadrigen RGB-Pixel-LEDs mit WS281x-Protokoll – siehe [LEDs](leds.md)
- **Spannung:** 5, 12 oder 24 V – passend zu deinen LEDs
- **Stecker:** frei wählbar. Wer mit L300-Material kompatibel sein will, nimmt [LP16](stecker-lp16.md).
