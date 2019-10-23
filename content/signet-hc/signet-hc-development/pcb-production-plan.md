---
title: Production PCB plan (7/5/19)
weight: 86 
---

For our first prototypes we had the boards made locally by [Bay Area Circuits](https://bayareacircuits.com/) so we could pick them up and inspect them ourselves before sending them off for assembly. We received our boards last week, and we are happy with the quality and were pleased to see that the board dimensions were more precise than specified, which will help provide a tight fit in the enclosure. We made sure to avoid a mistake we made with the original Signet and ordered the PCBs in an array (also called a panel) as shown below. Assembly houses will generally not assemble individual boards this small.

![Prototype PCB panel](/signet/images/bac-pcb-panel.jpg)

We had 12 panels produced but have only sent off one for assembly by [Screaming Circuits](https://www.screamingcircuits.com). If all goes well these boards will be used for initial Signet HC firmware development.

### Production PCB design

If we don't find problems with the assembled prototype boards then we will move forward with our [crowdfunding campaign](https://www.crowdsupply.com/nth-dimension/signet-high-capacity) shortly after. We probably won’t use the rest of the prototype panels however because we discovered that we can significantly cut long-term costs with changes to the board layout: we can route signals across the “Not Connected” (NC) pins of the eMMC chip to avoid having to place vias between the ball grid array (BGA) pads. This can be done safely because the eMMC specification designates specific pins for future use and vendor-specific use, so the NC pins should be truly disconnected. After rerouting the board using this technique we were able to increase our minimum via size from 0.2mm to 0.4mm. The new layout is shown below:

![Production PCB layout](/signet/images/production-pcb-layout.jpg)

The precision drilling needed to produce vias small enough to fit between the 0.5mm pitch pads is expensive, and many fabrication houses can’t produce vias this small, so this change will greatly decrease the cost of the production boards and expand our vendor options. 

### Production PCBA pipeline

We are weighing different options for the production PCB fabrication and assembly:

- Produce the PCBs in the US and to have them assembled overseas
- Have both fabrication and assembly done overseas

For the most recent original Signet production run we had the PCB’s fabricated and assembled in the US by different companies. We liked how this gave us a chance to do our own quality checks on the boards. It also meant we could produce more boards than we needed and potentially try different assembly houses with smaller batches. However, Signet HC has much more stringent requirements than Signet. The only way to make Signet HC entirely in the US and not risk losing money would be to set the initial sale price close to $100.

Having just the PCBs produced in the US only costs a few dollars more per board at volume (>500 units) but the problem we’ve seen is that the China based companies with good reputations with US customers will only assemble boards that they produced in house as a part of a turnkey service. It may be that non-turnkey services are simply less popular, making it harder to determine which companies are reliable. Because of these risks, we will probably go with a China based turnkey service and start with 100 boards then increase to 250 or more if everything goes well. We've heard good things about [PCBWay](https://www.pcbway.com/) so that is likely to be our first choice assuming we go the turnkey route.
