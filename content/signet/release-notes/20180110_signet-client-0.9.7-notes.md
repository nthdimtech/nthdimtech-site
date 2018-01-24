---
title: Signet Client Version 0.9.7
date: "2018-01-10"
---

Signet client version 0.9.7 introduces a keyboard layout management feature, improves typing support generally, and fixes several bugs

### Keyboard Layout Management 

While editing settings the Signet client can now detect the keyboard layout by
generating a sequence of key codes and modifiers (Shift, Alt, etc) and capture
the characters generated to derive the system's keyboard layout. The client
saves the detected keyboard layout as a part of the existing settings file.

The detection process has some limitations currently: It can detect keys used to
add modifiers/accent to other keys such as ` or ~ (so called "dead keys") but
currently it only detects the character for the modifier itself. This will be
will be fixed in a later release. The detection process also assumes that
 Shift or Right Alt are the only keys that modify characters. These are the most
common character modifiers but not the only possible ones. Later releases
will attempt to detect other modifier keys or possibly allow the user to
specify which are used.

### Miscellaneous features

* The client can now type UTF-16 unicode characters instead of ASCII only

* If a character in a string cannot be typed for any reason a dialog will popup
giving the option to copy the string to the clipboard instead

### Bug fixes

* All fields in CSV output are now quoted to prevent incorrect parsing if "," or
any other characters that could affect parsing are present 

* Fixed crash bug that caused data to be read out of bounds when completing the
"READ ALL UIDS" command during device unlock. The crash seemed to only impact
MacOS users but in theory could have caused faults on any system

* Fixed broken "Type" button for generic fields
