# Allgemeine-LED-Technik-Dokumentation
Allgemeine LED-Technik Dokumentation

Aufgelistet sind die Standarts die wir für unsere 12V WS2815 LED Technik verwenden

Controller:
  Unserer Standart soll es sein einen ESP 32 WT-32 zunutzen, dieser hat direkt einen Ethernet-Anschluss der direkt auf den Mikrocontroller gehen.
    https://de.aliexpress.com/item/1005006485369425.html?spm=a2g0o.productlist.main.3.67681b00wzVink&algo_pvid=4857ddb3-a06e-4533-b9fd-954690b4cf02&algo_exp_id=4857ddb3-a06e-4533-b9fd-954690b4cf02-1&pdp_npi=4%40dis%21EUR%219.99%219.99%21%21%2176.20%2176.20%21%402103853f17276533435462307e9603%2112000037380725559%21sea%21DE%212975965101%21X&curPageLogUid=yGFK2UEkQkuR&utparam-url=scene%3Asearch%7Cquery_from%3A

  Angestrebt werden 60FPS, daher ergeben sich folgende Limitierungen:
    Max Ausgänge: 4
    Max Universen pro Ausgang: 2
    Max LEDs pro Ausgang: 340

  Wenn keine LEDs parallel geschalten wurden:
    Max Ampere pro Ausgang: 4.08
    Max Ampere pro Controller: 16.34
   

Stecker: SP17 - 4 Polig
  Kabelaußendurchmesser 6 - 10mm
