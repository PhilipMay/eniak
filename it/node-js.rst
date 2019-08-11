Node.js
========

Install on Mac
--------------

To install `Node.js <https://nodejs.org/>`_ we use the `Node Version Manager (nvm) <https://github.com/nvm-sh/nvm>`_.
To install nvm we use `Homebrew <https://brew.sh/>`_: ``brew install nvm``

After nvm installation we get this message:

.. code-block:: bash

   [...]
   You should create NVM's working directory if it doesn't exist:

     mkdir ~/.nvm

   Add the following to ~/.bash_profile or your desired shell
   configuration file:

     export NVM_DIR="$HOME/.nvm"
     [ -s "/usr/local/opt/nvm/nvm.sh" ] && . "/usr/local/opt/nvm/nvm.sh"  # This loads nvm
     [ -s "/usr/local/opt/nvm/etc/bash_completion" ] && . "/usr/local/opt/nvm/etc/bash_completion"  # This loads nvm bash_completion

   You can set $NVM_DIR to any location, but leaving it unchanged from
   /usr/local/opt/nvm will destroy any nvm-installed Node installations
   upon upgrade/reinstall.

   Type `nvm help` for further information.

   Bash completion has been installed to:
     /usr/local/etc/bash_completion.d

After creating ``~/.nvm`` and editing ``~/.bash_profile`` we load the changes: ``source ~/.bash_profile``

With ``nvm install node`` we install the latest version of Node.js.
