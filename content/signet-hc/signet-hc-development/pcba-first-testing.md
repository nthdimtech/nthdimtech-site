
---
title: PCBA initial testing (5/6/19)
weight: 97 
---

It's been a week or so since we recieved the first Signet HC development prototypes. We've ran a number of tests and so far things are looking very good.

### Signal integrity

One of the first things we did was look at the quality of the critical Signals for the board. We found no significant noise on the "power good" signal which is used to determine when to start the MCU. The higher frequency signals of the oscillator and microSD clock also looked clean.

### Functional test

We tested the LED's with a blink test you can see below:

{{< youtube BdtEIDPl05Q>}} 

Blink tests are of course a go to first test but a bit more is going on in the test above. The blinking stops when the button is pressed which validates the button circuit. Also before the blinking is started the test attempts to read and write data to the SD card. If the SD card test failed the LED's would transition to an always on state instead of switching off.

### USB high-speed

One of the things we worried about most was high-speed USB functionality. It took a little time but once the startup code was configured corrected we were able to get the USB high-speed PHY to startup and get the device recognized as a high speed USB device by one of our desktop computers. This is a very limited test and we need to do bandwidth and error rate testing soon.

### Future testing and development

So far we have been only doing the minimum testing for each component. In the next few weeks we are going to try to test all of the components working together at full speed in a realistic use case to see if any problem crop up. We will save the testing applications we develop for testing of the production boards once they are produced.
