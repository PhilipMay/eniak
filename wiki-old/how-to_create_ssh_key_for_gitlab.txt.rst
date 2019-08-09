How-To create SSH Key for GitLab
================================

Voraussetzungen unter Windows
-----------------------------

-  Git Bash muss installiert sein

Vorgehen
--------

-  unter Windows Git Bash öffnen un eingeben:

.. code:: bash

   ssh-keygen -t rsa -C "your.email@example.com" -b 4096

-  die eigene Mail Adresse sollte einsetzt werden
-  als Speicherort ist der Default gut
-  den SSH Key ohne Passphrase erstellen (leere Eingabe) - warum siehe
   hier:
   https://code.visualstudio.com/docs/editor/versioncontrol#_common-questions
-  die Datei ``id_rsa.pub`` anzeigen lassen (keinesfalls id_rsa ohne
   pub), diese Datei liegt unter C:\Users\<User>\.ssh
-  den inhalt der Datei in GitLab einfügen:

   -  Profilbild klicken (oben rechts)
   -  Settings
   -  SSh Keys
   -  Inhalt bei Key einfühen
   -  Add Key klicken
