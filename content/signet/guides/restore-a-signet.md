---
title: Recover from a failed firmware update 
weight: 30
---

When updating Signet's firmware if Signet's connection to the host computer is interrupted the Signet will stop functioning. At this time the only way to recover from a partial firmware update is to load the firmware by switching the Signet into bootloader mode which requires chaning a DIP switch position on the Signet circuit board. The recovery steps are as follows:


1. Download the latest DFU firmware binary from the firmware DFU [directory](https://nthdimtech.com/downloads/signet-releases/firmware/dfu/)

1. Get "dfu-util"
	- On GNU/Linux you can get it from your distribution's package manager.
	- On MacOS it can be installed by [brew](https://brew.sh) with the command

		```bash
		brew install dfu-util
		```
	- On Windows you can download and unzip the latest release [archive](http://dfu-util.sourceforge.net/releases/dfu-util-0.9-win64.zip)
	- For additional help check the dfu-util [homepage](http://dfu-util.sourceforge.net/)

1. Remove the screw connecting the two halves of the Signet enclosure

1. Separate the two halves of your Signet enclosure by inserting a fingernail or a flat tool into the snap on the keyring loop. Do this with the button facing down so that the button doesn't fall out.

1. Remove the film covering the Signet board's DIP switch (if present)

1. With a toothpick or other small tool change move the DIP switch position toward the silkscreen label "bootsw"

1. Reconnect the device (without putting it back in the case). One of the device's LED's should be on. 

1. On Windows only:
	1. Download and run [ZiDag](https://github.com/pbatard/libwdi/releases/download/b721/zadig-2.4.exe)
	1. Click 'Options->List all devices'
	1. Select "STM32 Bootloader" from the main pulldown menu
	1. Click the "Install driver button"

1. Install firmware by running the following command, replacing '\<firmware version\>' with the DFU firmware version you downloaded. Due to a timing issue the command will fail some of the time. Try multiple times if neccisary until the no errors are reported.
	- On MacOS and GNU/Linux
	
		```bash
		sudo dfu-util -a 0 -s 0x8000000 -D signet-<firmware version>.dfu
		```
	- On Windows
	
		```bash
		dfu-util -a 0 -s 0x8000000 -D signet-<firmware version>.dfu
		```

1. Disconnect the device and move the DIP switch position back to the middle position.

1. Reassemble your Signet by first snaping the enclosure halves back together (again with the button facing down) then screwing the halves together until the screw head is flush with the enclosure. Warning: Tightening more can strip the threads.

