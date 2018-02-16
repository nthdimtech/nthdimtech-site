---
title: How to build the client from Source
weight: 30
---

## Build

You will need the following to build the Signet client from source:

* Qt5 development environment/packages
* libgcrypt
* One or more platform specific packages.

Run the following command to download submodules if you have downloaded the source from Git:
```bash
	$ git submodule update --init
```

### GNU/Linux systems

#### Debian-based systems

Run the following command to install Signet build dependencies on Debian-based systems (Ubuntu, Linux Mint, etc.):

```bash
	$ sudo apt-get install qt5-default libqt5websockets5-dev libqt5x11extras5-dev libgcrypt20-dev zlib1g-dev libx11-dev
```

#### Ohter GNU/Linux systems

If you run another GNU/Linux system, build or install the equivalent libraries for Qt5 (with Websockets and x11extras), zlib, and libgcrypt.

#### Building

To build run qmake and then make:

```bash
	$ qmake client/client.pro
	$ make
```

The build will create a `signet` binary that you can move elsewhere.

You will need to install Signet's `udev` rule before the client will work. You can find the `udev` rule in `signet-base/signetdev/host/linux/50-signet.rules`. Use `sudo` to copy it to `/etc/udev/rules.d`:

```bash
	$ sudo cp signet-base/signetdev/host/linux/50-signet.rules /etc/udev/rules.d
```

### MacOS

To install Signet's build dependencies first install [Brew](https://brew.sh)

Once you have Brew, run:

```bash
	$ brew install qt5 libgcrypt libgpg-error zlib
```

To build Signet run:

```bash
	$ /usr/local/opt/qt5/bin/qmake client/client.pro
	$ make
```

The build will create a `signet.app` folder that you can move or copy anywhere. For example:

```bash
	$ cp -r signet.app ~/Desktop
```

### Windows

First install [MSYS2](www.msys2.com). MSYS2 will provide a build environment and a package manager to download Signet's dependencies. Once MSYS2 is installed, launch the MSYS2/MinGW-64 shell and run:

```bash
	$ pacman -S mingw-w64-x86_64-gcc mingw64-w64-x86_64-make
	$ pacman -S mingw-w64-x86_64-qt5-static mingw-w64-x86_64-zlib mingw-w64-x86_64-libgcrypt
	$ pacman -S mingw-w64-x86_64-jasper mingw-w64-x86_64-openssl
```

Now you can build:

```bash
	$ export PATH=/mingw64/qt5-static/bin:$PATH
	$ qmake client/client.pro CONFIG+=release
	$ mingw32-make
```

This will build `Signet.exe` in the `release` subdirectory. This executable should be self contained and you can copy it anywhere and run it.
