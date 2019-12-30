# Ubuntu

## Package Management

### Update the System
```bash
apt update       # Fetches the list of available updates
apt list --upgradable # see list of packages that can be upgraded
apt upgrade      # Installs some updates; does not remove packages
apt full-upgrade # Installs updates; may also remove some packages, if needed
apt autoremove   # Removes any old packages that are no longer needed
```

### Get Info about a .deb File
`dpkg -I <package_name>.deb`

### List Content of a .deb File
`dpkg -c <package_name>.deb`

### List installed packages
`apt list --installed`

## Check Ubuntu Version
`lsb_release -a`

## Install VirtualBox Guest Additions
- install `build-essential` with: `sudo apt-get install build-essential`
- link the VirtualBox Guest Additions iso image to a cd drive
- cd should be auto mounted to somewhere at `/media` if XFCE or GNOME is installed
- change to that directory and execute installation: `sudo ./VBoxLinuxAdditions.run`

also see here: <https://askubuntu.com/questions/1035030/virtualbox-guest-additions-installation-problem/1047193#1047193>
