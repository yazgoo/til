# bluetooth headset

bluetooth headset not showing up in pavucontrol

fix was to 

add the following to /etc/bluetooth/main.conf

```
[General]
Disable = Headset
```

then restart bluetooth service

```
sudo systemctl restart bluetooth
```

```
bluetoothctl connect <mac address>
```

then it should show up in pavucontrol
