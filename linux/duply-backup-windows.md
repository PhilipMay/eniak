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
  - nano
- update `binutils` to newest (test) version
- update pip (optional): `pip3 install --upgrade pip`
- install duplicity: `pip3 install duplicity`


## Configuration
- edit .bashrc: `nano .bashrc`
- add `export PATH=/home/<your_username>/bin:$PATH`
