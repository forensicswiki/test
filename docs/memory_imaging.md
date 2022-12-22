---
tags:
  -  Memory Analysis
  -  Memory Imaging
---
Memory imaging is the process of making a bit-by-bit copy of memory. In
principle it is similar to [Disk Imaging](disk_imaging.md).

For physical memory it is common to have sections that are not
accessible, e.g. because of memory-mapped I/O

The resulting copy is stored in a [Forensics image
format](:category:forensics_file_formats.md). Some of these
formats have means to differentiate between an image of memory and e.g.
that of a disk.

## Introduction

The [physical memory](physical_memory.md) of computers can be
imaged and analyzed using a variety of tools. Because the procedure for
accessing physical memory varies between [operating
systems](operating_systems.md), these tools are listed by
operating system. Once memory has been imaged, it is subjected to
[memory analysis](memory_analysis.md) to ascertain the state of
the system, extract artifacts, and so on.

One of the most vexing problems for memory imaging is verifying that the
image has been created correctly. That is, verifying that it reflects
the actual contents of memory at the time of its creation. Because the
contents of memory are constantly changing on a running system, the
process can be repeated but the results will never--to a high degree of
probability--be the same. Thus, repeating the acquisition and comparing
the results is not a feasible means of validating correct image
creation. [Memory analysis](memory_analysis.md) can reveal
whether the image's contents are consistent with the known layout and
structure of a given operating system, as well as answering other
questions, but it cannot answer the question as to whether the image
accurately reflects the system from which it was taken at the time it
was taken.

## Methods

### Reading from the Physical Memory Object

