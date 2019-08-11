Linux & Ubuntu
==============

Check Ubuntu Version
--------------------

``lsb_release -a``

Services
--------

List enabled Services
~~~~~~~~~~~~~~~~~~~~~

``systemctl list-unit-files --state=enabled``

Package Management
------------------

Get Info about a .deb File
~~~~~~~~~~~~~~~~~~~~~~~~~~

``dpkg -I <package_name>.deb``

List Content of a .deb File
~~~~~~~~~~~~~~~~~~~~~~~~~~~

``dpkg -c <package_name>.deb``

List installed packages
~~~~~~~~~~~~~~~~~~~~~~~

``apt list --installed``
