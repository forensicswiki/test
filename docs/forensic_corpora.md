---
tags:
  - No Category
---
This page describes large-scale corpora of forensically interesting
information that are available for those involved in forensic research.

# Disk Images

The Real Data Corpus.
Between 1998 and 2006, [Garfinkel](simson_garfinkel.md) acquired
1250+ hard drives on the secondary market. These hard drive images have
proven invaluable in performing a range of studies such as the
developing of new forensic techniques and the sanitization practices of
computer users.

<!-- -->


Garfinkel, S. and Shelat, A., [Remembrance of Data Passed: A Study of Disk Sanitization Practices](http://www.simson.net/clips/academic/2003.IEEE.DiskDriveForensics.pdf),
IEEE Security and Privacy, January/February 2003.

<!-- -->

The Honeynet Project: Challenges.
In 2001 the Honeynet project distributed a set of disk images and asked
participants to conduct a forensic analysis of a compromised computer.
Entries were judged and posted for all to see. The drive and writeups
are still available online.

[The Honeynet Project: Challenges](https://www.honeynet.org/challenges/)

Other challenges were released in 2010 and 2011, and two contained
partial disk images.

* [Challenge 7: Compromised Server](https://www.honeynet.org/challenges/forensic-challenge-7-analysis-of-a-compromised-server/)
* [Challenge 9: Mobile Malware](https://www.honeynet.org/challenges/forensic-challenge-9-mobile-malware/)

<!-- -->

Honeynet Project Scans of the Month
The Honeynet Project provided network scans in the majority of its Scan
of the Month challenges. Some of the challenges provided disk images
instead. The Sleuth Kit's Wiki lists Brian Carrier's responses to those
challenges.

<http://wiki.sleuthkit.org/index.php?title=Case_Studies>

<!-- -->

The [Computer Forensic Reference Data Sets](https://cfreds.nist.gov/) project from [NIST](national_institute_of_standards_and_technology.md) hosts a few sample cases that may be useful for examiners to practice with:
<https://cfreds.nist.gov/Hacking_Case.html>

<!-- -->

Digital Forensics Tool Testing Images can be downloaded from Sourceforge
<https://dftt.sourceforge.net/>

<!-- -->

Shortinfosec: computer forensics competition
<https://www.shortinfosec.net/2008/07/competition-computer-forensic.html>

In the competition, you will have to analyze a submitted disk image for
incriminating evidence.

(Note: Unfortunately, when checked in October, 2011, the disk image
seemed unavailable.)

<!-- -->

Lance Mueller has created some disk images; they can be downloaded from his blog
<http://www.forensickb.com/search?q=practical>

<!-- -->

Barry Grundy created some disk images as parts of a Linux-based forensics tutorial
<https://linuxleo.com/>

<!-- -->

The PyFlag standard test image set
<https://pyflag.sourceforge.net/Documentation/tutorials/howtos/test_image.html>

<!-- -->

The Digital Forensic Research Workshop's Rodeos and Challenges
Several of the Rodeos and Challenges from DFRWS released their data and
scenario writeups. The following had disk images as parts of their
scenario:

- 2005 Rodeo, hosted on [CFReDS](https://cfreds.nist.gov/dfrws/Rhino_Hunt.html)
- 2008 Rodeo
- 2009 Rodeo
- 2009 Challenge
- 2011 Challenge

# Memory Images

The [Volatility](https://www.volatilesystems.com/default/volatility) FAQ
provides a listing of openly-available [memory images](https://code.google.com/p/volatility/wiki/FAQ#Are_there_any_public_memory_samples_available_that_I_can_use_for).

# Network Packets and Traces

## DARPA ID Eval

*The DARPA Intrusion Detection Evaluation.* In 1998, 1999 and 2000 the
Information Systems Technology Group at MIT Lincoln Laboratory created a
test network complete with simulated servers, clients, clerical workers,
programmers, and system managers. Baseline traffic was collected. The
systems on the network were then “attacked” by simulated hackers. Some
of the attacks were well-known at the time, while others were developed
for the purpose of the evaluation.

- [1998 DARPA Intrusion Detection
  Evaluation](http://www.ll.mit.edu/IST/ideval/data/1998/1998_data_index.html)
- [1999 DARPA Intrusion Detection
  Evaluation](http://www.ll.mit.edu/IST/ideval/data/1999/1999_data_index.html)
- [2000 DARPA Intrusion Detection Scenario
  Specific](http://www.ll.mit.edu/IST/ideval/data/2000/2000_data_index.html)

## Wireshark

The open source Wireshark project (formerly known as Ethereal) has a
website with many network packet captures:

- <https://wiki.wireshark.org/SampleCaptures>

## NFS Packets

The Storage Networking Industry Association has a set of network file
system traces that can be downloaded from:

- <http://iotta.snia.org/traces>

## Other

Github user "markofu" has aggregated several other network captures into
a Git repository.

- <https://github.com/markofu/pcaps>

# Email messages

*The Enron Corpus* of email messages that were seized by the Federal
Energy Regulatory Commission during its investigation of Enron.

- <http://www.cs.cmu.edu/~enron>
- <http://www.enronemail.com/>

The NIST **TextREtrieval Conference 2007** has released a public Spam
corpus:

- <https://plg.uwaterloo.ca/~gvcormac/spam/>

Email Messages Corpus Parsed from W3C Lists (for TRECENT 2005)

- <https://tides.umiacs.umd.edu/webtrec/trecent/parsed_w3c_corpus.html>

# Text Files

## Log files

[CAIDA](https://catalog.caida.org/) collects a wide variety of data.

[DShield](https://www.dshield.org/howto.html) asks users to submit
firewall logs.

## Text for Text Retrieval

The [Text REtrieval Conference (TREC)](https://trec.nist.gov/) has made
available a series of [text collections](https://trec.nist.gov//data.html).

## American National Corpus

The [American National Corpus (ANC) project](https://anc.org/) is creating
a collection of American english from 1990 onward. The goal is to create a
corpus of at least 100 million words that is comparable to the British
National Corpus.

## British National Corpus

The [British National Corpus (100)](http://www.natcorp.ox.ac.uk/) is a
100 million word collection of written and spoken english from a variety
of sources.

## IEEE VAST Challenges

IEEE Visual Analytics Science & Technology (VAST) Challenges

# Images

[Object and Concept Recognition for Content-Based Image Retrieval](http://imagedatabase.cs.washington.edu)
UW Image Database. A set of freely redistributable images from all over
the world, used for content-based image retrieval.

# Voice

## CALLFRIEND

CALLFRIEND is a database of recorded English conversations. A total of
60 recorded conversations are available from the University of
Pennsylvania at a cost of \$600.

## TalkBank

TalkBank in an online database of spoken language. The project was
originally funded between 1999 and 2004 by two National Science
Foundation grants; ongoing support is provided by two NSF grants and one
NIH grant.

## Augmented Multi-Party Interaction Corpus

The [AMI Meeting Corpus](https://groups.inf.ed.ac.uk/ami/corpus/) has 100 hours
of meeting recordings.

## Other Corpora

- Under an NSF grant, Kam Woods and [Simson
  Garfinkel](simson_garfinkel.md) created a website for digital
  corpora [2](https://digitalcorpora.org/). The site includes a complete
  training scenario, including disk images, packet captures and
  exercises.

<!-- -->

- The [Canterbury Corpus](https://corpus.canterbury.ac.nz/) is a set of
  files used for testing lossless compression algorithms. The corpus
  consists of 11 natural files, 4 artificial files, 3 large files, and a
  file with the first million digits of pi. You can also find a copyof
  the Calgaruy Corpus at the website, which was the defacto standard for
  testing lossless compression algorithms in the 1990s.

<!-- -->

- The [UMass Trace
  Repository](https://traces.cs.umass.edu/index.php/Main/HomePage)
  provides network, storage, and other traces to the research community
  for analysis. The UMass Trace Repository is supported by grant
  \#CNS-323597 from the National Science Foundation.

<!-- -->

- [Sony has made 60TB of Everquest 2 logs available to
  researchers.](https://arstechnica.com/gaming/2009/02/aaas-60tb-of-behavioral-data-the-everquest-2-server-logs/)
  What's there? "everything."

<!-- -->

- UCI's [Network Data
  Repository](http://networkdata.ics.uci.edu/resources.php) provides
  data sets of a diverse set of networks. Some of the networks are
  related to computers, some aren't.

<!-- -->

- [UT San Antonio Digital
  Corpora](https://digitalcorpora.org//corp/nps/files/filetypes1/)

# External Links

- [ForGe – Computer Forensic Test Image Generator](https://forensicfocus.com/articles/forge-computer-forensic-test-image-generator/),
  by Hunnu Visti, October 18, 2013

## CTF images

- [BelkaCTF](https://belkasoft.com/ctf)
