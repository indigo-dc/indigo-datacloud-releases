
# jSAGA ResourceManager API v. 1.2.0

The **Resource Management API** is an extension of the SAGA specification / JSAGA implementation. It does not replace the standard Job/Data Management API.

It allows to acquire and manage resources (compute, storage, network). One can then use these resources to run job or manage data (with existing job/data API). Features of this API include:
* Wrapping to underlying technologies (cloud, pilot jobs, grid…) to an uniform API,
* Asynchronous mode (task),
* Timeout management,
* Notification (metrics),
* Security context forwarding.

**Summary**:
* [Release Notes](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes


<a id="id2"></a>
### What's new

Highlights on the [improvements, new features and/or important fixes](http://software.in2p3.fr/jsaga/dev/changes-report.html#a1.2.0):
* Implemented the SAGA ResourceManagement API

Supported Platforms : 
* any OS supporting Java 1.7 or later


<a id="id3"></a>
#### List of RfCs 

* * N/A

<a id="id4"></a>
### Deployment Notes

Installation methods :

    ```mvn clean ; mvn install (on developer's host)```

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Tarballs:
* jsaga-installer-1.2.0-20160802.161115-8-bin.tar.gz

<a id="id6"></a>
## Documentation

* [jSAGA RM API GitBook](https://indigo-dc.gitbooks.io/jsaga-resource-management/content/)


<a id="id8"></a>
## Support

* [https://forge.in2p3.fr/projects/jsaga/boards/11](https://forge.in2p3.fr/projects/jsaga/boards/11)<br>
or
* by using the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
