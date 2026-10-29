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

## Spannungsabfall & Kabellängen

Jedes Kabel „verbraucht“ Spannung – je länger und je mehr Strom, desto weniger kommt am LED-Element an. Bei zu wenig Spannung werden die LEDs am Ende **dunkler und rötlich**, Weiß sieht gelblich aus.

Spannungsabfall an unserem **H05RN-F 4G0,75** (Hin- und Rückleiter zusammen, ca. 0,047 Ω pro Meter Kabel):

| Strom ↓ / Kabellänge → | 5 m | 10 m | 15 m | 20 m | 30 m |
|---|---:|---:|---:|---:|---:|
| **1 A** | 0,2 V | 0,5 V | 0,7 V | 0,9 V | 1,4 V |
| **2 A** | 0,5 V | 0,9 V | 1,4 V | 1,9 V | 2,8 V |
| **3 A** | 0,7 V | 1,4 V | 2,1 V | 2,8 V | 4,2 V |
| **4 A** | 0,9 V | 1,9 V | 2,8 V | 3,7 V | 5,6 V |
| **5 A** | 1,2 V | 2,3 V | 3,5 V | 4,7 V | 7,0 V |

<sub>Dazu kommt noch der Spannungsabfall im LED-Streifen selbst. Werte bei 20 °C – warme Kabel haben etwas mehr Widerstand.</sub>

**Faustregel:** Bis etwa **1,2 V Verlust (10 %)** sieht man nichts. Daraus ergeben sich diese maximalen Kabellängen vom Controller bis zum ersten LED-Element:

| Strom am Ausgang | max. Kabellänge |
|---:|---:|
| 1 A | ≈ 25 m |
| 2 A | ≈ 13 m |
| 3 A | ≈ 8 m |
| 4 A | ≈ 6 m |
| 5 A | ≈ 5 m |

> ℹ️ Die Tabelle gilt für **Vollweiß bei voller Helligkeit**. Bei normalen Shows mit bunten, bewegten Inhalten fließt im Schnitt deutlich weniger Strom – längere Kabel gehen dann oft trotzdem. Wer sicher gehen will, plant nach der Tabelle.

### Was tun bei langen Strecken?

- **Nachspeisen:** Am weit entfernten Element ein eigenes Netzteil anschließen, das +12 V und GND dort einspeist. **GND bleibt verbunden** (sonst stimmt das Datensignal nicht mehr), **+12 V vom Controller dort trennen** – zwei Netzteile nie direkt parallel auf dieselbe Leitung.
- **Controller näher ran:** Lieber die Controllerbox in die Nähe der Elemente stellen und nur das Netzwerkkabel lang ziehen – Ethernet geht bis 100 m ohne Verluste.
- **Weniger LEDs pro Ausgang** oder die Helligkeit in der Software begrenzen.
- **24 V** statt 12 V (mit dem [Controller V4](controller-v4-p4-nano.md)): halber Strom bei gleicher Leistung → halber Spannungsabfall, im Verhältnis zur doppelten Spannung also nur ein Viertel. Braucht aber 24-V-LEDs.

## Netzteil

### Empfehlung: Mean Well LRS-Serie (12 V)

Markennetzteile mit sauberer Regelung und echten Schutzschaltungen (Kurzschluss, Überlast, Überspannung, Übertemperatur) – und trotzdem günstig. Die LRS-Serie ist geschlossen (Lochblechgehäuse) und für den Einbau in Controllerboxen gedacht, **nicht für draußen ohne Gehäuse**.

| Modell | Leistung | Strom | LEDs bei Vollweiß* | Preis ca. | Bezugsquelle |
|---|---:|---:|---:|---:|---|
| LRS-50-12 | 50 W | 4,2 A | ≈ 220 | 11 € | [Conrad](https://www.conrad.de/de/p/mean-well-lrs-50-12-schaltnetzteil-12-v-dc-4-2-a-50-4-w-1439443.html) |
| LRS-75-12 | 72 W | 6 A | ≈ 320 | 13 € | [Conrad](https://www.conrad.de/de/p/mean-well-lrs-75-12-schaltnetzteil-12-v-dc-6-a-72-w-1439450.html) |
| LRS-100-12 | 102 W | 8,5 A | ≈ 450 | 14 € | [Conrad](https://www.conrad.de/de/p/mean-well-lrs-100-12-schaltnetzteil-12-v-dc-8-5-a-102-w-1439456.html) |
| LRS-150-12 | 150 W | 12,5 A | ≈ 660 | 18 € | [Conrad](https://www.conrad.de/de/p/mean-well-lrs-150-12-schaltnetzteil-12-v-dc-12-5-a-150-w-1439463.html) |
| LRS-200-12 | 204 W | 17 A | ≈ 900 | 35 € | [Amazon (DE.STEPPERONLINE)](https://www.amazon.de/dp/B0CW97CFJ9) |
| **LRS-350-12** | 348 W | 29 A | ≈ 1.540 | 38 € | [Conrad](https://www.conrad.de/de/p/mean-well-lrs-350-12-netzteile-928489406.html) |

<sub>* WS2815 mit 15 mA pro LED, Netzteil höchstens zu 80 % ausgelastet. Preise Stand Oktober 2026, inkl. MwSt., ohne Versand.</sub>

> 💡 **Für die Controllerbox V1:** Die **LRS-350-12** kostet kaum mehr als die LRS-200-12 und schafft auch 4 voll ausgefahrene Ausgänge bei Vollweiß (245 W, siehe oben). Sie hat einen temperaturgesteuerten Lüfter – die kleineren LRS bis 200 W kühlen passiv.

Dieselben Modelle gibt es auch mit **24 V** (Endung `-24`, z. B. LRS-350-24) und **5 V** (Endung `-5`) – passend für den [Controller V4](controller-v4-p4-nano.md) oder 5-V-LEDs.

> ⚠️ **Vorsicht vor Fälschungen:** Mean-Well-Netzteile werden oft kopiert, besonders auf AliExpress und eBay. Besser bei Elektronik-Distributoren kaufen (Conrad, Reichelt, Mouser, …).

### Alternative: No-Name-Netzteil

Günstiger, aber ohne Markenqualität: [12-V-Schaltnetzteil auf AliExpress](https://de.aliexpress.com/item/1005002843829663.html) – Ausgangsspannung **„12V“**, Leistung **„200W“** auswählen. Bisher in den Controllerboxen V1 verbaut.

## Sicherungen

Jeder Ausgang wird einzeln abgesichert, damit ein Kurzschluss im Kabel nicht die ganze Box lahmlegt. Wir nehmen **rückstellbare Flachsicherungen** (KFZ-Bauform): nach dem Auslösen einfach wieder eindrücken, kein Ersatz nötig.

| Teil | Bezugsquelle |
|---|---|
| Rückstellbare Flachsicherung 5 A (5 Stück) | [Amazon – GLOSO](https://www.amazon.de/dp/B0CL9L8JQP) |
| 6-fach Sicherungshalter mit LED-Anzeige (12/24 V) | [Amazon](https://www.amazon.de/dp/B0CG8R1CNY) |

Beim [Controller V1](controller-v1-wt32.md) sitzen die Sicherungen extern im Halter, beim [Controller V4](controller-v4-p4-nano.md) direkt auf der Platine.
