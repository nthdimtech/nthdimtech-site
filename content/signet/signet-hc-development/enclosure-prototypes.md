---
title: Enclosure prototype (4/23/19)
weight: 100
---

## First development log entry

We have been developing Signet HC for several months now and the project is starting to come together. If you want to learn more about Signet HC check the Crowd Supply campaign [pre-launch](https://www.crowdsupply.com/nth-dimension/signet-high-capacity) page and subscribe to be notified of when the campaign starts. If you are interested in the development process you can follow this development log. You can send feedback to the [mailing list](https://lists.nthdimtech.com/listinfo/signet-discuss) or directly to us at [contact@nthdimtech.com](mailto:contact@nthdimtech.com).

## Enclosure design requirements

When we set out to develop Signet HC we set some physical design goals. For the case the high level requirements are:

1. That the button be closer to the front of the USB than in the previous iteration

	Placing the button closer to the port reduces the leverage a button press exerts on the contacts which reduces the chance that a press could cause USB signal interruption.

2. That it not be more than 20mm wide or 52mm long

	If it's more than 20mm wide it wont fit alongside some other devices in a USB hub. If it's more than 52mm long it will be longer than some common keys and key fobs.

3. That it is easy to assemble and disassemble the case many times without damaging it

	There are some one time only case assembly methods that might be cheaper to manufacture. We value the ability for users to repair, extend, or re-purpose the hardware however and don't want to get in the way of users wanting to own their devices.

	Some users may prefer a tamper resistant case but there are significant challenges to getting that truly right in a small form factor. For most threat models needing physical access to the device to execute an attack is a sufficient deterrent. Users who have concerns about tampering should store the device only in secured locations.

## Enclosure prototypes
	
We have implemented a number of different designs in Freecad that meet these requirements and have had two designs CNC milled for evaluation. The first was assembled with cantilever snaps but we found that the case came apart too easily under ordinary stresses. The second design connects together using "bumps" on three sides of the inner lip of the enclosure and corresponding grooves on the other side of the enclosure. The best way to think of it is as a "bottle cap" snap. You can see some photos and a video of it below:

![Enclosure halves](/signet/images/enclosure-halves.jpg)
![Enclosure side](/signet/images/enclosure-bottom-side.jpg)
![Assembled enclosure](/signet/images/enclosure-assembled.jpg)

{{< youtube 3ftZYzniNgI >}} 

This design is commonly seen in car key fobs. The case is held together from multiple sides and can't be disassembled without applying some leverage. If we move forward with this design we will add a thin slot in the case (probably in the back) to insert a flat head screwdriver to pry open the case.

## Signet HC enclosure CAD files

For the original Signet we had designed most aspects of the enclosure on paper since we had no experience with CAD and hired a consultant to help with producing the actual model files with Autocad. Since we couldn't speak for the contents of the files we didn't feel comfortable releasing them. Now that we are designing the enclosure files with a free and open source tool we will be releasing them in the same repository as the circuit schematics.  A user could use them to design a customized case and produce it with 3D printing or CNC milling. It could even be helpful to designers of a completely different project.
