---
tags:
  - File Systems
---
The **New Technology File System** (**NTFS**) is a file system developed and
introduced by [Microsoft](microsoft.md) in 1995 with [Windows](windows.md) NT.
As a replacement for the [FAT](fat.md) file system, it quickly became the
standard for Windows 2000, Windows XP and Windows Server 2003.

The features of NTFS include:

* Hard-links
* Improved performance, reliability and disk space utilization
* Security access control lists
* File system journaling

## Time Stamps

NTFS keeps track of lots of time stamps. Each file has a time stamp for
'Create', 'Modify', 'Access', and 'Entry Modified'. The latter refers to
the time when the MFT entry itself was modified. These four values are
commonly abbreviated as the 'MACE' values. Note that other attributes in
each MFT record may also contain timestamps that are of forensic value.

Additional information on how NTFS timestamps work when files are moved
or copied is available here: [Microsoft KB 299648](https://mskb.pkisolutions.com/kb/299648)

### Changes in Windows Vista

In Windows Vista (presumably as of Windows XP SP3), NTFS no longer
tracks the Last Access time of a file by default. This feature can be
enabled by setting the NtfsDisableLastAccessUpdate value to '0' in the
Registry key:

    HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem

Note that this feature has been around since as early as Windows 2000
[1](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-2000-server/cc959914(v=technet.10)).

## Alternate Data Streams

The **NTFS** file system includes a feature referred to as Alternate
Data Streams (ADSs). This feature has also been referred to as "multiple
data streams", "alternative data streams", etc. ADSs were included in
**NTFS** in order to support the resource forks employed by the
Hierarchal File System (HFS) employed by Macintosh systems.

As of Windows XP SP2, files downloaded via Internet Explorer, Outlook, and
Windows Messenger were automatically given specific "zoneid" ADSs. The
[Windows](windows.md) Explorer shell would then display a warning when the user
attempted to execute these files (by double-clicking them).

Sysadmins should be aware that prior to Vista, there are no tools native
to the [Windows](windows.md) platform that would allow you to
view the existence of arbitrary ADSs. While ADSs can be created and
their contents executed or viewed, it wasn't until the "/r" switch was
introduced with the "dir" command on Vista that arbitrary ADSs would be
visible. Prior to this, tools such as LADS could be used to view the
existence of these files.

Microsoft FSRM (File System Resource Manager) also uses ADS as part of
'file classification'.

Examiners should be aware that most forensic analysis applications,
including [FTK
Imager](https://www.exterro.com/ftk-imager),[encase](encase.md)
and ProDiscover, will display ADSs found in acquired images in red.

<figure>
<img src="../assets/images/Alternate_data_stream_explore_with_FTKImager.jpg"
title="Alternate_data_stream_explore_with_FTKImager.jpg" width="1000"
alt="Alternate_data_stream_explore_with_FTKImager.jpg" />
<figcaption
aria-hidden="true">Alternate_data_stream_explore_with_FTKImager.jpg</figcaption>
</figure>

## Advanced Format (4KB Sector) Hard Drives

NTFS does not natively handle drives that use the new standard of 4KB
sectors. For information on this, see [Advanced
Format](advanced_format.md).

## USN Change journal

The update sequence number (USN) change journal, provides a persistent
log of all changes made to files on the volume. As files, directories,
and other NTFS objects are added, deleted, and modified, NTFS enters
records into the USN change journal, one for each volume on the
computer. Each record indicates the type of change and the object
changed. New records are appended to the end of the stream.

    fsutil usn ...

## Transactional NTFS (TxF)

According to MSDN Transactional NTFS (TxF) allows file operations on an
NTFS file system volume to be performed in a transaction.

Several TxF related file-system-metadata files can be found in the
file-system-metadata directory: \\\$Extend\\\$RmMetadata\\. TxF also
uses the MFT attribute \$LOGGING_UTILITY_STREAM with the name
\$TXF_DATA.

TxF uses the [Common Log File System (clfs)](common_log_file_system_(clfs).md)

## FILETIME date and time values

    import datetime

    def FromFiletime(filetime):
      """Converts a FILETIME timestamp into a Python datetime object.

        The FILETIME is mainly used in Windows file formats and NTFS.

        The FILETIME is a 64-bit value containing:
          100th nano seconds since 1601-01-01 00:00:00

        Technically FILETIME consists of 2 x 32-bit parts and is presumed
        to be unsigned.

        Args:
          filetime: The 64-bit FILETIME timestamp.

      Returns:
        A datetime object containing the date and time or None.
      """
      if filetime < 0:
        return None
      timestamp = filetime / 10

      return datetime.datetime(1601, 1, 1) + datetime.timedelta(microseconds=timestamp)

## Also see

* [\$MFT]($mft.md)

## External links

* [Technet: How NTFS Works](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc781134(v=ws.10)),
  by [Microsoft](microsoft.md)
* [Master File Table](https://learn.microsoft.com/en-us/windows/win32/devnotes/master-file-table)
* [MS-FSCC - Known Alternate Stream Names](https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-fscc/4f3837c4-2f96-40d7-b0bf-80dd1d0b0da0),
  by [Microsoft](microsoft.md)
* [Wikipedia: NTFS](https://en.wikipedia.org/wiki/NTFS)
* [Wikipedia: NTFS Reparse point](https://en.wikipedia.org/wiki/NTFS_reparse_point)
* [MSDN: Transactional NTFS](https://learn.microsoft.com/en-us/windows/win32/fileio/transactional-ntfs-portal)
* [Wikipedia: Transactional NTFS](https://en.wikipedia.org/wiki/Transactional_NTFS)
* [Linux-ntfs Documentation](https://sourceforge.net/directory/file-systems/)
  Detailed documentation of the NTFS format by the Linux-NTFS driver creators.
* [Default cluster size for NTFS, FAT, and exFAT](https://support.microsoft.com/en-us/topic/default-cluster-size-for-ntfs-fat-and-exfat-9772e6f1-e31a-00d7-e18f-73169155af95)
* [Distributed Link Tracking and Object Identifiers](https://learn.microsoft.com/en-us/windows/win32/fileio/distributed-link-tracking-and-object-identifiers)
* [New Technologies File System (NTFS)](https://github.com/libyal/libfsntfs/blob/main/documentation/New%20Technologies%20File%20System%20(NTFS).asciidoc),
  by the [libfsntfs project](libfsntfs.md), August 2009
* [The Four Stages of NTFS File Growth](https://learn.microsoft.com/en-us/archive/blogs/),
  by Jeff Hughes, October 16, 2009
* [Incident Response with NTFS INDX Buffers – Part 1: Extracting an INDX Attribute](https://www.mandiant.com/resources/blog),
  by William Ballenthin, September 18, 2012
* [Incident Response with NTFS INDX Buffers – Part 2: The Internal Structures of a File Name Attribute](https://www.mandiant.com/resources/blog),
  by Jeff Hamm, September 26, 2012
* [Analysis of hidden data in the NTFS file system](https://www.forensicfocus.com/articles/analysis-of-hidden-data-in-the-ntfs-file-system/),
  by Cheong Kai Wee, January 2006
* [The Four Stages of NTFS File Growth, Part 2](https://learn.microsoft.com/en-us/archive/blogs/),
  by John Marlin, March 12, 2015
* [Parsing the \$MFT NTFS metadata file](https://osdfir.blogspot.com/2020/04/parsing-mft-ntfs-metadata-file.html),
  by Joachim Metz, April 30, 2020
* [Windows Container Forensics](https://osdfir.blogspot.com/2021/07/windows-container-forensics.html),
  by Jonathan Greig, July 13, 2021

### Alternate Data Stream (ADS)

* [MS-FSCC: Known Alternate Stream Names](https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-fscc/4f3837c4-2f96-40d7-b0bf-80dd1d0b0da0),
  by [Microsoft](microsoft.md)

### USN change journal (UsnJrnl)

* [Wikipedia: USN Journal](https://en.wikipedia.org/wiki/USN_Journal)
