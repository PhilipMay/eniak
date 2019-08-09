PIP How-To
==========

Install and Update packages from a File
---------------------------------------

For pip you can create so called `requirements
files <https://pip.pypa.io/en/stable/user_guide/#requirements-files>`__.
These files just list one package per line. Packages from this file can
be installes with ``pip install -r <requirements_file.txt>`` and updatet
with ``pip install -r <requirements_file.txt> -U``. The update only
makes sence when you do not specify a version number with the package.

Since pip does not support an "update all" mechanism this is a good way
to install and update the needed packages.

Install GIT development code
----------------------------

.. code:: bash

   pip install git+<https_git_clone_link>

   # for branch_name:
   pip install git+<https_git_clone_link>@<branch_name>

To put it into a requirements file just add this:
``git+<https_git_clone_link>`` instead of the normal package name.

Install editable local Projects
-------------------------------

also see:
https://pip.pypa.io/en/stable/reference/pip_install/#editable-installs

.. code:: bash

   pip install -e .

FAQ
---

Wo speichert pip die Pakete unter Linux?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Die Pakete werden unter
``%%~/.local/lib/<python_version>/site-packages/%%`` gespeichert. Dieses
gilt natürlich nur wenn pip ohne Environment-Manager wie zum Beispiel
conda genutzt wird.
