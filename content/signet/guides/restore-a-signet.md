---
title: Recover from a failed firmware update 
weight: 30
---

When updating Signet's firmware if Signet's connection to the host computer is interrupted the Signet will stop functioning. At this time the only way to recover from a partial firmware update is to load the firmware by switching the Signet into bootloader mode which requires chaning a DIP switch position on the Signet circuit board. The recovery steps are as follows:


1. Download the latest DFU firmware binary from the firmware DFU [directory](https://nthdimtech.com/downloads/signet-releases/firmware/dfu/)

1. Get "dfu-util": On GNU/Linux you can get "dfu-util" it from your distribution's package manager. For other operating systems the "dfu-util" project
[homepage] (http://dfu-util.sourceforge.net/) contains instructions for getting a binary release or building a version from source. 

1. On Windows: 

1. Remove the bottom screw.

1. Separate the two halves by inserting a fingernail or a flat tool into 
the snap on the keyring loop. Do this with the button facing down so 
that the button doesn't fall out.

1. Remove the film covering the DIP switch on the signet circuit board.

1. With a toothpick or other small tool change the switch position toward the silkscreen label "bootsw".

1. Reconnect the device

1. On Windows only:
	1. Download and run [ZiDag](https://github.com/pbatard/libwdi/releases/download/b721/zadig-2.4.exe)
	1. Click 'Options->List all devices'
	1. Select "STM32 Bootloader" from the main pulldown menu
	1. Click the "Install driver button"

1. To install the firmware run the following command where '\<firmware version\>' is the DFU firmware version you downloaded. Due to a timing issue the command will fail some of the time. Try multiple times if neccisary until the no errors are reported.
	- On MacOS and GNU/Linux
	
		```bash
		sudo dfu-util -a 0 -s 0x8000000 -D signet-<firmware version>.dfu
		```
	- On Windows
	
		```bash
		dfu-util -a 0 -s 0x8000000 -D signet-<firmware version>.dfu
		```

1. Disconnect the device and move the DIP switch position back to the middle position.

1. Reconnect the device. It should now work correctly.

1. Snap the enclosure halves back together (again with the button facing down).

1. Screw the halves back together: Tighten the screw until the screw head is flush with the enclosure then add an extra quarter turn. Warning: Tightening more can strip the threads. 

