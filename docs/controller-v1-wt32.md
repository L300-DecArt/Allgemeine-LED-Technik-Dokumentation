[← Übersicht](../README.md)

# Controller V1 – WT32-ETH01

Unser erster eigener LED-Controller und die Basis der aktuellen Controllerboxen. Er bekommt Art-Net per Ethernet und gibt es auf 4 LED-Ausgänge aus.

> Für neue Projekte ist der [Controller V4](controller-v4-p4-nano.md) gedacht. V1 bleibt dokumentiert, weil viele Boxen damit im Einsatz sind.

## Eckdaten

| | |
|---|---|
| Mikrocontroller | [ESP32 WT32-ETH01](https://de.aliexpress.com/item/1005006485369425.html) (Ethernet direkt am Modul) |
| Firmware | ältere Version der Shizo-Firmware |
| Ansteuerung | Art-Net über Ethernet |
| Ziel-Bildrate | 60 FPS |
| Ausgänge | 4 |
| Universen pro Ausgang | max. 2 |
| LEDs pro Ausgang | max. 340 (= 2 × 170 RGB-Pixel) |
| Absicherung | extern, eine rückstellbare 5-A-Flachsicherung pro Ausgang (siehe [Sicherungen](stromversorgung.md#sicherungen)) – in der Regel verbaut |
| Netzteil | 12 V / 200 W in der Controllerbox (siehe [Netzteil](stromversorgung.md#netzteil)) |

Die Grenzen bei Ausgängen, Universen und LEDs ergeben sich aus den 60 FPS: Mehr Pixel pro Ausgang würden die Bildrate drücken.

## Anschlüsse an der Controllerbox

- Ethernet für Art-Net
- 230-V-Zuleitung fürs Netzteil
- 4 × LP16-Einbaubuchse **weiblich** (Ausgänge, ohne Clip) – siehe [Stecker](stecker-lp16.md)

## Leistung

Wie viel Strom die Ausgänge ziehen und warum ein 200-W-Netzteil reicht, steht unter [Stromversorgung](stromversorgung.md#so-rechnest-du).

## Weiter

- [Stückliste Controllerbox V1](stueckliste-controllerbox-v1.md)
- [Art-Net einrichten](art-net.md)
- [Fehlersuche](fehlersuche.md)
