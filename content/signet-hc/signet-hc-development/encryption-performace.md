---
title: Encryption performance testing (6/6/19) 
weight: 88
---

We'll be using AES encryption in conjunction with other algorithms to support encrypted volumes. We selected a microcontroller that featured an AES accelerator so that the encrypted volume performance would be acceptable. We've done some tests on it's performance and the maximum throughput we were able to achieve was 14.5MB/s. This is good enough but not ideal. The table below shows where how this speed relates to the other key metrics

Metric     | Speed
-----------|-------
AES Encryption/Decryption | 14.5MB/s
eMMC read/write | >30MB/s
Micro SD read/write (max) | 7.5MB/s
USB 2.0 transfer | >35MB/s

The AES speed is higher that the Micro SD speed so there is still an advantage to using an eMMC chip but unfortunately we will be using less than half of our eMMC and USB bandwidth when using AES encryption. We were able to find microcontrollers with faster AES accelerators but none of them also featured an integrated USB high-speed transceiver. Using one of these microcontrollers would require a separate USB high-speed transceiver chip. That would have increased costs and required a larger PCB. Although we really want to max out the USB and eMMC bandwidth we think that keeping the device affordable and compact is more important. We think we still have a good shot at maxing out our USB 2.0 bandwidth for unencrypted volumes.

To make sure that our AES accelerator was working as expected we used it with the mass storage device firmware we previously created with a hard-coded key. The read and written data were equal as expected but the performance dropped since we have not yet pipelined encryption with data storage and retrieval. Fortunately the SD/MMC controller, the AES accellerator, and the USB peripheral are all integrated with the microcontroller's 16 channel direct memory access (DMA) controller. We should be able to fully pipeline encrypted reads and writes so long as we supply two buffers to the USB, AES, and SD/MMC controllers. For each peripheral one buffer will be used to receive data from the previous pipeline stage via DMA and the other will be used to transmit data to the next pipeline stage via DMA.
