Linux Commands
==============

Services / systemd
------------------

List enabled Services
~~~~~~~~~~~~~~~~~~~~~

``systemctl list-unit-files --state=enabled``

User Management
---------------

Create a User
~~~~~~~~~~~~~

.. code:: bash

   useradd <username> -m -s /bin/bash
   passwd <username>

Delete a User
~~~~~~~~~~~~~

User accounts can be deleted with the userdel command. The ``-r`` option
specifies that the user's home directory and mail spool should also be
deleted.

.. code:: bash

   userdel -r <username>

See also:
https://wiki.archlinux.org/index.php/users_and_groups#Other_examples_of_user_management

Add a User to a Group
~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

   gpasswd -a <username> <group>

Hardware
--------

Get Info about GPU
~~~~~~~~~~~~~~~~~~

``lshw -C display``

Get Infos about CPU
~~~~~~~~~~~~~~~~~~~

``cat /proc/cpuinfo``

Get Infos about CPU Temperature and Fans
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You need the package called ``lm-sensors``. The command is ``sensors``. Also see: https://askubuntu.com/a/15833/478988

Proxy Handling
--------------

ssh through a proxy (to an EC2 instance in this example)

``ssh -i <key_file>.pem <user>@<target_host_or_ip> -o "ProxyCommand=nc -X connect -x <proxy_ip>:<proxy_port> %h %p"``

scp through a proxy (to an EC2 instance in this example)

``scp -i ~/.ssh/<key_file>.pem -o "ProxyCommand=nc -X connect -x <proxy_ip>:<proxy_port> %h %p" <file> <user>@<target_host_or_ip>:``

Special
-------

Rotate Terminal
~~~~~~~~~~~~~~~

-  to the right:
   ``echo 1 | sudo tee /sys/class/graphics/fbcon/rotate_all``
-  to the left:
   ``echo 3 | sudo tee /sys/class/graphics/fbcon/rotate_all``
