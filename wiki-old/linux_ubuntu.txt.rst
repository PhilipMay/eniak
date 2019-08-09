Linux & Ubuntu
==============

Check Ubuntu Version
--------------------

``lsb_release -a``

Services
--------

List enabled Services
~~~~~~~~~~~~~~~~~~~~~

``<nowiki>systemctl list-unit-files --state=enabled</nowiki>``

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

``<nowiki>apt list --installed</nowiki>``
