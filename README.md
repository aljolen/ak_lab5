# ak_lab5
Лабораторна робота №5

# PART 1

Commands for export:
```
export ARCH=arm
```
```
export PATH=/opt/gcc-arm-8.3-2019.03-x86_64-arm-linux-gnueabihf/bin:$PATH
```
```
export CROSS_COMPILE="ccache arm-linux-gnueabihf-"
```
```
export KDIR=$HOME/repos/linux-stable
```
# PART 2

Commands for rebuild archive:
```
cd ~/repos/busybox/_install
```
```
find . | cpio -o -H newc | gzip > ../rootfs.cpio.gz
```
```
cd ..
```
# PART 3

Commands for start QEMU:
```
qemu-system-arm -kernel _install/boot/zImage -initrd rootfs.cpio.gz -machine virt -nographic -m 512 --append "root=/dev/ram0 rw console=ttyAMA0,115200 mem=512M"
```
# PART 4
## Commands for check:
```
${CROSS_COMPILE}objdump -dS hello.ko.unstripped | less
```
insmod hello.ko

rmmod hello.ko
