[← Übersicht](../README.md)

# Stromversorgung & Absicherung

## So rechnest du

```
Strom pro Ausgang  = Anzahl LEDs × Strom pro LED
Leistung           = Spannung × Strom
```

Beispiel mit unserem Standard (WS2815, 12 V, max. 15 mA pro LED, 340 LEDs pro Ausgang – das ist das Maximum für 2 Art-Net-Universen):

| | Pro Ausgang | 4 Ausgänge (Controller V1) |
|---|---:|---:|
| Strom bei Vollweiß (15 mA/LED) | 5,1 A | 20,4 A |
| Leistung bei Vollweiß | 61 W | 245 W |

> ℹ️ **Unsere bisherige Auslegung** rechnet mit 12 mA pro LED: 4,08 A pro Ausgang, 195,84 W pro Controller – daher das **200-W-Netzteil** in der Controllerbox.
> Das reicht, solange die Ausgänge nicht dauerhaft voll weiß und voll hell laufen. Wer das braucht: Helligkeit in der Software begrenzen oder weniger LEDs pro Ausgang einplanen – sonst lösen die 5-A-Sicherungen aus.

Für Installationen mit eigenem Controller und weniger LEDs reichen natürlich kleinere Netzteile.

## Netzteil

| | |
|---|---|
| Typ | Schaltnetzteil 12 V, 200 W (für eine Controllerbox V1) |
| Bezugsquelle | [AliExpress](https://de.aliexpress.com/item/1005002843829663.html) – Ausgangsspannung **„12V“**, Leistung **„200W“** auswählen |

## Sicherungen

Jeder Ausgang wird einzeln abgesichert, damit ein Kurzschluss im Kabel nicht die ganze Box lahmlegt. Wir nehmen **rückstellbare Flachsicherungen** (KFZ-Bauform): nach dem Auslösen einfach wieder eindrücken, kein Ersatz nötig.

| Teil | Bezugsquelle |
|---|---|
| Rückstellbare Flachsicherung 5 A (5 Stück) | [Amazon – GLOSO](https://www.amazon.de/dp/B0CL9L8JQP) |
| 6-fach Sicherungshalter mit LED-Anzeige (12/24 V) | [Amazon](https://www.amazon.de/dp/B0CG8R1CNY) |

Beim [Controller V1](controller-v1-wt32.md) sitzen die Sicherungen extern im Halter, beim [Controller V4](controller-v4-p4-nano.md) direkt auf der Platine.
