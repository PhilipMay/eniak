Freifunk
========

Links
-----

-  `Freifunk <https://freifunk.net/>`__
-  `Freifunk Forum <https://forum.freifunk.net/>`__
-  :doc:`Meine Freifunk Hardware <meine-freifunk-hardware>`
-  `Pico Peering Agreement <http://picopeer.net/>`__
-  Braunschweig

   -  `Freifunk Braunschweig <https://freifunk-bs.de/>`__
   -  `Freifunk Firmware
      Braunschweig <http://firmware.freifunk-bs.de/>`__
   -  `Freifunk Braunschweig Karte <https://freifunk-bs.de/map/>`__
   -  `GitLab Stratum 0 <https://gitli.stratum0.org/explore/projects>`__
   -  `Status des aktuellen Freifunk Routers (nur wenn
      verbunden) <http://node.ffbs>`__

Router
------

.. warning::
   Devices with ≤4MB flash and/or ≤32MB
   ram will work but they will be very limited (usually they can't install
   or run additional packages) because they have low RAM and flash space.
   Consider this when choosing a device to buy, or when deciding to flash
   OpenWrt on your device because it is listed as supported.
   Also see: https://openwrt.org/supported_devices/432_warning

TP-Link TL-WR841N/ND
~~~~~~~~~~~~~~~~~~~~

-  :doc:`TP-Link TL-WR841N & TL-WR841ND </ff/tp-link-tl-wr841n-tl-wr841nd>`
-  Speicher: 4MB Flash, 32MB RAM :!:
-  Aufgrund des relativ kleinen 4MB Flash-Speichers ist die weitere
   Kompabilität zu zukünftigen Updates offen
-  Unterstützung zur Zeit nur bis Version 12 - Version 13 oder höher
   geht noch nicht
-  OpenWRT Link: https://openwrt.org/toh/tp-link/tl-wr841nd
-  Versionen von FF BS unterstützt: 3, 5, 7 bis 12
-  Original Firmware Download:
   https://www.tp-link.com/no/support/download/tl-wr841nd/

Archer C7 AC1750
~~~~~~~~~~~~~~~~

-  Speicher

   -  Version 1: 8MB Flash, 128MB RAM
   -  Version 2 bis 5: 16MB Flash, 128MB RAM @ 720MHz bis 775MHz

-  Achtung: Für FFBS gibt es nur die Firmware in Version 2, 4 und 5
-  Empfehlungen

   -  https://wiki.freifunk-franken.de/w/Portal:Hardware

-  OpenWRT Seite: https://openwrt.org/toh/tp-link/archer-c7-1750
-  TP-Link Support:
   https://www.tp-link.com/de/support/download/archer-c7/

AVM FRITZ!Box 4020
~~~~~~~~~~~~~~~~~~

-  Speicher: 16MB Flash, 128MB RAM @ 750MHz
-  OpenWRT Seite: https://openwrt.org/toh/avm/fritz.box.4020

AVM FRITZ!Box 4040
~~~~~~~~~~~~~~~~~~

-  Speicher: 32MB Flash, 256MB RAM
-  OpenWRT Seite: https://openwrt.org/toh/avm/avm_fritz_box_4040

TP-Link CPE210
~~~~~~~~~~~~~~

-  Achtung: Nur Version 1 und 2 - nicht Version 3
-  Speicher: 8MB Flash, 64MB RAM
-  Empfehlungen

   -  https://wiki.freifunk-franken.de/w/Portal:Hardware#TP-Link_CPE210

-  OpenWRT Seite: https://openwrt.org/toh/tp-link/cpe210

Unifi
~~~~~

-  OpenWRT Link: https://openwrt.org/toh/ubiquiti/unifiac
-  Unifi Vergleich:
   https://help.ubnt.com/hc/en-us/articles/360008036574-UniFi-Access-Point-Comparison-Charts
-  Router flashen:
   http://www.netz39.de/wiki/freifunk:anleitungen:ubiquitigeraete

Unifi AC Lite
^^^^^^^^^^^^^

-  Empfohlen

   -  https://darmstadt.freifunk.net/mitmachen/unterstuetzte-geraete/

UniFi AC Mesh
^^^^^^^^^^^^^

-  Empfohlen

   -  https://darmstadt.freifunk.net/mitmachen/unterstuetzte-geraete/