In [Windows](windows.md) the Physical Memory Object,
\\\Device\PhysicalMemory, can be used the access physical memory. Since
Windows 2003 SP1 user-mode access to this device-object is no longer
permitted
\[<http://technet.microsoft.com/en-en/library/cc787565(v=ws.10>).aspx\].
A kernel-mode process is still allowed to read from this device-object.

### MmMapIoSpace

The MmMapIoSpace function (or routine) is kernel-mode function to map a
physical address range to non-paged system space
\[<http://msdn.microsoft.com/en-us/library/windows/hardware/ff554618(v=vs.85>).aspx\].

## Memory Imaging Techniques

Crash Dumps
When configured to create a full memory dump,
[Windows](windows.md) operating systems will automatically save
an image of physical memory when a bugcheck (aka blue screen or kernel
panic) occurs. [Andreas Schuster](andreas_schuster.md) has a
[blog
post](http://computer.forensikblog.de/en/2005/10/acquisition_2_crashdump.html)
describing this technique.

LiveKd Dumps
The [Sysinternals](sysinternals.md) tool
[LiveKd](http://www.microsoft.com/technet/sysinternals/SystemInformation/LiveKd.mspx)
can be used to create an image of physical memory on a live machine in
crash dump format. Once livekd is started, use the command ".dump -f
\[output file\]"

Hibernation Files
[Windows](windows.md) 98, 2000, XP, 2003, and Vista support a
feature called [hibernation](hibernation.md) that saves the
machine's state to the disk when the computer is powered off. When the
machine is turned on again, the state is restored and the user can
return to the exact point where they left off. The machine's state,
including a compressed image of [physical
memory](physical_memory.md), is written to the disk on the
system drive, usually C:, as [hiberfil.sys](hiberfil.sys.md).
This file can be parsed and decompressed to obtain the memory image.
Once [hiberfil.sys](hiberfil.sys.md) has been obtained,
[Sandman](http://sandman.msuiche.net/) can be used to convert it to a dd
image.

[Mac OS X](mac_os_x.md) very kindly creates a file called
**/var/vm/sleepimage** on any laptop that is suspended. This file is NOT
erased when the machine starts up. It is unencrypted even if the user
turns on [File Vault](file_vault.md) and enables Secure Virtual
Memory.
[1](http://pc-eye.blogspot.com/2008/08/live-memory-dump-on-mac-laptops.html).

Firewire
It is possible for [Firewire](firewire.md) or IEEE1394 devices
to directly access the memory of a computer. Using this capability has
been suggested as a method for acquiring memory images for forensic
analysis. Unfortunately, the method is not safe enough to be widely used
yet. There are some published papers and tools, listed below, but they
are not yet forensically sound. These tools do not work with all
Firewire controllers and on other can cause system crashes. The
technology holds promise for future development, in general should be
avoided for now.

At [CanSec West 05](cansec_west_05.md), [Michael
Becher](michael_becher.md), [Maximillian
Dornseif](maximillian_dornseif.md), and [Christian N.
Klein](christian_n._klein.md) discussed an
[exploit](exploit.md) which uses Direct Memory Access (DMA) to read
arbitrary memory locations of a [firewire](firewire.md)-enabled
system. The
[paper](http://md.hudora.de/presentations/firewire/2005-firewire-cansecwest.pdf)
lists more details. The exploit is run on an [iPod running
Linux](http://ipodlinux.org/Main_Page). This can be used to grab screen
contents.

This technique has been turned into a tool that you can download from:
<http://www.storm.net.nz/projects/16>

The [Goldfish](http://digitalfire.ucd.ie/?page_id=430) tool automates
this exploit for investigators needing to analyze the memory of a Mac.

Cold and Warm reboots
Typical RAM-modules retain memory during reboots as long as power is
provided. The modules typically support a self-refresh. Whether the data
is retained depend on BIOS-es that do or do not clear the RAM during
their initialisation of the motherboards. Warm reboots refer to reboot
methods in which power is never removed from the memory module. Tools
like
[msramdump](http://mcgrewsecurity.com/oldsite/projects/msramdmp.1.html)
or
[afterlife](http://www.sei.cmu.edu/digitalintelligence/tools/afterlife/)
act like minimal OS-es with a memory footprint around a few 100k that
can save memory to disk (Nowadays often only upto 4G afaik). When the
RAM is cleared by the standard BIOS, [replacing the
bios](https://ohm2013.org/wiki/Village:Garrison#Lecture:_RAM_Memory_acquisition_using_live-BIOS_modification)
can be an option. Depending on the motherboard this method works fine.
[Cold boot](http://en.wikipedia.org/wiki/Cold_boot_attack) refers to the
cooling of RAM te increase the time the RAM module will retain data
without power. Opinions on how practical cold boot is are discussed in
"[On the Practicability of Cold Boot
Attacks](http://www1.cs.fau.de/filepool/projects/coldboot/fares_coldboot.pdf)".

Virtual Machine Imaging
There are numerous popular virtual machines that are in wide use such as
xen, qemu or vmware. If the memory image is for a machine running in
this kind of virtual environment, there are usually two methods for
obtaining a memory image. The common method is to pause/suspend/stop the
system and then collect the resulting memory image file, this has the
disadvantage of taking the machine offline during the suspend time.
Alternatively most of these systems support live dumping of a memory
image. [Qemu](http://www.qemu.org) supports the pmemsave function,
[Xen](http://www.xen.org) has the xm dump-core command.

## Also see

- [Memory analysis](memory_analysis.md)
- [Memory Imaging Tools](:tools:memory_imaging.md)

## External Links

- [Wikipedia article on Memory-mapped
  I/O](http://en.wikipedia.org/wiki/Memory-mapped_I/O)
- [RedTeam: FireWire
  round-up](http://web.archive.org/web/20101210223853/http://blogs.23.nu/RedTeam/0000/00/antville-5201)
- [FireWire Memory Dump of a Windows XP Computer: A Forensic
  Approach](http://www.friendsglobal.com/papers/FireWire%20Memory%20Dump%20of%20Windows%20XP.pdf),
  by [Antonio Martin](antonio_martin.md), 2007
- [Catching the ghost: how to discover ephemeral evidence with Live RAM
  analysis](http://forensic.belkasoft.com/en/live-ram-forensics) by Oleg
  Afonin and Yuri Gubanov, May 2013
- [Anti-forensic resilient memory
  acquisition](http://www.dfrws.org/2013/proceedings/DFRWS2013-13.pdf),
  by [Johannes Stuettgen](johannes_stuettgen.md), [Michael
  Cohen](michael_cohen.md), August 2013
- [64bit Big Sized RAM Image Acquisition
  Problem](http://takahiroharuyama.github.io/blog/2014/01/07/64bit-big-size-ram-acquisition-problem/),
  by [Takahiro haruyama](takahiro_haruyama.md), January 7, 2014
- [All memory dumping tools are not the
  same](http://brimorlabs.blogspot.com/2014/01/all-memory-dumping-tools-are-not-same.html),
  by [Brian Moran](brian_moran.md), January 14, 2014
- [Robust Linux memory acquisition with minimal target
  impact](http://www.rekall-forensic.com/docs/References/Papers/DFRWS2014EU.html),
  [Johannes Stüttgen](johannes_stüttgen.md) [Michael
  Cohen](michael_cohen.md), May 2014

