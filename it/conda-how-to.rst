Conda How-to
============

Create new Conda Environment
----------------------------

.. code-block:: bash

   # create environment
   conda create --name <new_env_name>

   # create environment with python 3.6
   conda create --name <new_env_name> python=3.6

also see: https://docs.conda.io/projects/conda/en/latest/commands/create.html

Activate and deactivate Environment
-----------------------------------

.. code-block:: bash

   # activate environment
   conda activate <env_name>

   # deactivate (leave) environment
   conda deactivate

see also: https://docs.conda.io/projects/conda/en/latest/glossary.html?highlight=deactivate#activate-deactivate-environment

Update all Packages
-------------------

.. code-block:: bash

   conda update --all

see also: https://docs.conda.io/projects/conda/en/latest/commands/update.html

List all available Environments
-------------------------------

.. code-block:: bash

   conda info --envs

see also: https://docs.conda.io/projects/conda/en/latest/commands/info.html

Remove Environment
------------------

.. code-block:: bash

   conda remove --name <env_name> --all

see also: https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#removing-an-environment

Remove unused cached Packages
-----------------------------

.. code-block:: bash

   conda clean -a

also see: https://docs.conda.io/projects/conda/en/latest/commands/clean.html

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
``conda config --append channels <Channelname>``

Den passenden Channel findet man unter https://anaconda.org

Beispiel für die Bibliothek geopPy: https://anaconda.org/search?q=geopy
