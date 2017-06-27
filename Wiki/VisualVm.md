# VisualVm tips
 
## How to enable verbose console logging in visualvm
`jvisualvm -J-Dnetbeans.logger.console=true`  

## How to fix issuie with no X server on cent os
```bash
yum install -y xorg-x11-server-Xorg xorg-x11-xauth xorg-x11-apps
grep -i X11Forwarding /etc/ssh/sshd_config
#Should be set to Yes
```
re-connect ssh and test:
```bash
xclock& , xeyes&
```

## How to fix issue libxtst
`if "libXtst.so.6: cannot open shared object file: No such file or directory":`

```bash
yum -y install libXtst
```

## How to debug docker using visualvm

* download and `mvn package` the project from [ejstatd](https://github.com/anthony-o/ejstatd)
* expose ports `1111 1112 1113` in your docker container
* copy `tools.jar`. If it's missing from (ojdkwindows)[https://github.com/ojdkbuild/ojdkbuild]
* run app:
```
java -cp "ejstatd-1.0.0.jar:$JAVA_HOME/lib/tools.jar" com.github.anthony_o.ejstatd.EJstatd -pr1111 -ph1112 -pv1113
```
Then add new jstatd connection on `local machine port 1111`