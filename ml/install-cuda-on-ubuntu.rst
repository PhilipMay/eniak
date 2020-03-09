Install CUDA on Ubuntu
======================

Just see here: https://www.tensorflow.org/install/gpu#ubuntu_1804_cuda_101

CUDA installieren - für Tensorflow 1.10
---------------------------------------

-  system update

   -  ``apt update``
   -  ``apt upgrade``

-  install CUDA Toolkit 10

   -  CUDA Download: https://developer.nvidia.com/cuda-zone
   -  Download now
   -  Linux -> x86 -> Ubuntu -> 17.04 -> deb (network)
   -  click download
   -  ``dpkg -i /<download_folder>/cuda-repo-ubuntu1710_9.2.148-1_amd64.deb``
   -  install public CUDA GPG key (see command from last message output)
   -  ``apt update``
   -  do not just install ``cuda`` now - install ``cuda-9-2`` to pin
      down the version number and avoid auto update to an other version
   -  **for Cuda 10 install cuda-10-0 and NOT just cuda-10**
   -  at install time there is a version conflict between nvidia-390 and
      libglx-mesa0 - that's why we need ``--force-overwrite`` option
      - see here:
      https://bugs.launchpad.net/ubuntu/+source/nvidia-graphics-drivers-390/+bug/1753796
      and `#Fehlermeldung <#Fehlermeldung>`__ below
   -  ``apt-get -o Dpkg::Options::="--force-overwrite" install cuda-9-2``

-  reboot to reload grafic driver
-  test grafic driver works

   -  ``nvidia-smi``

-  install cuDNN **(dev not needed)**

   -  download newest version for linux and CUDA 9.2:
      https://developer.nvidia.com/cudnn
   -  leider ist eine Anmeldung bzw. Login notwendig
   -  at this time (12th Sept. 2018) it is: cuDNN v7.2.1 (August 7,
      2018), for CUDA 9.2
   -  Download: cuDNN v7.2.1 Runtime Library for Ubuntu16.04 (Deb)
   -  Download: cuDNN v7.2.1 Developer Library for Ubuntu16.04 (Deb)
   -  manche Anleitungen empfehlen hier das tar Paket zu nehmen, die deb
      Pakete funktionieren jedoch sehr gut und können bei einem späteren
      Update einfacher wieder deinstalliert werden
   -  first install Runtime Library, then Developer Library:

      -  ``dpkg -i /<download_folder>/<Runtime_Library>``
      -  ``dpkg -i /<download_folder>/<Developer_Library>``

-  in ``.bashrc`` of the user (not root) append the following:

.. code:: bash

   # cuda settings
   export PATH=/usr/local/cuda/bin${PATH:+:${PATH}}
   export LD_LIBRARY_PATH=/usr/local/cuda/lib64:${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}

Links
-----

Weitere Links zu jedoch teilweise veralteten Anleitungen:

-  https://www.tensorflow.org/install/install_linux#NVIDIARequirements
-  https://medium.com/@taylordenouden/installing-tensorflow-gpu-on-ubuntu-18-04-89a142325138
-  https://github.com/yaroslavvb/tensorflow-community-wheels/issues/73
