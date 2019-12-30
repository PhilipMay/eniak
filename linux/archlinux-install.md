# Archlinux Installation

## Config files

### Uefi Boot Config

File `/boot/loader/loader.conf`:
```bash
default arch-uefi
timeout 1
console-mode max
editor no
```

File `/boot/loader/entries/arch-uefi.conf`:
```bash
title   Arch Linux
linux   /vmlinuz-linux
initrd  /amd-ucode.img
initrd  /initramfs-linux.img
options root=/dev/nvme0n1p3 rw resume=/dev/nvme0n1p2 acpi_backlight=native
```

File `/boot/loader/entries/arch-uefi-fallback.conf`:
```bash
title   Arch Linux Fallback
linux   /vmlinuz-linux
initrd  /amd-ucode.img
initrd  /initramfs-linux-fallback.img
options root=/dev/nvme0n1p3 rw resume=/dev/nvme0n1p2 acpi_backlight=native
```

### More Config Settings

File `/etc/locale.conf`:
```bash
LANG=en_US.UTF-8
LC_TIME=de_DE.UTF-8
```
