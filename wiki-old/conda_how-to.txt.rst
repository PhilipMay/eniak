Conda How-To
============

Conda Commands
--------------

Alle Pakete aktualisieren
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   conda update --all

Siehe auch hier: https://stackoverflow.com/a/44072944/271118

Conda Cache leeren
~~~~~~~~~~~~~~~~~~

Conda hebt jedes geladene Paket in einem Cache auf. Auch solche die
nicht mehr aktuell sind. Mit folgendem Befehl leert man diesen Cache.

.. code:: bash

   conda clean -a

Siehe auch hier: https://conda.io/docs/commands/conda-clean.html

Environment anlegen
~~~~~~~~~~~~~~~~~~~

.. code:: bash

   conda create --name <new_env_name>

Siehe auch hier:
https://conda.io/docs/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands

Environment mit Python 3.6 anlegen
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   conda create --name <new_env_name> python=3.6

Siehe auch hier:
https://conda.io/docs/user-guide/tasks/manage-python.html#installing-a-different-version-of-python

Environment wechseln
~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   # Linux & Mac:
   source activate <env_name>

   # Windows:
   activate <env_name>

Siehe auch hier:
https://conda.io/docs/user-guide/tasks/manage-environments.html#activating-an-environment

Environment verlassen
~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   # Linux & Mac:
   source deactivate

   # Windows:
   deactivate

Siehe auch hier:
https://conda.io/docs/user-guide/tasks/manage-environments.html#deactivating-an-environment

Environment löschen
~~~~~~~~~~~~~~~~~~~

.. code:: bash

   conda remove --name <new_env_name> --all

Siehe auch hier:
https://conda.io/docs/user-guide/tasks/manage-environments.html#removing-an-environment

Vorhandene Environment anzeigen
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   conda info --envs

conda-forge Pakete erstellen
----------------------------

-  conda-forge: https://conda-forge.org/
-  conda install conda-verify vor dem build:
   https://github.com/conda/conda-verify
-  Beispiele:

   -  https://github.com/conda-forge/keras-feedstock
   -  https://github.com/conda-forge/numpy-feedstock

Where are the conda environments stored?
----------------------------------------

-  Mac: ``/usr/local/miniconda3/envs``

Weitere Conda-Channel konfigurieren
-----------------------------------

Wenn eine Python Bibliothek nicht im Standardverzeichnis von Conda
gepflegt wird, kann es notwendig sein weitere Channel für die
Installation zu konfigurieren.

Hierzu muss in der Conda-Bash der folgende Befehl ausgeführt werden:
``<nowiki>conda config --append channels <Channelname></nowiki>``

Den passenden Channel findet man unter https://anaconda.org

Beispiel für die Bibliothek geopPy: https://anaconda.org/search?q=geopy

|image0|

.. |image0| image:: /it/conda-channels.jpg
   :width: 400px
