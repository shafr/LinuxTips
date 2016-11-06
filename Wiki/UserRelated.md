# User related

## create new user
```bash
sudo useradd -d /home/testuser -m testuser
sudo passwd testuser
```
## Add users to sudoers
```bash
sudo adduser <username> sudo
```

## Create new group and add user there
```bash
sudo useradd -M -s /bin/nologin -g tomcat -d /opt/tomcat tomcat
```

## Change primary group for user
```bash
usermod -g <grp> <usr>
```

## Change default bash shell:
```bash
sudo chsh <username>
/bin/bash
```

## list groups
compgen -g

## Add user to group
usermod -g <groupname> username