TP-Link TL-WR1043N/ND
~~~~~~~~~~~~~~~~~~~~~

-  Speicher

   -  Version 1: 8MB Flash, 32MB RAM :!:
   -  Version 2 bis 5: 8MB bis 16MB Flash, 64MB RAM

-  Empfehlungen

   -  https://www.chemnitz.freifunk.net/static-mitmachen/
   -  https://ffmuc.net/wiki/p/Router#TP-Link_TL-WR1043N.2FND
   -  https://www.freifunk-donau-ries.de/2016/05/26/neue-routerbestellung-ist-da/
   -  https://www.freifunk-uelzen.de/router-empfehlungen/
   -  https://www.freifunk-bochum.de/mitmachen/der-router/

-  OpenWRT Seite: https://openwrt.org/toh/tp-link/tl-wr1043nd
-  Maximale Anzahl Clients (Erfahrungswert): > 45 -
   `Quelle <https://ffmuc.net/wiki/p/Router#TP-Link_TL-WR1043N.2FND>`__
-  Softwarefehler beim Booten - sichere Trennung zwischen lokalen
   Netzwerk und externen Netzwerk nicht gegeben -
   `Quelle <https://ffmuc.net/wiki/p/Router#TP-Link_TL-WR1043N.2FND>`__

TP-Link TL-WDR4300
~~~~~~~~~~~~~~~~~~

-  Speicher: 8MB Flash, 128MB RAM
-  OpenWRT Link: https://openwrt.org/toh/tp-link/tl-wdr4300

TP-Link TL-WDR3600
~~~~~~~~~~~~~~~~~~

-  Speicher: 8MB Flash, 128MB RAM
-  Probleme mit Version 1.5 :!: -
   https://dev.archive.openwrt.org/ticket/21593#ticket
-  OpenWRT Link: https://openwrt.org/toh/tp-link/tl-wdr3600
-  sehr alt - wird nicht mehr hergestellt

Know-how
--------

-  `Router mit TFTP
   flashen <https://ffmuc.net/wiki/p/Router_mit_TFTP_flashen>`__

Outdoor Box
~~~~~~~~~~~

-  https://wiki.freifunk.net/Outdoorf%C3%A4higen_Router_basteln
-  https://wiki.freifunk.net/Outdoor_Box
-  https://wiki.freifunk.net/DIY_Halterung
-  https://wiki.darmstadt.freifunk.net/DIY_TL-WR842ND_Outdoor_Box
-  https://wiki.darmstadt.freifunk.net/DIY_TL-WR841N_Outdoor_Box
-  http://wiki.leipzig.freifunk.net/Gehaeuse
-  https://forum.freifunk.net/t/umbau-tl-wr841nd-fuer-outdoor-einsatz/2077
-  https://www.youtube.com/watch?v=v1fI3JdK8gg

Hardware
^^^^^^^^

-  Abzweigdose / Anschlussdose

   -  165 x 125 x 75 IP 65
   -  186 x 146 x 75
   -  190 x 145 x 70 - EUR 8,65 + EUR 4,90 Versandkosten
   -  https://www.bauhaus.info/schalterdosen-deckel/spelsberg-feuchtraum-abzweigdose-abox/p/22679820

-  Power Over Ethernet Passive POE Injector

   -  `eBay
      1 <https://www.ebay.de/itm/Power-Over-Ethernet-Passive-POE-Injector-Adapter-Splitter-Cable-kit-weis/152891691504>`__
   -  `Amazon
      1 <https://www.amazon.de/RJ45-Koppler-CableCreation-Keystone-Modulverbinder-kupplung/dp/B01FHC1EXW/ref=sr_1_30?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&keywords=cat+buchse&qid=1555337780&s=gateway&sr=8-30>`__

-  Kabelverschraubung M20

   -  Kabelverschraubung
   -  Dichtring
   -  Gegenmutter
   -  `Amazon
      1 <https://www.amazon.de/Faconet%C2%AE-Kabelverschraubung-Netzwerkkabel-sichern-Zugentlastung/dp/B075B85H4C/ref=sr_1_6?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&keywords=Kabelverschraubung%2BM20&qid=1555332519&s=gateway&sr=8-6&th=1>`__

-  Kabelverschraubung M12

   -  Kabelverschraubung
   -  Dichtring
   -  Gegenmutter

-  Stufenbohrer
-  Silikon
-  Heißkleber
