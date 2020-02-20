Archlinux Installation
======================

.. code::

   # Bios Settings?

   # Time Settings?

   # keyboard Settings
   loadkeys de-latin1-nodeadkeys

   # connect to wlan


   # show disk status
   lsblk

   # delete disk if you have ssd
   # https://wiki.archlinux.de/title/Dm-crypt#Verschl.C3.BCsselung_anlegen
   blkdiscard /dev/nvme0n1

   # check if disk is clean now
   lsblk

   # partition
   # TODO: links
   gdisk /dev/nvme0n1
   - create 512MB boot / EFI - type: ef00
   - rest for root (LUKS) - type: 8309

   # show disk status
   lsblk

   # LUKS anlegen
   cryptsetup luksFormat /dev/nvme0n1p2
   cryptsetup open /dev/nvme0n1p2 cryptroot

   # create and mount filesystems
   mkfs.ext4 /dev/mapper/cryptroot
   mount /dev/mapper/cryptroot /mnt
   # https://wiki.archlinux.org/index.php/EFI_system_partition#Format_the_partition
   mkfs.fat -F32 /dev/nvme0n1p1
   mkdir /mnt/boot
   mount /dev/nvme0n1p1 /mnt/boot

   # swap file erstellen
   # https://wiki.archlinux.org/index.php/Swap#Swap_file_creation
   # TODO: Link zu Ubuntu Seite
   fallocate -l 20G /mnt/swapfile
   chmod 600 /mnt/swapfile
   mkswap /mnt/swapfile
   swapon /mnt/swapfile

   #select mirrors
   nano /etc/pacman.d/mirrorlist

   # install packages
   pacstrap /mnt base linux linux-firmware
   pacstrap /mnt nano gnome cryptsetup
   pacstrap /mnt efibootmgr dosfstools gptfdisk

   # gen and check fstab
   genfstab -U /mnt >> /mnt/etc/fstab
   less /mnt/etc/fstab

   #Chroot
   arch-chroot /mnt

   #Time zone
   ln -sf /usr/share/zoneinfo/Europe/Berlin /etc/localtime
   hwclock --systohc

   nano /etc/locale.gen
   - remove comment for de_DE UTF-8
   - remove comment for en_US UTF-8
   locale-gen
   nano /etc/locale.conf

   # see: http://www.gentoo.org/doc/en/guide-localization.xml#doc_chap3
   LANG="en_US.UTF-8"
   LC_TIME="de_DE.UTF-8"

   nano /etc/vconsole.conf
   KEYMAP=de-latin1-nodeadkeys

   nano /etc/hostname
   - enter hostname

   nano /etc/hosts

   127.0.0.1	localhost
   ::1		localhost
   127.0.1.1	myhostname.localdomain	myhostname

   nano /etc/mkinitcpio.conf

   - TODO: add content

   mkinitcpio -P

   passwd

   # install systemd-boot
   bootctl install

   nano /boot/loader/entries/arch-uefi.conf
   nano /boot/loader/entries/arch-uefi-fallback.conf
   nano /boot/loader/loader.conf

   # TODO: add content later

   bootctl update

   exit
   umount -R /mnt
   reboot

   # create user
   useradd <username> -m -s /bin/bash
   passwd <username>

   #gnome aktivieren
   systemctl enable gdm.service
   systemctl enable NetworkManager

   reboot

   # microcode
   # https://wiki.archlinux.org/index.php/Microcode
   pacman -S amd-ucode
   # add in boot config
   initrd  /cpu_manufacturer-ucode.img

   # TODO: fstrim
   systemctl enable fstrim.timer

   # TODO: https://wiki.archlinux.org/index.php/Swap#Swappiness
   nano /etc/sysctl.d/99-swappiness.conf

   vm.swappiness=10

   # Leneove ThinkPad T495x specific

   # mask this
   # https://wiki.archlinux.org/index.php/Lenovo_ThinkPad_T495s#Backlight
   systemctl mask systemd-backlight@backlight:acpi_video0.service
