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
    
## Stecker:<br>
  !!!Ausgang ist immer weiblich und Eingang ist immer männlich!!!<br>

  Der passende Stecker zu unseren Anforderungen ist der:


  ### EW-LP16 - 4 Polig:
  
  Kabelaußendurchmesser: 7 - 9mm
    
  Max Stromstärke: 10A


### Clips müssen immer auf Kabelseite sein!
  Aliexpress Links:
  
  [männlicher Stecker](https://de.aliexpress.com/item/1005006403420945.html?spm=a2g0o.cart.0.0.3ce54ae4bq4xFz&mp=1&gatewayAdapt=glo2deu)

  [weiblicher Stecker](https://de.aliexpress.com/item/1005007946297249.html?pdp_npi=4%40dis%21EUR%21%E2%82%AC%201%2C72%21%E2%82%AC%201%2C29%21%21%211.98%211.48%21%40211b80e117514406703254875ed2db%2112000042969687459%21sh%21DE%210%21X&spm=a2g0o.store_pc_allItems_or_groupList.new_all_items_2007603037704.1005007946297249&gatewayAdapt=glo2deu)

  [männliche eckige Buchse](https://de.aliexpress.com/item/1005007946297249.html?pdp_npi=4%40dis%21EUR%21%E2%82%AC%201%2C72%21%E2%82%AC%201%2C29%21%21%211.98%211.48%21%40211b80e117514406703254875ed2db%2112000042969687459%21sh%21DE%210%21X&spm=a2g0o.store_pc_allItems_or_groupList.new_all_items_2007603037704.1005007946297249&gatewayAdapt=glo2deu)
  
  [weibliche eckige Buchse:](https://de.aliexpress.com/item/1005006403420945.html?spm=a2g0o.cart.0.0.3ce54ae4bq4xFz&mp=1&gatewayAdapt=glo2deu)

  [weibliche runde Buchse:](https://de.aliexpress.com/item/1005008326481915.html?pdp_npi=4%40dis%21EUR%21%E2%82%AC%202%2C79%21%E2%82%AC%202%2C09%21%21%213.21%212.40%21%40211b80e117514408456598660ed2db%2112000044613732494%21sh%21DE%210%21X&spm=a2g0o.store_pc_allItems_or_groupList.new_all_items_2007603037704.1005008326481915&gatewayAdapt=glo2deu)

  [männlicher runde Buchse](https://de.aliexpress.com/item/1005007641514787.html?pdp_npi=4%40dis%21EUR%21%E2%82%AC%202%2C66%21%E2%82%AC%201%2C99%21%21%213.06%212.29%21%40211b80e117514408723671144ed2db%2112000041615752515%21sh%21DE%210%21X&spm=a2g0o.store_pc_allItems_or_groupList.new_all_items_2007603037704.1005007641514787&gatewayAdapt=glo2deu)


  [LINK ZUM HERSTELLER: POWER SIGNAL DATE CONNECTOR STORE](https://de.aliexpress.com/store/1102181980?spm=a2g0o.store_pc_allItems_or_groupList.pcShopHead_2003108905688.0)

Die Pinbelegung sieht dabei wie folgt aus:

![alt_text](https://github.com/L300-DecArt/Allgemeine-LED-Technik-Dokumentation/blob/main/Bilder/LP-16_Pinbelegung.png)

am H05rn-f 4Gx0,75mm^2 empfehlt sich folgende Belegung:

Pin 1 - Backup - Braun<br>
Pin 2 - Data   - Gelbgrün<br>
Pin 3 - +12V   - Grau<br>
Pin 4 -  GND   - Schwarz<br>
  
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


