Linux & Ubuntu
==============

Check Ubuntu Version
--------------------

``lsb_release -a``

Get Infos about CPU
-------------------

``cat /proc/cpuinfo``

Services
--------

List enabled Services
^^^^^^^^^^^^^^^^^^^^^

``systemctl list-unit-files --state=enabled``

Package Management
------------------

Update the System
^^^^^^^^^^^^^^^^^

.. code-block:: bash

   apt update       # Fetches the list of available updates
   apt upgrade      # Installs some updates; does not remove packages
   apt full-upgrade # Installs updates; may also remove some packages, if needed
   apt autoremove   # Removes any old packages that are no longer needed

Get Info about a .deb File
^^^^^^^^^^^^^^^^^^^^^^^^^^

``dpkg -I <package_name>.deb``

List Content of a .deb File
^^^^^^^^^^^^^^^^^^^^^^^^^^^

``dpkg -c <package_name>.deb``

List installed packages
^^^^^^^^^^^^^^^^^^^^^^^

``apt list --installed``
