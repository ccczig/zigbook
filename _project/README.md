# xv6-riscv-zig

* https://github.com/binarycraft007/xv6-riscv-zig
    * https://github.com/riscv2os/xv6-riscv-zig/

## build success

```
root@fqdn:~/xv6-riscv-zig# zig build
LLVM Emit Object...

root@fqdn:~/xv6-riscv-zig#

```

## run fail

```
root@fqdn:~/xv6-riscv-zig# ls zig-out
bin
root@fqdn:~/xv6-riscv-zig# cd zig-out/bin
root@fqdn:~/xv6-riscv-zig/zig-out/bin# ls
_cat   fs.img  _grind  kernel  _ln  _mkdir  _sh        _usertests  _zombie
_echo  _grep   _init   _kill   _ls  _rm     _stressfs  _wc

t@fqdn:~/xv6-riscv-zig/zig-out/bin# qemu-system-riscv64 -machine virt -bios none -kernel kernel -m 256
M -smp 3 -nographic -drive file=fs.img,if=none,format=raw,id=x0 -device virtio-blk-device,drive=x0,bus=vi
rtio-mmio-bus.0
[info] (kmain): xv6 kernel is booting
[debug] (kalloc): available [0x80024000 - 0x88000000]
[debug] (kalloc): start init kernel page allocator
[debug] (kalloc): init kernel page allocator success
[debug] (kvm): start init kernel page table
[debug] (kvm): kernel page table init success
!KERNEL PANIC!
could not find virtio disk

```
