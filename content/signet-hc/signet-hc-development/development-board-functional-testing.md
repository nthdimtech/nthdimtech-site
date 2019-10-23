---
title: PCBA performance testing (6/1/19) 
weight: 89
---


Our first round of testing focused on confirming basic functionality and the tests weren't sufficient for us to say that we had validated the design. We recently developed a series of test programs to review the performance and reliability of the development board. The results have all been encouraging so we will be ordering production boards soon. It's likely that soon after the production boards are similarly validated we will start our [Crowdfunding campaign](https://www.crowdsupply.com/nth-dimension/signet-high-capacity).

To help perform our tests we've taken advantage of the signal wire debug (SWD) connections on the development board. When developing the original Signet we were uncomfortable using in-circuit debugging tools since at the time we
didn't find any that were open hardware and we also typically required software that only ran on proprietary systems. This development cycle promises to be more challenging however so we have a greater need for in-circuit debugging. Thankfully there is now at least one open hardware SWD debugger now called the [Black Magic Probe](https://1bitsquared.com/products/black-magic-probe). Admittedly we are using an STLink debugger for now but we will be giving the Black Magic Probe a try soon. 

![Signet HC being debugged](/signet/images/signet-hc-swd-testing.jpg)

### USB interface speed test

To test the USB interface speed we used a template application from STMicrotronics that implements a dummy USB mass storage device that ignores writes and sends arbitrary data on reads. To perform our test we used the Unix command line utility "dd" as you can see below.

Read test: 36.7MB/s
	
```bash
> dd if=/dev/sdc of=/dev/null bs=1M count=128
128+0 records in
128+0 records out
134217728 bytes (134 MB, 128 MiB) copied, 3.65977 s, 36.7 MB/s
```

Write test: 34.3MB/s

```bash
> dd if=/dev/zero of=/dev/sdc bs=1M count=128
128+0 records in
128+0 records out
134217728 bytes (134 MB, 128 MiB) copied, 3.90831 s, 34.3 MB/s
```

These results are in-line with test results from other USB 2.0 devices. Speeds between 25-35MB/s are typical for USB 2.0 devices. Only a relative few USB 2.0 devices achieve speeds around 40MB/s. We believe we can improve on the numbers above somewhat by using direct memory access (DMA) driven transfers instead of microcontroller driven memory transfers.

### SD card speed test

To test the SD card transfer rate we wrote two small test programs. One program contained a loop that wrote 128MB to the SD card and another that wrote 128MB to the SD card. Here are the results from timing both programs:


Operation   | Speed
------------|-------
Read        | 7.5MB/s
Write       | 5.5MB/s

Both of these speeds are unacceptably low for the final product but are also not far off our our expectations on the development board. The SD card is running as 24Mhz with a 4 bit wide bus while the final product will use an eMMC
chip that will be running at 48Mhz with an 8 bit wide bus. So there is reason to expect that the production throughput values will be four times higher than those above without any software optimizations.

The write speed is especially low in this test since the write transfer size (16KB) is much lower than the flash sector erase size (128KB). This results in flash sectors being erased multiple times. Our research suggests this problem can be mitigated in production by having the microcontroller tell the memory chip to erase blocks ahead of writes.

### Real USB mass storage test

We also did a real use case test with the device identifying as USB mass storage drive backed by the SD card. To get throughput numbers we performed tests using the Unix "dd" utility in the same way we performed the USB interface test. Here are our results:

Operation   | Speed
------------|-------
Read        | 7.0MB/s
Write       | 5.3MB/s

These test results show about only a 6% reduction in speed relative to the SD card test results. The relatively low USB transfer overhead indicated by this test makes us optimistic that our end performance with the eMMC chip will be good.

We also tested writing and reading a 2GB file to the device and checking data integrity. Our test did not show any differences between the written and read data. Naturally we couldn't resist actually formatting the drive and using it as intended. We think it's a major milestone to be able to be able to use the development board as an ordinary flash drive despite it still being only test code. You can see our mass storage version of a "Hello world" test below.

![Mass storage hello world](/signet/images/signet-hc-msc-hello-world.png)

Next we'll be looking forward to seeing the performance boost of using eMMC memory and adding accelerated AES encryption to the pipeline.
