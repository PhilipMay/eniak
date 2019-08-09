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
