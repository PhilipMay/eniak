# Linux Commands

## Services / systemd

### List enabled Services
`systemctl list-unit-files --state=enabled`

## User Management

### Create a User
```bash
useradd <username> -m -s /bin/bash
passwd <username>
```

### Delete a User
User accounts can be deleted with the userdel command. The `-r` option
specifies that the user\'s home directory and mail spool should also be
deleted.

`userdel -r <username>`

See also:
<https://wiki.archlinux.org/index.php/users_and_groups#Other_examples_of_user_management>

### Add a user to a Group
```bash
gpasswd -a <user> <group>
```

## Hardware

### Get Info about GPU
`lshw -C display`

## Get Infos about CPU
`cat /proc/cpuinfo`
