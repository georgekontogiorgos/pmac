pmac Releases
=============

The latest untagged master branch can be obtained at
https://github.com/dls-controls/pmac.

Tagged source code releases from 2-0 onward can be obtained at
https://github.com/dls-controls/pmac/releases (earlier versions are not
recommended)

The versions of EPICS base, asyn, and motor modules used for
each release can be obtained from configure/RELEASE.local. The file
configure/RELEASE.linux-x86_64.Common should be modified to reflect
site location of dependencies.

Release Notes
=============
R2-0 (May 23, 2018)
======================
### Changes
* fixes to issues with Coordinate System motors demand and read-back
inconsistency
* fixes to any issues with race conditions due to a lack of parameter
library locking
* now works with clipper
* supports 'direct demands'
    * for avoiding the pitfalls of the motor record (particularly with
    deferred moves)
* implements coordinated deferred moves:
    *  a set of motors can be commanded to start and complete motion at
    the same time.
* updated edm GUI
* simplified templates and builder support
* stop now always works
    * stop a trajectory scan or coordinate system motor by clicking
    stop on one of the real motors
* full suite of system tests using py.test

Note that I'm now making dls-master and master the SAME. To make
this friendly to external users I have:-

* I have fixed the etc/Makefile so that it skips the folder if builder
is not available
* I have commented the required configure files to say they need
changes for each site
* I have added a non-builder example IOC (with edm GUI)

R2-0-1 (May 23, 2018)
=====================
### Changes
* fix example IOC to build outside of Diamond

R2-1 (May 23, 2018)
===================
### Changes
* restore continuous integration (new synapps dependencies)
* Fix seg fault on startup with no brick connected
* clean up compiler warnings
* Add Power Pmac IDE project as example configuration
* Get all system tests working against PPmac
    * except trajectory scan tests - not yet supported
* Fix coordinate system control features for ppmac
* Added $(PMAC):PollAllNow PV -
    * put value 1 with callback
    * synchronizes the current brick status
* fix issues with feedrate check (now compatible with PPMAC)

