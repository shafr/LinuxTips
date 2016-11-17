# Building Kernel
* Pull latest .tar.xz stable kernel file from `https://www.kernel.org/`
* Unzip it (Ramdrive would be good place)
* Copy current config file there 
```bash
cp /boot/config-$(uname -r) .config
```
* Apply patch
Check that patch file works:
```bash
patch -p1 -i <patch> --dry-run
```
Extract patch to current kernel folder
```bash
patch -p1 -i <patch>
```

* Run ui editor
```bash
make xconfig
```
* Build kernel (-j number of your kernels+1)
```bash
make all -j 9
```
