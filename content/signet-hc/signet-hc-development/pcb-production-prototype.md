---
title: PCBA production prototype (7/12/19)
weight: 85
---

We recently got our production prototype PCBs. All the boards we have checked so far have passed a basic test program we wrote for them. The test begins by writing to a flash memory sector and then reading the sector back to test if the data was stored correctly. Then the indicator LEDs will start blinking until the button is pressed. If the initial memory read/write test was successful then the LEDs will turn on and stay on, otherwise they will turn off. Finally the device starts up its USB interface and identifies itself as a generic SCSI device i.e. a flash memory drive.

![Production PCBA under test](/signet/images/signet-hc-prod-test.jpg)

The boards appear to be flawless. The extra planning and checking we have done seems to have paid off. We are very grateful to [Bay Area Circuits](https://bayareacircuits.com/) for fabricating the boards and [Screaming Circuits](https://screamingcircuits.com/) for the assembling them.

![Production PCBA top](/signet/images/signet-hc-prod-top.jpg)
![Production PCBA bottom](/signet/images/signet-hc-prod-bottom.jpg)

Our next step is to repeat the performance tests we ran on the development boards on the prototype boards and make sure all the performance metrics meet our expectations. Assuming we find no issues, we will move on to creating an initial Signet HC production firmware source code by combing the original Signet firmware and Signet HC flash drive test code. Once this firmware is stable we will move on to starting our [crowdfunding campaign](https://www.crowdsupply.com/nth-dimension/signet-high-capacity) and add features gradually until it is time to release Signet HC.

