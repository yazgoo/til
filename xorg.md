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

# configure keyboard via xorg.conf

Instead of running custom commands at xorg start

```bash
❯ cat /etc/X11/xorg.conf.d/00-keyboard.conf
Section "InputClass"
        Identifier "system-keyboard"
        MatchIsKeyboard "on"
        Option "XkbLayout" "fr"
        Option "XkbVariant" "bepo"
        Option "XkbOptions" "caps:swapescape"
EndSection
```
