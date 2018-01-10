---
title: Downloads
weight: 30
---

## Signet Client Downloads

The Signet client is a standalone cross-platform application that supports Windows (7 and up), MacOS,
and GNU/Linux. The latest client version is [0.9.6](/signet/downloads/signet-client-release-notes-0.9.6/).
The latest firmware version is [1.2.2](/signet/downloads/signet-firmware-release-notes-1.2.2).

Operating system      | Download
----------------------|---------------
Windows (64 bit)      | [signet-0.9.6-64bit.exe](https://nthdimtech.com/downloads/signet-releases/0.9.6/windows/signet-0.9.6-64bit.exe)
Windows (32 bit)      | [signet-0.9.6-32bit.exe](https://nthdimtech.com/downloads/signet-releases/0.9.6/windows/signet-0.9.6-32bit.exe)
Mac                   | [signet-0.9.6.dmg](https://nthdimtech.com/downloads/signet-releases/0.9.6/macos/signet-0.9.6.dmg)
Linux (Debian/Ubuntu) | [signet-0.9.6](https://nthdimtech.com/downloads/signet-releases/0.9.6/linux/signet-0.9.6)

### Windows

The Windows client has been tested on Windows 7, 8, and 10. It is avaialable in a
[32-bit version](https://nthdimtech.com/downloads/signet-releases/0.9.6/windows/signet-0.9.6-32bit.exe)
and a
[64-bit version](https://nthdimtech.com/downloads/signet-releases/0.9.6/windows/signet-0.9.6-64bit.exe).
There are no setup steps: just download and run.

### GNU/Linux

1. Download
[signet-0.9.6](https://nthdimtech.com/downloads/signet-releases/0.9.6/linux/signet-0.9.6)
then make it executable.

	```bash
chmod u+x ~/Downloads/signet-0.9.6
	```
	{{% notice note %}}
You may also want to move it to a more permanent location. Execute the commands below to copy
it to `~/bin`.

Use a path in your home directory to keep the binary separate from binaries managed by
your Linux distribution.

```bash
mkdir ~/bin
mv ~/Downloads/signet-0.9.6 ~/bin
```
	{{% /notice %}}

1. You will need to install a udev
rule to allow the application to connect to the device.

	1. Download [50-signet.rules](https://nthdimtech.com/downloads/signet-releases/0.9.6/linux/50-signet.rules)
	1. Copy it to `/etc/udev/rules.d/`.

		```bash
sudo cp ~/Downloads/50-signet.rules /etc/udev/rules.d
		```

	You may need to disconnect and reconnect your Signet device for the rule to take effect.

### MacOS

1. Download [signet-0.9.6.dmg](https://nthdimtech.com/downloads/signet-releases/0.9.6/macos/signet-0.9.6.dmg).
1. Open the application.
	The application is unsigned so Mac OS will not immediately allow you to run it. To authorize the application:
	1. Copy the Signet application in the DMG file to `/Applications` or `/Desktop`.
	1. Run it from finder.
	1. Click past the "unknown publisher" warning.

	You should be able to run it in the future 
	with no warnings or extra steps.

## Source

The Signet firmware and client are released under the [GPLv3](https://www.gnu.org/licenses/gpl.txt) license.
You can find all of the sources at the [Nth Dimension github page](https://www.github.com/nthdimtech).

## Past Releases

You can find all past client and firmware releases [here](https://nthdimtech.com/downloads/signet-releases).
