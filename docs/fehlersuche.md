[← Übersicht](../README.md)

# Fehlersuche

Die häufigsten Probleme – grob nach Häufigkeit sortiert. **Vor jeder Fehlersuche an der Verkabelung: Strom aus.**

## Element bleibt komplett dunkel

1. **Strom da?** Mit dem Multimeter an der Buchse messen: Pin 3 (+12 V) gegen Pin 4 (GND) sollte ~12 V zeigen.
2. **Sicherung ausgelöst?** Der Sicherungshalter zeigt das per LED an → siehe [Sicherung löst aus](#sicherung-löst-aus).
3. **Datenrichtung falsch?** LED-Streifen haben eine Richtung (Pfeil auf dem Streifen). Die Daten müssen am **Eingang (männlich)** reinkommen.
4. **Kabel kaputt?** Anderes Kabel probieren oder durchmessen – siehe [Kabel prüfen](kabel-konfektionieren.md#prüfen--bei-jedem-neuen-kabel).

## Element reagiert nicht auf Art-Net

Das Element leuchtet z. B. im Test-Effekt des Controllers, aber nicht mit der Lichtsoftware:

- **Gleiches Netz?** Rechner und Controller brauchen IPs im selben Bereich (z. B. `2.0.0.1` und `2.0.0.10`, Maske `255.255.255.0`). Webinterface des Controllers im Browser aufrufen – wenn das nicht geht, kommt auch kein Art-Net an.
- **Richtige Netzwerkkarte?** Viele Programme senden Art-Net nur über eine ausgewählte Netzwerkkarte. WLAN und LAN verwechselt?
- **Richtiges Universe?** Mit der Art-Net-Map im Webinterface vergleichen – siehe [Art-Net einrichten](art-net.md#universen-und-ausgänge).
- **Firewall:** Art-Net läuft über **UDP-Port 6454** – unter Windows ggf. für die Software freigeben.

## Falsche Farben

Rot und Grün vertauscht, oder Weiß sieht komisch aus:

- **Farbreihenfolge** stimmt nicht. Viele LED-Streifen erwarten **GRB** statt RGB. Die Reihenfolge in der Software (Fixture) umstellen – oder im Controller, falls die Firmware das anbietet.
- **Weiß wird zum Ende hin gelblich/rötlich** → zu viel Spannungsabfall, siehe [Spannungsabfall & Kabellängen](stromversorgung.md#spannungsabfall--kabellängen).

## Flackern, zufällige Farben, „Glitzern“

- **GND-Verbindung prüfen.** Daten und Strom brauchen ein gemeinsames GND – besonders beim Nachspeisen mit einem zweiten Netzteil.
- **Datenleitung zu lang** bis zur ersten LED (Controller V4: max. 5 m). Kürzeres Kabel testen.
- **Wackelkontakt** in einem Stecker – am Kabel wackeln und beobachten.
- **Netzwerk überlastet:** Bei vielen Universen auf WLAN lieber Ethernet nehmen.

## Erste Pixel leuchten, ab einer Stelle ist alles dunkel oder falsch

- **Ein Pixel ist defekt** und gibt die Daten nicht weiter. Bei **WS2815** springt die Backup-Datenleitung ein – wenn trotzdem alles dahinter dunkel ist, ist die Backup-Ader (Pin 1, braun) nicht verbunden.
- **Zu wenige Pixel konfiguriert:** In der Software oder im Segment-Editor sind weniger LEDs eingestellt, als das Element hat.

## Sicherung löst aus

- **Sofort beim Einstecken:** Kurzschluss zwischen +12 V und GND – im Kabel, im Stecker oder im Element. Kabel einzeln abstecken, bis die Sicherung hält.
- **Erst bei hellen Inhalten:** Zu viele LEDs am Ausgang für die Sicherung. Bei Vollweiß zieht jede WS2815 bis zu 15 mA – rechnen siehe [Stromversorgung](stromversorgung.md#so-rechnest-du). Helligkeit begrenzen oder weniger LEDs pro Ausgang.

> Rückstellbare Sicherungen: Nach dem Auslösen den Knopf wieder eindrücken. Löst sie direkt wieder aus, ist der Fehler noch da – **nicht festhalten oder überbrücken.**

## Netzteil schaltet ab oder „pumpt“ (alles blinkt im Takt)

Das Netzteil ist **überlastet** und schaltet zum Schutz ab. Weniger Last anschließen oder ein stärkeres Netzteil nehmen – siehe [Netzteil](stromversorgung.md#netzteil).
