### Docker start Stopped container:
docker start -ia <container name>

### Override entrypoint
docker run --entrypoint <entrypoint>

# Machine Hosting Docker:
## Install docker on ubuntu 16.04 (if you have issues that it hangs):
```bash
apt-get install dmsetup
dmsetup mknodes
apt-get install docker-engine
```
## Install Docker on CentOs
```bash
#Install Docker

sudo yum install -y yum-utils

sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo

sudo yum makecache fast
sudo yum -y install docker-ce
sudo systemctl start docker


#Activate Experimental features
/usr/lib/systemd/system/docker.service
ExecStart=<...> --experimental=true
sudo systemctl daemon-reload
sudo systemctl restart docker

#Compress
docker --squash
```


## Add user permissions:
```bash
sudo gpasswd -a <user> docker
```

## Docker add insecure registry (testing purpose!):
```bash
/usr/lib/systemd/system/docker.service

ExecStart ... --insecure-registry <host>:<port>

sudo systemctl daemon-reload
sudo systemctl restart docker
```

## Install docker compose
```bash
curl -L "https://github.com/docker/compose/releases/download/1.8.1/docker-compose-$(uname -s)-$(uname -m)" > /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
```

## Docker remove groups of items:
```bash
# stop all running containers
docker stop $(docker ps -q)

# remove all containers
docker rm $(docker ps -aq)

# remove all image
docker rmi $(docker images -q)

# removed untagged images
docker rmi $(docker images | grep "^<none>" | awk "{print $3}") 

#Remove old docker images
docker images -q -a | xargs --no-run-if-empty docker rmi
```



# Docker container:
## Upload file to Some server
I'm using [HFS file server](http://www.rejetto.com/hfs/?f=dl).

Create a physical folder `Incoming` and add it there - and allow to upload files. 
```bash
uploadFile(){
    curl -i -F filedata=@$1 http://<ip>:<port>/Incoming/
}
uploadFile myFile
```

## Install Netstat
```bash
yum install net-tools
```
