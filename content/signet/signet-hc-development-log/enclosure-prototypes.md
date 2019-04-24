---
title: Signet HC enclosure development
---

## Enclosure design requirements

When we set out to develop Signet HC we set some physical design goals. For the case the high level requirements are that:

1) The button be closer to the front of the USB than the previous iteration

Placing the button closer to the port reduces the leverage the press exerts on the contacts which reduces the chance that a press could cause USB signal interruption.

2) Not be more than 20mm wide or 52mm long

If it’s more than 20mm wide it wont fit alongside some other devices in a USB hub. If it’s more than 52mm long it will be longer than some common keys and keyfobs.

3) It is easy to assemble and disassemble the case many times without damaging it

There are some one time only case assembly methods that might be cheaper to manufacture and assemble. I value the ability for users to repair, extend, or re-purpose the hardware however and don’t want to get in the way of users wanting to own their devices.

Some users may prefer a tamper resistant case but there are significant challenges to getting that truly right in a small form factor on a limited budget. For most thread models needing physical access to the device to implement an attack will be sufficient deterrent. My advice to users still worried about tampering is to only store the device in secured locations.

## Enclosure prototypes
	
I have implemented a number of different designs in Freecad that meet these requirements have had two designs CNC milled for evaluation. The first was assembled with cantilever snaps but I found that the case came apart too easily under ordinary stress. The second design connects together using a “bumps” on all three sides of the inner lip of the enclosure and corresponding groove on the other side of the enclosure. The best way to think of it is as a “bottle cap” snap. You can see some photos and a video of it below:

{{< youtube w7Ft2ymGmfc >}} 

I have seen designs similar to this in car key fobs. The case is held together from multiple sides and can’t be disassembled without applying some leverage. Assuming we move forward with this design the production version there will be a slot in the case, probably in the back, to insert a flat head screwdriver to open the case.

## Signet HC enclosure CAD files

For the original Signet I had designed most aspects of the enclosure on paper since I had no experience with CAD and hired a consultant to help with producing the actual model files with Autocad. I had considered publishing the design files but I only wanted to do so if I could actually speak for their contents. Now that I am designing the enclosure files with a free and open source tool from scratch I will be releasing them in the same repository that I release the circuit schematics.  A user could create a customized case with these files with 3D printing or CNC milling or even use it as a starting point for a different project.Signet HC enclosure progress
