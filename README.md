<img height=90px src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwiki.installgentoo.com%2Fimages%2Fthumb%2F0%2F0a%2FFreebsd.png%2F300px-Freebsd.png&f=1&nofb=1">


# FreeBSD-Stuff
This Repository is created as a reminder for post installation of the Operating System FreeBSD,
which is a Unix-Like OS.


## Post Installation (FreeBSD 13.1):
Stuff to do after installing FreeBSD

> **before doing anything make sure you use the `su` command to
emulate the root user, otherwise you may face some problems.**

### Updates
1. Install updates and patches for the running branch of FreeBSD
```
freebsd-update fetch install
```

2. Update the FreeBSD Packages Repository
```
pkg update
```

### VirtualBox Graphics & Audio Drivers:
In case you installed FreeBSD as a virtual machine using VirualBox,
VirualBox comes with graphics and audio drivers which FreeBSD may have
a problem identifying.
