Conda Installation auf Windows
==============================

#. Download Mini Conda (nicht Anaconda):
   https://conda.io/docs/user-guide/install/windows.html

   #. Für Python 3.6 und nicht 2.5 und als 64 bit Version (nicht 32 bit)

#. Proxy installieren

   #. in der ``.condarc`` Datei folgendes einfühen (und darauf achten,
      dass der Key "ssl_verify" nicht doppelt ist), diese Datei liegt
      unter ``C:\Users\<User>``

.. code:: YAML

   proxy_servers:
     http: http://user:pass@corp.com:8080
     https: https://user:pass@corp.com:8080

   ssl_verify: False

