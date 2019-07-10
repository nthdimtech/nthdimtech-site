---
title: Downloads
weight: 30
---

## Signet Downloads

The Signet client is a standalone cross-platform application that supports Windows (7 and up), MacOS, and GNU/Linux. Read the latest client [release notes](/signet/release-notes/20190709_signet-client-0.9.14-notes) (version 0.9.14) for information on new features and improvements. [Browser plugins](#browser-plugins) for the Signet client are available for [Firefox](https://addons.mozilla.org/en-US/firefox/addon/signet/) and [Chrome](https://chrome.google.com/webstore/detail/signet/gppbigcoahebbhkhdpdlilkncbedfpbm). The latest firmware version is [1.3.4](https://nthdimtech.com/downloads/signet-releases/firmware/signet-1.3.4.sfw). You can download a binary image below or download the [source code](#source-code) to build your own binaries. Check the sections below for installation notes for your platform.

Description      | Version | File | GPG signature
-----------------|---------|------|---------------
Windows client (64 bit)  | 0.9.14 |[Download](https://nthdimtech.com/downloads/signet-releases/0.9.14/windows/signet-0.9.14-64bit.exe) | [Signature](/signet/release-signatures/0.9.14/windows/signet-0.9.14-64bit.exe.sig)
MacOS client             | 0.9.14  |[Download](https://nthdimtech.com/downloads/signet-releases/0.9.14/macos/signet-0.9.14.dmg) | [Signature](/signet/release-signatures/0.9.14/macos/signet-0.9.14.dmg.sig)
GNU/Linux client         | 0.9.14  |[Download](https://nthdimtech.com/downloads/signet-releases/0.9.14/gnu-linux/signet-0.9.14) | [Signature](/signet/release-signatures/0.9.14/gnu-linux/signet-0.9.14.sig)
GNU/Linux udev rule | 0.9.14  |[Download](https://nthdimtech.com/downloads/signet-releases/0.9.14/gnu-linux/50-signet.rules) | [Signature](/signet/release-signatures/0.9.14/gnu-linux/50-signet.rules.sig)
Android client   | 0.1.5 | [Download](https://nthdimtech.com/downloads/signet-releases/android/0.1/signet-0.1.5.apk) | [Signature](/signet/release-signatures/android/0.1/signet-0.1.5.apk.sig)
Firmware binary | 1.3.4  |[Download](https://nthdimtech.com/downloads/signet-releases/firmware/signet-1.3.4.sfw) | [Signature](/signet/release-signatures/firmware/signet-1.3.4.sfw.sig)
Client source code |  0.9.14 | [Download](https://nthdimtech.com/downloads/signet-releases/sources/signet-client-0.9.14.tar.bz2) | [Signature](/signet/release-signatures/sources/signet-client-0.9.14.tar.bz2.sig)

To verify the GPG signatures you can download Nth Dimension's public [GPG key](https://nthdimtech.com/nthdimtech.asc). The key fingerprint is

	D475 81AE 98C1 7249 9153 87BE 0E47 D2FA 6E50 979D

For additional validation you can find a copy of the key on the GitHub repository for this site [here](https://github.com/nthdimtech/nthdimtech-site/blob/master/content/nthdimtech.asc). Copies of the signature files can also be found in the [GitHub repository](https://github.com/nthdimtech/nthdimtech-site/blob/master/content/signet/release-signatures) as well.

### Browser plugins 

Browser plugins for Signet are available online for [Firefox](https://addons.mozilla.org/en-US/firefox/addon/signet/) and [Chrome](https://chrome.google.com/webstore/detail/signet/gppbigcoahebbhkhdpdlilkncbedfpbm)

Browser | Version | Install Page
--------|---------|-------
Firefox | 0.1.2   | [Install](https://addons.mozilla.org/en-US/firefox/addon/signet/)
Chrome  | 0.1.0   | [Install](https://chrome.google.com/webstore/detail/signet/gppbigcoahebbhkhdpdlilkncbedfpbm)


The sources for the plugins are inside the Signet client code. You can install the plugins using the links below. You may also download one of the standalone plugin files [here](https://nthdimtech.com/downloads/signet-releases/browser-plugins).  If you install from one of the plugin files you will not recieve automatic updates. For Chrome the only way to install from a file is through chrome://extensions with developer mode turned on.

### Android

The Android client supports android version 4.4 (Lollypop) and above. At this time the Android client has a limited set of functionality but can be used to copy account data to the clipboard for use.

1. Download the [apk](https://nthdimtech.com/downloads/signet-releases/android/0.1/signet-0.1.5.apk)

1. Tap on the APK file to initiate installation of the application
	
	{{% notice note %}}
If you have already installed the application before you may have to uninstall the current version
	{{% /notice %}}

1. Insert your Signet device.

1. Tap yes when prompted by Android to allow the application to access Signet

1. Tap yes when prompted by Android to allow the application to be launched when Signet is connected.


### Windows

The Windows client has been tested on Windows 7, 8, and 10. There are no setup steps: just download and run.

### GNU/Linux

1. Download
[signet-0.9.14](https://nthdimtech.com/downloads/signet-releases/0.9.14/gnu-linux/signet-0.9.14)
then make it executable.

	```bash
chmod u+x ~/Downloads/signet-0.9.14
	```
	{{% notice note %}}
You may also want to move it to a more permanent location. Execute the commands below to copy
it to `~/bin`.

Use a path in your home directory to keep the binary separate from binaries managed by
your Linux distribution.

```bash
mkdir ~/bin
mv ~/Downloads/signet-0.9.14 ~/bin
```
	{{% /notice %}}

1. Install the Signet udev rule to allow the application to connect to the device.

	1. Download [50-signet.rules](https://nthdimtech.com/downloads/signet-releases/0.9.14/gnu-linux/50-signet.rules)
	1. Copy it to `/etc/udev/rules.d/`.

		```bash
sudo cp ~/Downloads/50-signet.rules /etc/udev/rules.d
		```

	You may need to disconnect and reconnect your Signet device for the rule to take effect.

### MacOS

1. Download the DMG file: [signet-0.9.14.dmg](https://nthdimtech.com/downloads/signet-releases/0.9.14/macos/signet-0.9.14.dmg).
1. Open the DMG file.
1. Run Signet from the disk image or copy it to a permanent location of your choice (e.g. `/Applications` or `/Desktop`)

## Past Binary Releases

You can find all past client and firmware releases [here](https://nthdimtech.com/downloads/signet-releases).

## Source Code

The Signet firmware and client are released under the [GPLv3](https://www.gnu.org/licenses/gpl.txt) license. You can find all Signet sources from the [Nth Dimension github page](https://www.github.com/nthdimtech). You can also download the [latest source archive](https://nthdimtech.com/downloads/signet-releases/sources/signet-client-0.9.14.tar.bz2) if you want to build the latest release or browse [past source archives](https://nthdimtech.com/downloads/signet-releases/sources/) to build an earlier version. You can
follow [these instructions](/signet/how-to-build-the-client-from-source) to build the client application from source.
