scantool.net
============

This is a git repo of "ScanTool.net", the GPLv2 OBDII automotive diagnostics software distributed by [ScanTool.net, LLC](http://www.scantool.net/). The last release of the software, 1.21, was in 2009 and development stopped then. As it seems to be the only freely available, fully functional Linux software for ScanTool.net hardware, a number of people are still running it.

I've imported the original source to this repo (scantool_net121src.zip, available from the [archive downloads page](http://www.scantool.net/downloads/archive/diagnostic-software/) and am including the documentation and changes necessary to get it running on a modern Linux (in my case, Fedora 18).

Dependencies
============
* [Allegro](http://alleg.sourceforge.net/), "a game programming library". Version 4 should be what's needed.
* [DZCOMM](http://sourceforge.net/projects/dzcomm/), a vintage-2003 "cross-platform" (DOS/Linux/SunOS) RS232 library

Installation - Fedora 18
========================
# `yum install allegro allegro-devel`
# cd into dz099i, which has an unzipped copy of [DZCOMM](http://sourceforge.net/projects/dzcomm/) 0.9.9i
## `chmod +x fixunix.sh && ./fixunix.sh`
## 

export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/src/allegro/lib/unix

References
==========

Here are a few forum threads and blog posts that reference getting this software running on Linux:
* [Linux (ScanTool.net forum)](https://www.scantool.net/forum/index.php?topic=825.0)
* [HOWTO : ScanTool.Net for Linux (ODB-II)](http://www.mp3car.com/linux/79795-howto-scantool-net-for-linux-odb-ii.html)
