## Install jetty
[Instruction](http://pietervogelaar.nl/ubuntu-12-04-install-jetty-9)
## Jetty and letsencrypt
[Instruction](https://gist.github.com/xkr47/920ffe94f6a4c171ee59)

## GET HTTPS CERT from LetsEncrypt
[Generate key using Lets encrypt](https://certbot.eff.org/#ubuntuxenial-other)

## Use let's encrypt keys with Tomcat
```bash
https://community.letsencrypt.org/t/how-to-use-the-certificate-for-tomcat/3677/3
openssl pkcs12 -export -in cert.pem -inkey privkey.pem -out cert_and_key.p12 -name tomcat -CAfile chain.pem -caname root
./keytool -importkeystore -deststorepass <pass> -destkeypass <pass> -destkeystore MyDSKeyStore.jks -srckeystore cert_and_key.p12 -srcstoretype PKCS12 -srcstorepass <pass> -alias tomcat
keytool -import -trustcacerts -alias root -file chain.pem -keystore MyDSKeyStore.jks
```

Configure server.xml:
```xml
<Connector port="8443" protocol="org.apache.coyote.http11.Http11Protocol"
maxThreads="150" SSLEnabled="true" scheme="https" secure="true"
clientAuth="false" sslProtocol="TLS"
keystoreFile="/path/to/MyDSKeyStore.jks" keystorePass="<changeit>"
keyAlias="tomcat" keyPass="<changeit>"/>
```

# CentOs install python
```bash
curl -O https://www.python.org/ftp/python/2.7/Python-2.7.tgz
tar xfz Python-2.7.tgz
cd Python-2.7
./configure
make
make install
which python
python -V
```