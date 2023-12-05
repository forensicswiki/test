---
tags:
  - Mobile Forensics
  - Open Source Software
  - Tools
---
BitPim is a free, [open source](https://opensource.org/osd/), cross-platform
program for viewing and editing data on a [CDMA](cdma.md) cell phone.
Roger Binns was the founder, project manager,
and lead developer of the project, first releasing it on March 1st,
2003. Since then leadership has been handed over to another party and
over two million users have downloaded it. The program has been
developed in [python](python.md) and originally only supported
the LG VX4400 but it now supports a variety of phone manufactures
including:

* Audiovox
* Kyocera
* LG
* Motorola
* [Nokia](nokia.md)
* [Palm](palm.md)
* Samsung
* Sanyo
* Toshiba

In order to use the program, a data cable and it's drivers, usually
available from the supplier/manufacturer, are required. BitPim will try
and automatically detect a phone but its recommended that settings are
manually configured.

## Features

![Alt text](assets/images/150px-bitpim.png "screen-phonebooktab.png")

The program can examine the phonebook, calendar, media (e.g. sounds,
ringers, images), memos, todo lists, SMS messages, call history, play
lists, and raw filesystem from devices.

Features are dependent on the phone model. For a full list of each
phones supported features see [BitPim's supported phones
list](http://www.bitpim.org/help/phones-featuressupported.htm).

The data can be manipulated through the software and changes can be
uploaded to the phone. Calendar, Phonebook, Memo, Todo, and Playlist
data can all be imported from an external file. For backup purposes all
of the data can be exported to external files.

### Forensics

If doing a forensic investigation the application should always be in
read only mode, which claims to block all write commands to the phone.
The program will not recover deleted data nor does it always recover all
undeleted data. The file system view is a very important feature
forensically as it allows a raw view of data from the phone, possibly
uncovering data that BitPim missed or found unimportant. An advanced
feature that could also be vital to a forensic investigation is
BitFling. This feature allows another computer to
remotely access a phones data over the internet. A phone could be
confiscated in California, connected to BitPim with
BitFling configured, and be forensically analyzed
in New York. Lastly exporting the data is very important so that copies
of the data can be made, ensuring no data is lost or manipulated.

## Compatability

BitPIM runs on Windows, Linux, and MacOS.

## External Links

* [Official website](http://www.bitpim.org/)
