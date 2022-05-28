<img height=90px src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwiki.installgentoo.com%2Fimages%2Fthumb%2F0%2F0a%2FFreebsd.png%2F300px-Freebsd.png&f=1&nofb=1">


# FreeBSD-Stuff
This Repository is created as a reminder for post installation of the Operating System FreeBSD,
which is a Unix-Like OS.


## Post Installation (FreeBSD 13.1)
Stuff to do after installing FreeBSD

> **before doing anything make sure you use the `su` command to
emulate the root user, otherwise you may face some problems.**

### Updates:
1. Install updates and patches for the running branch of FreeBSD:
```
freebsd-update fetch install
```

2. Update the FreeBSD Packages Repository:
```
pkg update
```

## VirtualBox Graphics & Audio Drivers
In case you installed FreeBSD as a virtual machine using VirualBox,
VirualBox comes with graphics and audio drivers which FreeBSD may have
a problem identifying.

therefore we need to install and configure the emulators/virtualbox-ose-additions package

### Installation:
You need to install the `emulators/virtualbox-ose-additions` package using the `pkg` installer:
```
pkg install emulators/virtualbox-ose-additions
```

### Configuration:
To configure the vbox additions you will need to edit the file `/etc/rc.conf` using any text editor you have installed such as `ee` & `vi`

1. Edit `/etc/rc.conf`:
```
ee /etc/rc.conf
```
2. Add the following at the end of the `/etc/rc.conf` file:
```
vboxguest_enable="YES"
vboxservice_enable="YES"
```

## FreeBSD - Desktop
As an example we will install and configure the `mate desktop` & `slim` but feel free to pick a desktop you want

### Installing the Required Packages:
```
pkg install xorg mate-desktop mate slim
```

### Configuration:
We will need to edit the `/etc/rc.conf` and enable dbus & slim etc..

1. Edit `/etc/rc.conf`:
```
ee /etc/rc.conf
```
2. Add the following in the end of the file
```
dbus_enable="YES"
slim_enable="YES"
```

also in the slim configuration file there is a commented `default_user` which we need to uncomment and 
set it up to our username, location: `/usr/local/etc/slim.conf`
1. Edit `/usr/local/etc/slim.conf`:
```
ee /usr/local/etc/slim.conf
```
2. Ucomment `default_user` (remove the # before it)
the end result should look like this:
```
default_user  username
```

Now the final step is editing the `.xinitrc` for both user & root

user: navigate to `/home/username` by writing `cd /home/username`, 
edit `.xinitrc` and add the following:
```
exec mate-session
```

root: navigate to `/root` by writing `cd /root`, 
edit `.xinitrc` and add the same thing as the user, and reboot


![image](https://user-images.githubusercontent.com/33517160/170816213-72e4984e-c18f-4b87-b058-6c165857e4bc.png)
