---
tags:
  - File Formats
---
There are multiple versions of the Firefox Disk Cache format:

* Cache version 1
* Cache version 2 - default as of firefox 32
  [1](http://www.janbambas.cz/new-firefox-http-cache-enabled/)

## Cache version 1

The Cache directory contains the multiple type of cache files:

* Cache Map File
* Cache Block File
* Cache Data File

### Cache Map file

File named _CACHE_MAP_

Contains:

* Cache Map file header
* An array of Cache Map buckets

There are 32 buckets in the Cache map file. Within each bucket, there
are 256 records inside each bucket, hence the Cache Map file contains
8192 records in total.

Each record contains the information for one instance of cache data. A
record contains four 32-bit integers:

* A Hash Number
* An Eviction Rank
* The Data Location
* The Metadata Location

### Cache Block file

File named _CACHE_00#_, where \# is a number ranging from \[1-3\].

### Cache Data File

File named:

    <hash number><type><generation number>

Where <hash number>, <type>, <generation number> are placeholders for
the corresponding values.

## Cache version 2

    cache2/index
    cache2/doomed/*
    cache2/entries/*

## See Also

* [Mozilla Firefox](mozilla_firefox.md)
* [gzip](gzip.md)

## External Links

* [Mozilla wiki: Necko/Cache](https://wiki.mozilla.org/Necko/Cache)
* [Web Browser Forensics, Part 2](http://www.symantec.com/connect/articles/web-browser-forensics-part-2),
  by Keith J. Jones, Rohyt Belani, May 10, 2005
* [Firefox Cache Format and Extraction](https://www.forensicfocus.com/articles/firefox-cache-format-and-extraction/),
  by John Ritchie, March 9, 2012
