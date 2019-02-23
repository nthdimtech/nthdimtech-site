---
title: Updating your Signet's firmware 
weight: 30
---

Some Signet client features depend on the latest firmware and occasionaly new firmware releases fix device bugs. To update signet firmware you
will need to download the latest firmware file and use the client to upload the new firmware.

1. Download the latest firmare binary [here](https://nthdimtech.com/downloads/signet-releases/firmware/). Download the highest numbered file with the extension ".sfw". You can also download the corresponding ".sfw.sig" file to verify the firmare's GPG signature. See the [downloads](signet/downloads) page for more information on the GPG signature files.

1. Open the Signet client and unlock the device

1. Select the menu option "Device-\>Update Firmware" and select the firmware file you downloaded

1. Carefully long press the Signet device button to start the firmware update. If the device is inadvertantly disconnected during the update you will need to perform a [manual firmware update](../restore-a-signet).

1. Once the firmware update completes you device should restart with the new firmware enabled. You can verify the firmware update by clicking on "Help-\>About"
