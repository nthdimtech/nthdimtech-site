---
title: Development process (10/23/19)
weight: 84
---

The Signet HC blog went on hold during the campaign because we wanted to focus
on promoting the campaign and getting production started, so we limited
ourselves to writing
[campaign updates](https://www.crowdsupply.com/nth-dimension/signet-high-capacity/updates).
Many of the campaign updates were written at similar technical level as the
blog in any case. Now that the campaign is over we will to shift to putting
more content on the blog again. Announcements of development milestones will
still be posted in campaign updates naturally.

## Current development state

Here is the progress made so far.

- Signet firmware has been mostly ported to Signet HC
- The FIDO2 firmware adapted from SoloKeys has been ported but is not working properly yet

Our next priority will be to design a new firmware upgrade system. When we have
the upgrade system working well we can choose to ship devices as soon as the
hardware is ready. 

The firmware upgrade process for Signet HC will be more complicated than Signet
because Signet HC will need to be able to recover from interrupted firmware
updates. If we don’t make upgrades interruptible users would be forced to
upgrade over UART if there is an interruption. 

The new system will also support firmware signature verification so the
microcontroller can verify the origin of new firmware. It will be possible to
turn off signature verification or change the signing key once the device is
unlocked with a master password.

Once the firmware update system is ready our next priorities will be to
integrate the storage volume features with the Signet GUI and finish debugging
our FIDO2 implementation.

## Signet HC development process

We didn’t have a well-defined development process for the original Signet and
that probably led to some avoidable errors. With more experience behind us we
have determined that the project will benefit from a test and documentation
driven development process. This will mean that:

- Documentation is written before code is written
- Tests are designed before features are implemented

### Documentation driven development

For each feature we design we will first write a document describing how a
users will interact with the feature. This document will include information
about what problem the feature solves as well as what dialogs and menus it adds
and how they should be used. This will fix a problem that occurred with the
original Signet where end user documentation lagged behind development and
users often would need to discover new features through release notes or by
accident while using the client.

Once user level documentation is written for a feature we will write a design
document that will describe how the feature works at a technical level. This
will speed up coding and make it easier to define tests for the feature. It
will also will make it easier for anyone doing a security audit to scrutinize
both the design and implementation of each feature.

### Test driven development

While we are writing the technical documentation for a feature we
will also design its tests. We believe that designing tests at this time will
probably result in better code coverage than if tests were developed after code
was written.  Testing will mostly be functional but we will develop unit tests
for more complicated modules. If bugs are found in a particular area that
aren’t caught by the release process then more tests will be added for that
area.
