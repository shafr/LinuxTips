# How to copy files to/from Openshift/Docker POD without rsync / root access / routing
Start server
```bash
wget https://raw.githubusercontent.com/stackp/Droopy/master/droopy
python droppy -p 8090
```
Using OC tools to forward port
```bash
oc login ...
oc port-forward <pod> 8090:8090
``` 
Upload file on your local machine from browser from `http://localhost:8090`
