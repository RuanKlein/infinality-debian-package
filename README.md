# Infinality package for Debian

This repo is a fork of [Xiao-Long Chen](https://github.com/chenxiaolong)'s
[repo](https://github.com/chenxiaolong/Debian-Packages), only to add
installation instruction.

## Introduction

[Infinality](http://www.infinality.net/blog/) is a collection of patches
aiming to provide better font rendering and customization, and thus fixing
this problem for GNU/Linux distros.  Go for its homepage for further
information.

## Installation instruction

Thanks to [Hadrons](http://tinyurl.com/nlk7ou7) for his excellent
[post](http://forums.debian.net/viewtopic.php?f=16&t=88545), we could now
install Infinality on Debian in a couple of simple steps:

```sh
## su sucks, sudo rocks

# Install the basic requirement: Git and devscripts
sudo aptitude install git devscripts

# Clone the repo
cd /any/dir/
git clone https://github.com/cmpitg/infinality-debian-package.git

# Install and build dependencies
cd infinality-debian-package/freetype-infinality/
dpkg-checkbuilddeps
cd ../fontconfig-infinality/
dpkg-checkbuilddeps
# Then install them all

# Build the package
cd ../freetype-infinality/
./build.sh
cd ../fontconfig-infinality/
./build.sh

# Install all the .deb files
cd ../
sudo dpkg -i \
    freetype-infinality/*.deb \
    fontconfig-infinality/*.deb

# reboot and enjoy
sudo reboot
```

Tweak your settings in `/etc/profile.d/infinality-settings.sh`.

## License

Hmmm, I don't know :-D.  I find nothing in Chen's repo.
