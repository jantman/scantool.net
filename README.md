scantool.net
============

This is a git repo of "ScanTool.net", the GPLv2 OBDII automotive diagnostics software distributed by [ScanTool.net, LLC](http://www.scantool.net/). The last release of the software, 1.21, was in 2009 and development stopped then. As it seems to be the only freely available, fully functional Linux software for ScanTool.net hardware, a number of people are still running it.

I've imported the original source to this repo (scantool_net121src.zip, available from the [archive downloads page](http://www.scantool.net/downloads/archive/diagnostic-software/) and am including the documentation and changes necessary to get it running on a modern Linux (in my case, Fedora 18).

Dependencies
============
* [Allegro](http://alleg.sourceforge.net/), "a game programming library". Version 4 should be what's needed.
* [DZCOMM](http://sourceforge.net/projects/dzcomm/), a vintage-2003 "cross-platform" (DOS/Linux/SunOS) RS232 library
** `texinfo` (`makeinfo` binary) is required for dzcomm

Installation - Fedora 18
========================
# `yum install allegro allegro-devel texinfo`
# cd into dz099i, which has an unzipped copy of [DZCOMM](http://sourceforge.net/projects/dzcomm/) 0.9.9i
## `chmod +x fixunix.sh && ./fixunix.sh` (should already be done on the directory in this repo)
## `./configure --enable-shared=yes`
## `make depend`
## `make`
## `export DZCOMM_DIR=`pwd``
# cd back into the clone of this repo
## `export LD_LIBRARY_PATH=$PWD/dz099i/lib/unix/`
## `export C_INCLUDE_PATH=$PWD/dz099i/include:$PWD/dz099i/include/dzcomm/`
## `make NOWERROR=1`
# ... and, we currently end up with:
Shutting down Allegro due to signal #11
Segmentation fault (core dumped)

Status
------
I've only gotten this to compile by hard-coding the local path to dz990i in the makefile. At this point, it finally compiles fully, but segfaults. I'll need to work on that later.

References
==========

Here are a few forum threads and blog posts that reference getting this software running on Linux:
* [Linux (ScanTool.net forum)](https://www.scantool.net/forum/index.php?topic=825.0)
* [HOWTO : ScanTool.Net for Linux (ODB-II)](http://www.mp3car.com/linux/79795-howto-scantool-net-for-linux-odb-ii.html)
