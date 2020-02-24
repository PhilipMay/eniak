# Duply Backup with Windows and Cygwin

## Installation
- install cygwin: <https://cygwin.com/>
- first just install base packages
- install the following additional packages (by just starting `setup-x86_64.exe` again):
  - python3
  - python36-pip
  - python3-devel
  - gcc-core
  - librsync-devel
  - gnupg2
  - nano
- update `binutils` to newest (test) version (2.31.1-1)
- update pip (optional): `pip3 install --upgrade pip`
- install duplicity: `pip3 install duplicity`
- create bin dir: `mkdir bin`
- change to that dir: `cd bin`
- create link to gpg2: `ln -s /usr/bin/gpg2.exe gpg.exe`
- download duply: <https://duply.net/>
- unpack duply
- copy duply script to bin dir: `cp /cygdrive/c/Users/<your_username>/Downloads/<duply_dir>/duply .`
- change back to home dir `cd`

## Configuration of .bashrc
- edit .bashrc: `nano .bashrc`
- add `export PATH=/home/<your_username>/bin:$PATH`

# Check Installation and configuration
The following commands should execute without error or warning:
- `duplicity --version`
- `duply --version`
- `gpg --version`
