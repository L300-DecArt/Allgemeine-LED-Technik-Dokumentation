[← Übersicht](../README.md)

# Kabel konfektionieren & prüfen

So baust du ein LP16-Kabel nach unserem Standard – und prüfst es, **bevor** es auf ein Festival geht. Ein vertauschtes oder kurzgeschlossenes Kabel kann LEDs und Controller zerstören.

## Du brauchst

- [H05RN-F 4G0,75](kabel.md) in der gewünschten Länge
- 1 × LP16-**Stecker männlich MIT Clip** + 1 × LP16-**Stecker weiblich MIT Clip** (siehe [Stecker](stecker-lp16.md#für-lose-kabel--immer-mit-clip))
- Lötkolben, Lötzinn, Abisolierzange, Seitenschneider
- Multimeter mit Durchgangsprüfer
- Etiketten oder Beschriftungsband

## Schritt für Schritt

1. **Erst alles aufs Kabel schieben!** Überwurfmutter, Dichtung und Steckergehäuse auf das Kabel fädeln – in der richtigen Reihenfolge und Richtung. *Der häufigste Fehler:* Alles fertig gelötet, und das Gehäuse liegt noch auf dem Tisch.
2. **Abmanteln und abisolieren.** Außenmantel und Adern so weit abisolieren, wie es der Beipackzettel des Steckers angibt. Lieber etwas zu kurz als zu lang – blanke Litze darf nicht über den Lötkelch hinausstehen.
3. **Adern verzinnen.** Kurz verzinnen, damit keine einzelnen Litzen abstehen.
4. **Anlöten nach Belegung:**

   | Pin | Funktion | Ader |
   |:---:|---|---|
   | 1 | Backup-Daten | Braun |
   | 2 | Daten | Gelbgrün |
   | 3 | +12 V | Grau |
   | 4 | GND | Schwarz |

   Die Pin-Nummern stehen klein auf dem Einsatz. Auf beiden Kabelenden **gleich** belegen – Pin 1 auf Pin 1 usw.
5. **Zusammenbauen.** Einsatz ins Gehäuse, Gehäuse verschrauben, **Überwurfmutter fest anziehen** – sie ist Zugentlastung und Abdichtung zugleich. Der Mantel muss in der Dichtung sitzen, nicht die Einzeladern.
6. **Beschriften.** Länge auf beide Enden, z. B. „10 m“.

## Prüfen – bei jedem neuen Kabel

Multimeter auf Durchgang stellen.

| Prüfung | Messen zwischen | Erwartet |
|---|---|---|
| Durchgang jede Ader | Pin 1 ↔ Pin 1, Pin 2 ↔ Pin 2, Pin 3 ↔ Pin 3, Pin 4 ↔ Pin 4 (Anfang ↔ Ende) | ✅ piept |
| Kein Vertauschen | Pin 1 Anfang ↔ Pin 2, 3, 4 am Ende (und so weiter) | ❌ piept nicht |
| **Kein Kurzschluss** | Pin 3 (+12 V) ↔ Pin 4 (GND) am selben Ende | ❌ **piept nicht** – das ist der wichtigste Test! |
| Kein Kurzschluss Daten | Pin 2 ↔ Pin 3 und Pin 2 ↔ Pin 4 | ❌ piept nicht |

Zum Schluss einmal **am Kabel wackeln**, während der Durchgangsprüfer an einer Ader hängt – wenn es dabei aussetzt, ist eine Lötstelle kalt.

> 💡 **Tipp:** Wer viele Kabel prüfen muss, baut sich einen kleinen Prüfadapter: eine männliche und eine weibliche LP16-Einbaubuchse in einem Kästchen, die Pins auf Messbuchsen herausgeführt. Dann muss man nicht mit den Messspitzen in die Stecker fummeln.
