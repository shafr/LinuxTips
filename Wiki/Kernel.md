# Building Kernel
Note that you would need lots of space for that - like 2gb for build tools and 20GB for kernels

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
make xconfig (allows search)
make gconfig (has good descriptions)
```
* Build kernel (-j number of your kernels+1)
```bash
fakeroot make-kpkg -j N --initrd --append-to-version=my-very-own-kernel kernel-image kernel-headers
make all -j 9
```
