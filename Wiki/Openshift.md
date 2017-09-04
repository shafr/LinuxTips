# How to copy files to/from Openshift/Docker POD without rsync / root access / routing
Start server
```bash
wget https://raw.githubusercontent.com/stackp/Droopy/master/droopy
python droopy --dl 8090
```
Using OC tools to forward port
```bash
oc login ...
oc port-forward <pod> 8090:8090
``` 
Upload file on your local machine from browser from `http://localhost:8090`

# How to use VisualVm with Openshift
1) Download [ejstatd](https://github.com/saikek/ejstatd) & corresponding tools.jar (from java folder) to the machine. 
You can use Droopy Tool or even Wget if you have public facing storage ) for that.

2) Run it:
```bash
java -Djava.rmi.server.hostname=localhost -cp "ejstatd-1.0.0.jar:tools1.8.jar" com.github.anthony_o.ejstatd.EJstatd -pr2222 -ph2223 -pv2224
```

3) On the VisualVm machine - login to openshift & enable port forwarding:
```bash
oc login <address> --token=<token>
oc port-forward <POD ID> 2222 2223 2224
```

4) Open VisualVm & connect jstat to local machine port 2222

# How to transfer files from / to OpenShift using Transfer.sh
I recommend checking `transfer.sh` site for more info on arguments (such as encryption)

1) Login to your pod machine, and zip files for easier transfer:
```bash
zip -9 -e -r <archive name> <file or folder to zip>
``` 
2) Provide password for archive

3) Upload files using `transfer.sh` and create any meaningful:

```bash
curl --upload-file <file> https://transfer.sh/<alias url>
```

4) Download file from other machine using your URL generated.
