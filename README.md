# assembly-service [![Build Status](https://travis-ci.com/probonopd/assembly-service.svg?branch=master)](https://travis-ci.com/probonopd/assembly-service)

![](https://cdn-images-1.medium.com/max/800/1*PRi2K9TJEa6hO0I92P-p6A.png)

Experimental assembly Service for Flatpak, builds Flatpak into AppImage

Still in the (very) early stages. Playground. Who wants to help?

## Motivation

Let's install a simple text editor, gedit, using Flatpak on a Xubuntu 18.04 Live system:

```
sudo add-apt-repository ppa:alexlarsson/flatpak -y
sudo apt-get -y install flatpak
sudo flatpak remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
sudo flatpak install -v --noninteractive flathub org.gnome.gedit
This operation downloads around 400 MB and places no less than 48,192 files into the filesystem that take up 1.4 GB of space.
me@host:~$ find /var/lib/flatpak -type f | wc -l
48192
```

For me, it is important for me to have one file per application, a file which does not need to be installed, a file which I can copy around to different systems, a file which I can use on non-persistent Live systems, a file which I can archive for future use long after the repositories will have vanished.

So, if Flatpak is arguably great at delivering materials, and AppImage is arguably great at assembling them into shippable single-file binaries - why not combine both?
