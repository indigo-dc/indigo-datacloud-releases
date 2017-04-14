# ONE-FaSS v. 1.0

# FaSS

FairShare Scheduler for OpenNebula.

## What is FaSS?
The current [OpenNebula](http://www.opennebula.org/) scheduler is first-in-first-out (FIFO).
FaSS grants fair access to dynamic resources prioritizing tasks assigned according to an initial weight and to the historical resource usage.

## Summary:

* [Release Notes v. v 1-0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 1.0.0

<a id="id2"></a>
### What's new

This is FaSS version 1.0, the first version released.
It is going to contain all the pieces (Priority Manager, Database, ONE XMLRPC, ...), plus a basic plugin, which prints relevant information (id of VM,
userID, cpu, usage, shares... ), but does not recalculate the priorities. The user will have to insert the priority algorithm.
Some algorithms (like MultiFactor) and more functionalities are going to be implemented in the following months.

Supported Platforms:
* CentOS 7 and OpenNebula 5.2

<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

Installation is explained in doc/install.md and doc/install-centos.md in our GitHub (https://github.com/indigo-dc/one-fass/) and it is done with an rpm file:
```$ rpm -Uvh one-fass-service-systemd_devel-1.0.x86_64.rpm```</br>

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* Centos 7: http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/one-fass-indigo-service-test-1.0.x86_64.rpm


<a id="id6"></a>
## Documentation

* [ONE-FaSS on GitBook](https://indigo-dc.gitbooks.io/one-fass/content/)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
