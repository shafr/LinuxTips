# Fix apt issues with upgrade:
```bash
sudo rm -rf /var/lib/dpkg/updates/*
sudo rm -rf /var/lib/apt/lists/*
sudo rm /var/cache/apt/*.bin
sudo apt-get clean
sudo apt-get autoremove -f
sudo apt-get update
sudo dpkg --configure -a
sudo apt-get install -f
```

Also try this one:
```bash
sudo apt-get -y --force-yes --reinstall --ignore-missing --ignore-hold install libc6 libc6-dev
sudo apt-get --fix-broken --fix-missing --assume-yes --force-yes install
```
