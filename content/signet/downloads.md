---
title: Downloads
weight: 30
---

## Signet Downloads

The Signet client is a standalone cross-platform application that supports Windows (7 and up), MacOS, and GNU/Linux. The latest client version is [0.9.12](/signet/release-notes/20190110_signet-client-0.9.12-notes).  The latest firmware version is [1.3.4](https://nthdimtech.com/downloads/signet-releases/firmware/signet-1.3.4.sfw). You can download a binary image below or download the [source code](#source-code) to build your own binaries.

Description      | Version | File | GPG signature
-----------------|---------|------|---------------
Windows client (64 bit)  | 0.9.12.2 |[Download](https://nthdimtech.com/downloads/signet-releases/0.9.12/windows/signet-0.9.12-64bit.exe) | [Signature](/signet/release-signatures/0.9.12/windows/signet-0.9.12-64bit.exe.sig)
MacOS client             | 0.9.12.1  |[Download](https://nthdimtech.com/downloads/signet-releases/0.9.12/macos/signet-0.9.12.dmg) | [Signature](/signet/release-signatures/0.9.12/macos/signet-0.9.12.dmg.sig)
GNU/Linux client         | 0.9.12.1  |[Download](https://nthdimtech.com/downloads/signet-releases/0.9.12/gnu-linux/signet-0.9.12) | [Signature](/signet/release-signatures/0.9.12/gnu-linux/signet-0.9.12.sig)
Android client   | 0.1 | [Download](https://nthdimtech.com/downloads/signet-releases/android/0.1/signet-0.1.apk) | [Signature](/signet/release-signatures/android/0.1/signet-0.1.apk.sig)
Firmware binary | 1.3.4  |[Download](https://nthdimtech.com/downloads/signet-releases/firmware/signet-1.3.4.sfw) | [Signature](/signet/release-signatures/firmware/signet-1.3.4.sfw.sig)
Client source code |  0.9.12.1 | [Download](https://nthdimtech.com/downloads/signet-releases/sources/signet-desktop-client-0.9.12.1.tar.bz2) | [Signature](/signet/release-signatures/sources/signet-desktop-client-0.9.12.1.tar.bz2.sig)

To verify the GPG signatures you can download Nth Dimension's public [GPG key](https://nthdimtech.com/nthdimtech.asc). The key fingerprint is

	D475 81AE 98C1 7249 9153 87BE 0E47 D2FA 6E50 979D

For additional validation you can find a copy of the key on the GitHub repository for this site [here](https://github.com/nthdimtech/nthdimtech-site/blob/master/content/nthdimtech.asc). Copies of the signature files can also be found in the [GitHub repository](https://github.com/nthdimtech/nthdimtech-site/blob/master/content/signet/release-signatures) as well.

### Windows

The Windows client has been tested on Windows 7, 8, and 10. There are no setup steps: just download and run.

### GNU/Linux

1. Download
[signet-0.9.12](https://nthdimtech.com/downloads/signet-releases/0.9.12/gnu-linux/signet-0.9.12)
then make it executable.

	```bash
chmod u+x ~/Downloads/signet-0.9.12
	```
	{{% notice note %}}
You may also want to move it to a more permanent location. Execute the commands below to copy
it to `~/bin`.

Use a path in your home directory to keep the binary separate from binaries managed by
your Linux distribution.

```bash
mkdir ~/bin
mv ~/Downloads/signet-0.9.12 ~/bin
```
	{{% /notice %}}

1. Install the Signet udev rule to allow the application to connect to the device.

	1. Download [50-signet.rules](https://nthdimtech.com/downloads/signet-releases/0.9.12/gnu-linux/50-signet.rules)
	1. Copy it to `/etc/udev/rules.d/`.

		```bash
sudo cp ~/Downloads/50-signet.rules /etc/udev/rules.d
		```

	You may need to disconnect and reconnect your Signet device for the rule to take effect.

### MacOS

1. Download the DMG file: [signet-0.9.12.dmg](https://nthdimtech.com/downloads/signet-releases/0.9.12/macos/signet-0.9.12.dmg).
1. Open the DMG file.
1. Run Signet from the disk image or copy it to a permanent location of your choice (e.g. `/Applications` or `/Desktop`)

## Past Binary Releases

You can find all past client and firmware releases [here](https://nthdimtech.com/downloads/signet-releases).

## Source Code

The Signet firmware and client are released under the [GPLv3](https://www.gnu.org/licenses/gpl.txt) license. You can find all Signet sources from the [Nth Dimension github page](https://www.github.com/nthdimtech). You can also download the [latest source archive](https://nthdimtech.com/downloads/signet-releases/sources/signet-desktop-client-0.9.12.1.tar.bz2) if you want to build the latest release or browse [past source archives](https://nthdimtech.com/downloads/signet-releases/sources/) to build an earlier version. You can
follow [these instructions](/signet/how-to-build-the-client-from-source) to build the client application from source.
