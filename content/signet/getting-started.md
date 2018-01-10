---
title: Getting Started with Signet 
weight: 10
TableOfContents: true
---

## Before You Start

Download the client for your operating system [here](/signet/downloads/) before starting.

## Device Mangement 

Once you have your client downloaded and device plugged in you will need to initialize it and unlock your device. The video below
shows you how to do this and other basic device managment tasks, such as:

* Changing your password.
* Backing up your device's data.

{{< vimeo 231168945 >}}

## Password Management

Once you have a handle on managing your device you're ready to start adding data and
accessing it.

{{< vimeo 231168954 >}}

## Data Types

### Access Data Types

Just below the search bar is a pulldown menu where you can select which kind of data you want to view or search for.

![signet data type pull down menu](/images/signet-pulldown-menu-1_png_project-body-fixed.jpg)

There are common UI actions shared across data types such as delete and open.

Some data types may feature special actions on the toolbar below the main view, such as launch a browser with the account's listed URL or 
tell Signet to type one of the commonly used data fields (login, user name, password).

### Add New Data Fields

You can add any number of custom fields to existing data and to define the data type so
that the application can choose a proper UI control for it.

When you add a custom field in the `view/edit` dialog, 
the Signet client adds the field to that entry only, and the data will appear below a separator line.

The screen captures below give a few examples, such as:

* Storing a contact's personal website.
* Storing the routing account number for a debit card.
* Adding unstructured notes about an account.

![Signet user created data type](/images/signet-contact-user-field-1_png_project-body-fixed.jpg)

## Mouse-Free Login

Signet automatically gives keyboard focus back to the previous application when you request it to type.
This allows you avoid having to fumble with a mouse or keyboard shortcut to enter data into a field. This feature, combined with new keyboard navigation features, makes many common
tasks like logging into websites easier and quicker. The video below demonstrates how to do this.

{{< vimeo 232519353 >}}

## Data Backup

Signet offers two forms of data back-up: encrypted automatic backup, and export to unencrpted CSV.

### Automatic Backup

The client can request to make regular backups in your preferred locations at whatever frequency you want. The automatically-created backups are given a name that includes the current date to make them easy to manage.

You can also configure the client to make backups on removable media in addition to, or instead of, local filesystem backups. This way you will still have a backup if you lose your Signet and your computer through theft or accident. To keep your removable backup current, the Signet client will make a record of the last time it successfully wrote to the removable media. When that date is older than a configurable period the client will request to make a new backup to the removable media.

### Export to CSV

You can process your data in an unencrypted human readable form. This could enable you to import the data into another program, perform your own custom processing on it, or act as another kind of backup.

Signet's security model requires that only a single database entry can be decrypted by a button press. To maintain this model but still support exporting to CSV, unencrypted export operations are confirmed differently. The light blinks twice as slow and you must hold the button for two seconds before the device will decrypt all the entries to allow CSV generation.

### Video Demonstration

{{< vimeo 236532337 >}}
