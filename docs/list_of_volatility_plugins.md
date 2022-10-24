---
tags:
  -  Research
  -  Websites
  -  Articles that need to be expanded
---
The [Volatility Framework](volatility_framework.md) was designed
to be expanded by plugins. Here is a list of the published plugins for
the **Volatility 1.3 framework**. Note that these plugins are not hosted
on the wiki, but all on external sites. **The latest release of the
[Volatility Framework](volatility_framework.md) is 2.2**. These
plugins are **not compatible with the latest version** of the framework
and information about compatible plugins can be found on the
[wiki](http://code.google.com/p/volatility/wiki/VolatilityIntroduction?tm=6)
on the [project Googlecode site](http://code.google.com/p/volatility).

## Command Shell

- [volshell](http://moyix.blogspot.com/2008/08/indroducing-volshell.html)
  (By
  [Moyix](http://moyix.blogspot.com/2008/08/indroducing-volshell.html))-
  Creates a python shell can be used with the framework.

## Malware Detection

- [IDT](http://mhl-malware-scripts.googlecode.com/files/idt.py) (By
  [Michael Hale
  Ligh](http://mnin.blogspot.com/2009/07/new-and-updated-volatility-plug-ins.html)) -
  Prints the Interrupt Descriptor Table (IDT) addresses for one
  processor
- [DriverIRP](http://mhl-malware-scripts.googlecode.com/files/driverirp.py)
  (By [Michael Hale
  Ligh](http://mnin.blogspot.com/2009/07/new-and-updated-volatility-plug-ins.html)) -
  Prints driver IRP function addresses
- [kernel_hooks](http://mhl-malware-scripts.googlecode.com/files/kernel_hooks.py)
  (By [Michael Hale
  Ligh](http://mnin.blogspot.com/2009/07/new-and-updated-volatility-plug-ins.html)) -
  Detects IAT, EAT, and in-line hooks in kernel drivers instead of
  usermode modules
- [malfind2](http://mhl-malware-scripts.googlecode.com/files/malfind2.py) -
  (By [Michael Hale
  Ligh](http://mnin.blogspot.com/2009/07/new-and-updated-volatility-plug-ins.html)) -
  Automates the process of finding and extracting (usually malicious)
  code injected into another process
- [orphan_threads](http://mhl-malware-scripts.googlecode.com/files/orphan_threads.py)
  (By [Michael Hale
  Ligh](http://mnin.blogspot.com/2009/07/new-and-updated-volatility-plug-ins.html)) -
  Detects hidden system/kernel threads
- [usermode_hooks2](http://mhl-malware-scripts.googlecode.com/files/usermode_hooks2.py)
  (By [Michael Hale
  Ligh](http://mnin.blogspot.com/2009/07/new-and-updated-volatility-plug-ins.html)) -
  Detect IAT/EAT/Inline rootkit hooks in usermode processes
- [kernel_hooks](http://mhl-malware-scripts.googlecode.com/files/kernel_hooks.py)
  (By [Michael Hale
  Ligh](http://mnin.blogspot.com/2009/07/new-and-updated-volatility-plug-ins.html)) -
  Detect IAT/EAT/Inline hooks in kernel drivers
- [Volatility Analyst Pack
  0.1](http://mhl-malware-scripts.googlecode.com/files/vap-0.1.zip) (By
  [Michael Hale
  Ligh](http://mnin.blogspot.com/2009/12/new-and-updated-volatility-plug-ins.html)) -
  A pack which contains updates to many of the listed modules

## Data Recovery

- [cryptoscan](http://jessekornblum.com/tools/volatility/cryptoscan.py)
  (By [Jesse Kornblum](jesse_kornblum.md) - Finds
  [TrueCrypt](truecrypt.md) passphrases
- [moddump](http://moyix.blogspot.com/2008/10/plugin-post-moddump.html)
  (By
  [Moyix](http://moyix.blogspot.com/2008/10/plugin-post-moddump.html)) -
  Dump out a kernel module (aka driver)
- [Registry
  tools](http://www.cc.gatech.edu/%7Ebrendan/volatility/dl/volreg-0.6.tar.gz)
  (By
  [Moyix](http://moyix.blogspot.com/2009/01/memory-registry-tools.html)) -
  A suite of plugins for accessing data from the registry, including
  password hashes, LSA secrets, and arbitrary registry keys.
- [Modified Regripper & Glue
  Code](http://www.cc.gatech.edu/%7Ebrendan/volatility/dl/volrip-0.1.tar.gz)
  (By
  [Moyix](http://moyix.blogspot.com/2009/03/regripper-and-volatility-prototype.html)) -
  Code to run a modified RegRipper against the registry hives embedded
  in a memory dump. Note that due to a dependency on Inline::Python,
  this only works on Linux.
- [getsids](http://moyix.blogspot.com/2008/08/linking-processes-to-users.html)
  (By
  [Moyix](http://moyix.blogspot.com/2008/08/linking-processes-to-users.html)) -
  Get information about what user (SID) started a process.
- [ssdt](http://moyix.blogspot.com/2008/08/auditing-system-call-table.html)
  (By
  [Moyix](http://moyix.blogspot.com/2008/08/auditing-system-call-table.html)) -
  List entries in the system call table. Can be used to detect certain
  rootkits that hook system calls by replacing entries in this table.
- [threadqueues](http://kurtz.cs.wesleyan.edu/%7Ebdolangavitt/memory/threadqueues.py)
  (By
  [Moyix](http://moyix.blogspot.com/2008/09/window-messages-as-forensic-resource.html)) -
  Enumerates window messages pending for each thread on the system.
  Window messages are the mechanism used to send things like button
  presses, mouse clicks, and other events to GUI programs.
- [objtypescan](http://computer.forensikblog.de/files/volatility_plugins/volatility_objtypescan-current.zip)
  (By [Andreas
  Schuster](http://computer.forensikblog.de/en/2009/04/scanning_for_file_objects.html)) -
  Enumerates Windows kernel object types. (Note: If running the SVN
  version of Volatility, just install the plugin file from this archive)
- [keyboardbuffer](http://computer.forensikblog.de/files/volatility_plugins/keyboardbuffer.py)
  (By [Andreas
  Schuster](http://computer.forensikblog.de/en/2009/04/read_password_from_keyboard_buffer.html#more)) -
  Extracts keyboard buffer used by the BIOS, which may contain BIOS or
  disk encryption passwords.
- [mutantscan](http://computer.forensikblog.de/files/volatility_plugins/volatility_mutantscan-current.zip)
  (By [Andreas
  Schuster](http://computer.forensikblog.de/en/2009/04/searching_for_mutants.html#more)) -
  Extracts mutexes from the Windows kernel.(Note: If running the SVN
  version of Volatility, just install the plugin file from this
  archive.)
- [symlinkobjscan](http://computer.forensikblog.de/files/volatility_plugins/volatility_symlinkobjscan-current.zip)
  (By [Andreas
  Schuster](http://computer.forensikblog.de/en/2009/04/symbolic_link_objects.html#more)) -
  Extracts symbolic link objects from the Windows kernel.(Note: If
  running the SVN version of Volatility, just install the plugin file
  from this archive.)
- [driverscan](http://computer.forensikblog.de/files/volatility_plugins/volatility_driverscan-current.zip)
  (By [Andreas
  Schuster](http://computer.forensikblog.de/en/2009/04/scanning_for_drivers.html#more)) -
  Scan for kernel _DRIVER_OBJECTs. (Note: If running the SVN version of
  Volatility, just install the plugin file from this archive.)
- [fileobjscan](http://computer.forensikblog.de/files/volatility_plugins/volatility_fileobjscan-current.zip)
  (By [Andreas
  Schuster](http://computer.forensikblog.de/en/2009/04/linking_file_objects_to_processes.html#more)) -
  File object -\> process linkage, including hidden files. (Note: If
  running the SVN version of Volatility, just install the plugin file
  from this archive.)

## Process Enumeration

- [suspicious](http://jessekornblum.com/tools/volatility/suspicious.py)
  (By [Jesse Kornblum](jesse_kornblum.md) - Identify
  "suspicious" processes. This version counts any command line running
  [TrueCrypt](truecrypt.md) or any command line that starts with
  a lower case drive letter as suspicious.

## Output Formatting

- [pstree](http://scudette.blogspot.com/2008/10/pstree-volatility-plugin.html)
  (By
  [Scudette](http://scudette.blogspot.com/2008/10/pstree-volatility-plugin.html)) -
  Produces a tree-style listing of processes
- [vol2html](http://gleeda.blogspot.com/2009/03/briefly-vol2html-update.html)
  (By [Jamie Levy AKA
  Gleeda](http://gleeda.blogspot.com/2008/11/vol2html-perl-script.html)) -
  Converts volatility output to HTML. Not technically a plugin, but
  useful nonetheless.
- [SQLite](http://jls-scripts.googlecode.com/files/vol_sql-0.2.tgz) (By
  [Jamie Levy AKA
  Gleeda](http://gleeda.blogspot.com/2010/01/volatilitys-output-rendering-functions.html)) -
  Allows one to place Volatility output into a SQLite3 Database

## Other Helper Tools

Though these are not actual plugins they are helpful tools for obtaining
output from the [Volatility Framework](volatility_framework.md).

- [VolReport(win)](http://volatility.googlecode.com/files/vol-Report%28win%29.zip)
  (By
  [SAL](http://volatility.googlecode.com/files/VolReport%28win%29_%20Simple%20Aggregation%20for%20Volatility%20Output.pdf))
- [Volatility Batch File
  Maker](http://forensiczone.blogspot.com/2009/10/volatility-batch-file-maker.html)
  (By [Richard
  McQuown](http://forensiczone.blogspot.com/2009/10/walk-through-volatility-batch-file.html))
- [Volscript](https://docs.google.com/leaf?id=0Bz2rZ4S-yK8AZDYzNDU3ZjktYTBhMS00NGQ3LTg2MGItYWM2YTFjYWE3YmQ3&sort=name&layout=list&num=50)
  Windows based Volatility batch script that runs a number of Volatility
  commands to produce a report (By [Christopher
  Bentley](http://active-security.blogspot.com/2011/05/volatility-script-for-windows.html))

