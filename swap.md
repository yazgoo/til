# swap file

taken from https://wiki.archlinux.org/title/swap


Swap file creation 
==================

Use [[dd]] to create a swap file the size of your choosing. For example, creating a 512 MiB swap file:

```bash
 # dd if=/dev/zero of=/swapfile bs=1M count=512 status=progress

 # chmod 0600 /swapfile

 # mkswap -U clear /swapfile

 # swapon /swapfile
```

`etc/fstab` :
```fstab
/swapfile none swap defaults 0 0
```
