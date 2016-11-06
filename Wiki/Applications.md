
## Torrents
### DELUGE:
```bash
wget http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm
rpm -ivh nux-dextop-release-0-5.el7.nux.noarch.rpm
yum -y install deluge
```

### Transmission:
```bash
http://elearning.wsldp.com/pcmagazine/how-to-install-transmission-torrent-on-centos-7/
yum install epel-release
yum install transmission
```

## Streaming / Encoding
### Wowza
```bash
wget http://www.wowza.com/downloads/WowzaStreamingEngine-4-0-3/WowzaStreamingEngine-4.0.3.tar.bin
---
chmod  +x  WowzaStreamingEngine-4.0.3.tar.bin
cd /usr/local/WowzaStreamingEngine/bin
systemctl stop WowzaStreamingEngine
```

## Youtube video downloader
```bash
wget https://yt-dl.org/downloads/latest/youtube-dl
chmod +x youtube-dl
rpm -Uhv http://pkgs.repoforge.org/rpmforge-release/rpmforge-release-0.5.3-1.el7.rf.x86_64.rpm
yum update -y
yum install ffmpeg

youtube-dl --extract-audio --audio-format mp3 <url>
```

## Encode video:
```bash
ffmpeg -i LostInTranslation.mkv -vcodec copy -acodec copy LostInTranslation.mp4
```

# Centos if Vmware tools are not installed properly:
```
yum install kernel-devel gcc
yum -y install kernel-headers-$(uname -r)
echo export KERN_DIR=/usr/src/kernels/`uname -r` >> ~/.bashrc
```