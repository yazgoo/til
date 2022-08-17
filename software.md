# audio

- pacmixer, an alsamixer like interface for pulseaudio 

# video

## backlight

### [backlight_control](https://github.com/Hendrikto/backlight_control)

a simple lightweight program to handle backlight

# network

## DNS

dig as been replace with drill (packet ldns) 

## "telnet" with SSL

openssl s_client -connect host:port

## nmap

### find open TCP ports

nmap -n -PN -sT -p- localhost

## sshd

Verbose logs

```
LogLevel DEBUG3
```

Add allowed key exchange algorithms

```
 KexAlgorithms +diffie-hellman-group14-sha1
```

## SQL files

DSQ to query files
https://github.com/multiprocessio/dsq

https://datastation.multiprocess.io/blog/2022-01-11-dsq.html
