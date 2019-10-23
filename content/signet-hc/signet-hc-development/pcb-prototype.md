
---
title: PCBA prototype (4/30/19)
weight: 99
---

We just recieved some PCBA's with the latest circuit design for Signet HC. These boards are larger than the final PCBs to allow more signal lines to be exposed for debugging and so that we can get the boards more quickly than if we used the tight tolerances the final production boards will need. We used [Macrofab](https://macrofab.com) to produce
these prototypes which has allowed us to iterate quickly since we can get PCB's back in 2 weeks so long as we solder the through hole compoents ourselves.

![Development PCB top and bottom](/signet/images/macrofab-dev-pcb.jpg)

Other than having narrower traces and fewer pin headers the production PCB will likely have a similar set of components as this PCB. The microcontroller will have the same part number but be in a BGA package. The biggest change will be that the microSD card slot will be replaced with an eMMC chip which will be faster and have a smaller footprint. In the next week or two we will know for sure if the microcontroller we have selected (STM32F733) can do the job needed for Signet HC. If so we will be in a position to order production PCB's since we have produced the design already. Check out the renders from KiCad below

![Development PCB top and bottom](/signet/images/signet-hc-prod-renders.png)

We will probably wait to order production boards until the level of pre-launch signups on [Crowd Supply](https://www.crowdsupply.com/nth-dimension/signet-high-capacity) reaches a high enough level to start the campaign. This gives us the longest possible time to potentially make changes and improvements.
