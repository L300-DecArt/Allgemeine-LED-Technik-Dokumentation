# Allgemeine-LED-Technik-Dokumentation

Hier wird der Standard beschrieben den wir für unsere 12V WS2815 LED Technik verwenden

## LEDs:
  Protokoll: WS2815<br>
  Spannung: 12V<br>
  Max Stromstärke pro LED: 15mA<br>

  [WS-2815](https://de.aliexpress.com/item/1005004289391906.html?spm=a2g0o.productlist.main.1.440foJeeoJeevz&algo_pvid=3e679300-23e6-4f53-8256-4e59664eea96&algo_exp_id=3e679300-23e6-4f53-8256-4e59664eea96-0&pdp_npi=4%40dis%21EUR%2119.39%219.89%21%21%21147.90%2175.44%21%4021039cba17276415190216883e30a9%2112000038338767396%21sea%21DE%212975965101%21X&curPageLogUid=op9JRbgbQs11&utparam-url=scene%3Asearch%7Cquery_from%3A)
  

## Controller:
  Unserer Standart soll es sein einen [ESP32 WT-32]( https://de.aliexpress.com/item/1005006485369425.html?spm=a2g0o.productlist.main.3.67681b00wzVink&algo_pvid=4857ddb3-a06e-4533-b9fd-954690b4cf02&algo_exp_id=4857ddb3-a06e-4533-b9fd-954690b4cf02-1&pdp_npi=4%40dis%21EUR%219.99%219.99%21%21%2176.20%2176.20%21%402103853f17276533435462307e9603%2112000037380725559%21sea%21DE%212975965101%21X&curPageLogUid=yGFK2UEkQkuR&utparam-url=scene%3Asearch%7Cquery_from%3A) zunutzen, dieser hat direkt einen Ethernet-Anschluss der direkt auf den Mikrocontroller gehen.
   

  Angestrebt werden 60FPS, daher ergeben sich folgende Limitierungen:<br>
    Max Ausgänge: 4<br>
    Max Universen pro Ausgang: 2<br>
    Max LEDs pro Ausgang: 340<br>

  Wenn keine LEDs parallel geschalten wurden, ergeben sich dadurch folgende Stromstärken und Leistungen:<br>
    Max Stromstärke pro Ausgang: 4.08A<br>
    Max Stromstärke pro Controller: 16.32A<br>
    Max Watt pro Controller: 195.84W<br>

  Daher macht es Sinn in eine Controllerbox ein 12V 200W Netzteil zu verbauen. (siehe Netzteil)<br>
  Für Installationen mit eigenem Controller können natürlich auch Netzteile mit angepasster niedrigerer Leistung verwendet werden.

## Netzteil:

    200W Netzteil:
    https://a.aliexpress.com/_Ex9F1f7

## Sicherung:<br>

Für Controllerplatine V1:

https://www.amazon.de/dp/B0CL9L8JQP?ref=ppx_yo2ov_dt_b_fed_asin_title

https://www.amazon.de/dp/B0CG8R1CNY?ref=ppx_yo2ov_dt_b_fed_asin_title
   
    
## Kabel:<br>
  Das dünnste für unsere Stromstärken benötigte und gleichzeitig sehr hochwertige Kabel ist das:
  
  H05rn-f 4Gx0,75mm^2:<br>
    Max Stromstärke: 10A<br>
    Kabelaußendurchmesser: 6.80-8.80mm<br>

https://www.etoh24.de/diverse-h05rn-f-4g0-75mm2-schwarz-schnittlaenge.html?from=g_merchant-kabel&gad_source=1&gclid=CjwKCAjw9eO3BhBNEiwAoc0-jYx7MpJ9fFhayBmVVZVrlFNip4jZDGn0BexgIYFV-p3qBQM5n5UEcxoCvqAQAvD_BwE
    
## Stecker:

Wir verwenden durchgehend den **EW-LP16, 4-polig** (M16, IP68, Lötanschluss, Kunststoffgehäuse).

| | |
|---|---|
| Max. Stromstärke | 10 A |
| Kabelaußendurchmesser | 7 – 9 mm (passt zu H05RN-F 4G0,75) |
| Hersteller / Shop | [Power Signal Date Connector Store (AliExpress)](https://de.aliexpress.com/store/1102181980) – **alle Teile unten sind aus diesem Shop** |

### Die Regeln – bitte vor jeder Bestellung lesen!

1. **Ausgang ist immer weiblich (W, Löcher), Eingang ist immer männlich (M, Stifte).**
2. **Clips sind immer am Kabel – an BEIDEN Enden:** jedes lose Kabel hat einen **Stecker männlich MIT Clip** und einen **Stecker weiblich MIT Clip**.
3. **Alles, was fest zum Gerät gehört, hat KEINEN Clip:** Einbaubuchsen am Gehäuse (männlich am Eingang, weiblich am Ausgang) – und auch Kupplungen an fest angeschlossenen Gerätekabeln.

Warum? Jede Steckverbindung braucht genau **eine Seite MIT Clip und eine Seite OHNE Clip**. Clip + Clip rastet nicht ein, ohne + ohne hält nicht.
Weil alle Kabel Clips haben, müssen alle Geräte-Anschlüsse ohne Clip sein – dann passt jedes Kabel an jedes Gerät.

![Verbindungsschema LP16](Bilder/LP16/verbindungsschema.svg)

### Woran erkenne ich den Clip?

Der Clip ist die **silberne Metall-Lasche mit „push“-Taste** oben auf dem Stecker. Zum Lösen draufdrücken und abziehen.
Das Gegenstück ohne Clip hat an der Stelle nur eine kleine Kunststoff-Nase, in die der Clip einrastet.

| | MIT Clip (für lose Kabel) | OHNE Clip (nur für Geräte) |
|---|:---:|:---:|
| **männlich** | <img src="Bilder/LP16/kabel-maennlich-mit-clip.jpg" width="200"> | <img src="Bilder/LP16/kabel-maennlich-ohne-clip.jpg" width="200"> |
| **weiblich** | <img src="Bilder/LP16/kabel-weiblich-mit-clip.jpg" width="200"> | <img src="Bilder/LP16/kabel-weiblich-ohne-clip.jpg" width="200"> |
| | Metall-Lasche oben → rastet ein | nur Rastnase → nimmt den Clip auf |

> 💡 **Lesehilfe für den Shop:** Dort heißt es bei allen Teilen **„Plug“ = mit Clip** und **„Socket“ = ohne Clip**.
> Immer **(P) = Kunststoff** nehmen, (M) ist die Metallversion.

### Teileübersicht

Die Shop-Links sind Sammelangebote mit mehreren Varianten – **bei der Bestellung unbedingt die angegebene Variante auswählen!**

#### Für lose Kabel – immer MIT Clip

| Bild | Teil | Clip | Wofür | Link + Variante |
|:---:|---|:---:|---|---|
| <img src="Bilder/LP16/kabel-maennlich-mit-clip.jpg" width="130"> | **Stecker männlich** | ✅ MIT | Anfang jedes Kabels (geht in einen Ausgang) | [Link](https://de.aliexpress.com/item/1005006403420945.html) – Variante **„4 Pin male Plug“** |
| <img src="Bilder/LP16/kabel-weiblich-mit-clip.jpg" width="130"> | **Stecker weiblich** | ✅ MIT | Ende jedes Kabels (geht in einen Eingang) | [Link](https://de.aliexpress.com/item/1005007946297249.html) – Variante **„4 Pin Female Plug“** |

#### Für Geräte – Einbaubuchsen, immer OHNE Clip

| Bild | Teil | Montage | Wofür | Link + Variante |
|:---:|---|---|---|---|
| <img src="Bilder/LP16/buchse-weiblich-eckig.jpg" width="130"> | **Buchse weiblich, eckig** | 4 Schrauben (liegen bei) | Ausgänge (Controllerbox, LED-Element) | [Link](https://de.aliexpress.com/item/1005006403420945.html) – Variante **„4 Pin female socket“** |
| <img src="Bilder/LP16/buchse-maennlich-eckig.jpg" width="130"> | **Buchse männlich, eckig** | 4 Schrauben | Eingänge (LED-Element) | [Link](https://de.aliexpress.com/item/1005007946297249.html) – Variante **„4 Pin male socket“** |
| <img src="Bilder/LP16/buchse-weiblich-rund.jpg" width="130"> | **Buchse weiblich, rund** | Mutter (Rundloch) | Ausgänge (Controllerbox, LED-Element) | [Link](https://de.aliexpress.com/item/1005009884344833.html) – Farbe **„Female socket nut(P)“** + Pins **„4Pin“** |
| <img src="Bilder/LP16/buchse-maennlich-rund.jpg" width="130"> | **Buchse männlich, rund** | Mutter (Rundloch) | Eingänge (LED-Element) | [Link](https://de.aliexpress.com/item/1005009884344833.html) – Farbe **„Male socket nut(P)“** + Pins **„4Pin“** *(Produktbild zeigt 3-polig)* |

#### Für Geräte mit fest angeschlossenen Kabeln – Kupplungen OHNE Clip

Wenn ein LED-Element keine Einbaubuchsen hat, sondern Kabel fest rausgeführt werden, kommen an deren Enden **Kupplungen ohne Clip**. Sie verhalten sich genau wie eine Einbaubuchse – nur eben am Kabel.

| Bild | Teil | Clip | Wofür | Link + Variante |
|:---:|---|:---:|---|---|
| <img src="Bilder/LP16/kabel-maennlich-ohne-clip.jpg" width="130"> | **Kupplung männlich** | ❌ OHNE | Eingang am festen Gerätekabel | [Link](https://de.aliexpress.com/item/1005012227141734.html) – Variante **„4 Pin male socket“** |
| <img src="Bilder/LP16/kabel-weiblich-ohne-clip.jpg" width="130"> | **Kupplung weiblich** | ❌ OHNE | Ausgang am festen Gerätekabel | [Link](https://de.aliexpress.com/item/1005009884344833.html) – Farbe **„Femal Cable Socket(P)“** + Pins **„4Pin“** |

> ⚠️ **Kupplungen ohne Clip niemals an lose Kabel bauen!** Sie sehen den Steckern mit Clip sehr ähnlich – vor dem Löten immer prüfen, ob oben die Metall-Lasche drauf ist.

### Was muss ich bestellen? – Schnellcheck

| Ich baue … | Ich brauche |
|---|---|
| ein **Kabel / eine Verlängerung** | 1× **Stecker männlich MIT Clip** + 1× **Stecker weiblich MIT Clip** |
| eine **Controllerbox** | pro Ausgang 1× **Buchse weiblich** (eckig oder rund) |
| ein **LED-Element mit Gehäuse** | Eingang: 1× **Buchse männlich** · Ausgang: 1× **Buchse weiblich** (eckig oder rund) |
| ein **LED-Element mit festen Kabeln** | Eingang: 1× **Kupplung männlich OHNE Clip** · Ausgang: 1× **Kupplung weiblich OHNE Clip** |

<details>
<summary>Maßzeichnungen & Datenblatt</summary>

| Stecker männlich | Stecker weiblich | Buchse eckig | Buchse rund |
|:---:|:---:|:---:|:---:|
| <img src="Bilder/LP-16-Stecker%20M%C3%A4nnlich%202.jpg" width="200"> | <img src="Bilder/LP-16-Stecker%20Weiblich%202.jpg" width="200"> | <img src="Bilder/LP-16%20Buchse%20Weiblich%20eckig%202.png" width="200"> | <img src="Bilder/LP-16%20Buchse%20Weiblich%20rund%201.png" width="200"> |

<img src="Bilder/LP-16%20Specs.jpg" width="500">

</details>

### Pinbelegung

![LP16 Pinbelegung](Bilder/LP-16_Pinbelegung.png)

Am H05RN-F 4G0,75 mm² empfiehlt sich folgende Belegung:

| Pin | Funktion | Ader |
|:---:|---|---|
| 1 | Backup | Braun |
| 2 | Data | Gelbgrün |
| 3 | +12 V | Grau |
| 4 | GND | Schwarz |
  
## Verschraubungen:<br>
  Passende Verschraubungen für unseren Kabelausßendurchmesser sind:<br>
  <br>
    PG11:<br>
      Kabelaußendurchmesser: 5-10mm<br>
      Gewinde: M18x1,5<br>
<br>
    PG13:<br>
      Kabelaußendruchmesser: 6-11mm<br>
      Gewinde: M20x1,5<br>


