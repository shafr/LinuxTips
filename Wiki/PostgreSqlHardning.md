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
# Restart service
```
