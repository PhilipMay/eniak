Archlinux Installation
======================

Config files
------------

Uefi Boot Config
~~~~~~~~~~~~~~~~

File ``/boot/loader/loader.conf``:

.. code:: bash

   default arch-uefi
   timeout 1
   console-mode max
   editor no

File ``/boot/loader/entries/arch-uefi.conf``:

.. code:: bash

   title   Arch Linux
   linux   /vmlinuz-linux
   initrd  /amd-ucode.img
   initrd  /initramfs-linux.img
   options root=/dev/nvme0n1p3 rw resume=/dev/nvme0n1p2 acpi_backlight=native

File ``/boot/loader/entries/arch-uefi-fallback.conf``:

.. code:: bash

   title   Arch Linux Fallback
   linux   /vmlinuz-linux
   initrd  /amd-ucode.img
   initrd  /initramfs-linux-fallback.img
   options root=/dev/nvme0n1p3 rw resume=/dev/nvme0n1p2 acpi_backlight=native

More Config Settings
~~~~~~~~~~~~~~~~~~~~

File ``/etc/locale.conf``:

.. code:: bash

   LANG=en_US.UTF-8
   LC_TIME=de_DE.UTF-8

In file ``/etc/mkinitcpio.conf`` set ``MODULES=(amdgpu)``.

Installed Packages
------------------

Installed groups:

::

   base
   base-devel
   gnome
   gnome-extra
   texlive-most

Installed packages:

::

   acpid
   amd-ucode
   archlinux-wallpaper
   auracle-git
   base
   bazel
   chromium
   code
   cups
   docker
   duplicity
   duply
   efibootmgr
   firefox
   gimp
   git
   google-chrome
   hexchat
   hplip
   inkscape
   keepassxc
   libreoffice-still
   libreoffice-still-de
   linux
   linux-firmware
   mesa-demos
   nano
   pacman-contrib
   pacutils
   powertop
   reflector
   screen
   skypeforlinux-stable-bin
   texmaker
   usbutils
   vim
   virtualbox
   virtualbox-guest-iso
   vlc
   wat-git
   wget

AUR packages:

::

   auracle-git r305.941b5aa-1
   duply 2.2-1
   google-chrome 79.0.3945.88-1
   skypeforlinux-stable-bin 8.55.0.141-1
   wat-git r29.0861966-1

Printer
-------

-  use `hplip <https://www.archlinux.de/packages/extra/x86_64/hplip>`__
-  installation with ``hp-setup -i`` as user (not root) - see
   https://wiki.archlinux.org/index.php/CUPS/Printer-specific_problems#HPLIP
