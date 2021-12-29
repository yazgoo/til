# swap escape and caps lock

```bash
setxkbmap -option caps:swapescape
```

# tearfree

https://linuxreviews.org/HOWTO_fix_screen_tearing

```
File: /etc/X11/xorg.conf.d/20-intel-gpu.conf

Section "Device"
   Identifier  "Intel Graphics"
   Driver      "intel"
   Option      "AccelMethod"  "uxa"
   Option      "TearFree" "true"
EndSection
```
