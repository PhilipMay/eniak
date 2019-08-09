Screen
======

Open a Session with Name
------------------------

``screen -S <your_session_name>``

List Sessions
-------------

Do not start screen, but instead print a list of session identification
strings. Sessions marked "detached" can be resumed with ``screen -r``.
Those marked "attached" are running and have a controlling terminal.

.. code:: bash

   screen -ls

Recover a 'lost' Screen Session
-------------------------------

If your remote connection crashed while you had an open screen session
you have to detach it before you can reconnect. You do it this way:

Reattach a session and if necessary detach it first.

.. code:: bash

   screen -d -r <session_name>

Rename a session
----------------

To rename a session do:

#. Attach to the session in question
#. Press ``ctrl``\ + ``a``
#. Type ``:sessionname <your_session_name>`` – yes, the first colon is
   needed there, no extra spaces
#. Type ``enter``
