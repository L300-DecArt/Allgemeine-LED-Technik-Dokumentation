[← Übersicht](../README.md)

# Art-Net einrichten

Die Controller bekommen ihre Pixeldaten per **Art-Net** über das Netzwerk – von Resolume, ShizoEngine, einem Lichtpult oder jeder anderen Software, die Art-Net senden kann.

> Diese Seite beschreibt die aktuelle Shizo-Firmware (Controller V4). Die ältere Firmware auf dem [Controller V1](controller-v1-wt32.md) funktioniert ähnlich, die Menüs können aber abweichen.

## Grundbegriffe

| Begriff | Bedeutung |
|---|---|
| **Universe** | Ein Paket mit 512 Kanälen. Ein RGB-Pixel braucht 3 Kanäle → max. 170 volle Pixel pro Universe. |
| **Ausgang** | Ein physischer LED-Anschluss am Controller. |
| **Segment** | Ein Abschnitt auf einem Ausgang (z. B. ein LED-Element), im Webinterface frei anlegbar. |

## Netzwerk

Ab Werk startet die Firmware mit diesen Einstellungen:

| | Standard |
|---|---|
| IP-Adresse | `2.0.0.10` |
| Gateway | `2.0.0.1` |
| Netzmaske | `255.255.255.0` |
| DHCP-Server | aus |

Der Bereich `2.x.x.x` ist der klassische Art-Net-Bereich. Dein Rechner braucht eine IP im selben Netz, z. B. `2.0.0.1` mit Maske `255.255.255.0`.

**Mehrere Controller:** Jeder Controller braucht eine **eigene IP**. Vorschlag für ein festes Schema:

| Gerät | IP |
|---|---|
| Rechner / Lichtsteuerung | `2.0.0.1` |
| Controller 1 | `2.0.0.10` |
| Controller 2 | `2.0.0.11` |
| Controller 3 | `2.0.0.12` |
| … | … |

Die IP am besten **außen auf die Controllerbox kleben**.

Statt eines eigenen Netzes kann der Controller auch per **WLAN** in ein bestehendes Netz – dafür im Webinterface unter *Connect to WLANs* das Netzwerk eintragen.

## Universen und Ausgänge

Im Webinterface legst du im **Segment-Editor** pro Ausgang die Segmente an (Breite × Höhe × Anzahl). Die Firmware verteilt die Pixeldaten dann **fortlaufend auf Universen**, beginnend bei **Universe 0**:

- Jeder Ausgang belegt so viele Universen, wie er braucht.
- Der nächste Ausgang fängt mit dem nächsten freien Universe an.
- Die **Art-Net-Map** unter dem Segment-Editor zeigt genau, welches Universe zu welchem Ausgang und Segment gehört – und wo ein Universe endet. **Richte die Software genau nach dieser Map ein**, dann stimmen die Pixel.

Beispiel mit 340 LEDs pro Ausgang (2 Universen pro Ausgang):

| Ausgang | Universen |
|---|---|
| 1 | 0, 1 |
| 2 | 2, 3 |
| 3 | 4, 5 |
| 4 | 6, 7 |

> 💡 Für flüssige 60 FPS: **max. 2 Universen pro Ausgang** beim Controller V1.

## Software einrichten

Grundsätzlich überall gleich:

1. Art-Net-Ausgabe aktivieren und die **IP des Controllers** als Ziel eintragen (oder Broadcast, wenn nur ein Controller im Netz ist).
2. Pixel-Fixture bzw. LED-Streifen anlegen: Anzahl Pixel, **RGB**, 3 Kanäle pro Pixel.
3. Jedem Fixture das **Universe** aus der Art-Net-Map zuweisen.
4. Pixel auf dem Mapping-Bild platzieren.

**Resolume Arena:** Die Art-Net-Ausgabe (Lumiverse, Ziel-IP) wird in den Einstellungen unter *DMX* eingerichtet, die Pixel-Fixtures im *Advanced Output*.

## Wenn nichts ankommt

Siehe [Fehlersuche](fehlersuche.md#element-reagiert-nicht-auf-art-net).
