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
```bash
compgen -g
```

## Rename group:
```bash
groupmod --new-name NEW_GROUP_NAME OLD_GROUP_NAME
```

## Add user to group
```bash
usermod -g <groupname> username
```

## Remove user
```bash
userdel <username>
```

## Rename user
```bash
sudo usermod -l newUsername oldUsername
sudo usermod -d /home/newHomeDir -m newUsername

```
[StackOverflow][rename-user]


## LOGIN as other user:   
sudo -i -u user    


[rename-user]: https://askubuntu.com/questions/34074/how-do-i-change-my-username
