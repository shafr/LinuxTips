## Add Dropbox backup
```
git clone https://github.com/andreafabrizi/Dropbox-Uploader/
chmod +x dropbox_uploader.sh
./dropbox_uploader.sh
./dropbox_uploader.sh upload /opt/tomcat/webapps /
```

## Copy files using rSync
[10 usefull commands](http://www.tecmint.com/rsync-local-remote-file-synchronization-commands/)
```
rsync -a --ignore-existing --progress --include '*.zip' /home/src/user:/remote/storage
```
(you can also use SSL key login for automatic copy)

## Borg Backup:

```bash
#install borg backup
sudo apt install borgbackup

# Init - Create folder where backups would be stored & init it (think of it as .git repo init)
borg init --encryption=repokey /media/backup/

# Do a backup
borg create -v --stats --progress \
/media/backup::<commit name> \
<folder to backup> \
--exclude <mask or path> \
--exclude <mask or path> 

# List backups
borg list

# List backup contents:
borg extract --list /media/backup::<commit name>
```

