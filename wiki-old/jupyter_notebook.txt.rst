Jupyter Notebook
================

Using Jupyter with Conda
------------------------

<WRAP center round tip 60%> At the moment (Aug. 6. 2019) this problem
seems to be fixed in jupyter. No other software is needed. </WRAP>

When using Jupyter Notebook with Conda there `might be
problems <https://stackoverflow.com/questions/39604271/conda-environments-not-showing-up-in-jupyter-notebook/44786736>`__.
Jupiter might not find python packages you installed to the environment
you use. To solve this use the `nb_conda_kernels
package <https://github.com/Anaconda-Platform/nb_conda_kernels>`__.

This package is designed to be managed solely using conda. It should be
installed in then environment from which you run Jupyter Notebook or
JupyterLab. If you want to use ``my_conda_env`` as the conda environment
you want to use. Just install ``nb_conda_kernels`` this way:

.. code:: bash

   conda install -n my_conda_env nb_conda_kernels

Executing Jupyter Notebook from command line
--------------------------------------------

.. code:: bash

   jupyter nbconvert --ExecutePreprocessor.timeout=None --to notebook --execute <noteboo_name>.ipynb

The ``--ExecutePreprocessor.timeout=None`` is important to turn off the
timeout for the maximum time (in seconds) each notebook cell is allowed
to run.

also see:
https://nbconvert.readthedocs.io/en/latest/execute_api.html#executing-notebooks-from-the-command-line

<WRAP center round important 60%> If you have timeout problems - this
might help:
``<nowiki>pip install git+https://github.com/jupyter/nbconvert.git</nowiki>``
</WRAP>
