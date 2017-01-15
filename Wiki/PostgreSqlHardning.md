# PostgreSql Hardning
### Install PostgreSql:
```bash
sudo apt-get -y install postgresql
```

### Change default port:
```bash
# Update file
/etc/postgresql/<version>/main/postgresql.conf
# Change value
port = <something else>

listen_addresses = '*'

# Restart service
```




### Enable connection from any host
```bash
#Update file: /etc/postgresql/<version>/main/pg_hba.conf
host    all             all              0.0.0.0/0                       md5
host    all             all              ::/0                            md5
```
