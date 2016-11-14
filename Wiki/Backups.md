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
