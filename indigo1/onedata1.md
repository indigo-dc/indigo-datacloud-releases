# ONEDATA v. 3.0.0.07


**Onedata** is a global data management system, providing easy access to distributed storage resources, supporting wide range of use cases from personal data management to data-intensive scientific computations.

For quick overview of basic concepts and functionality check out our [Getting started](https://indigo-dc.gitbooks.io/onedata-documentation/content/doc/getting_started/what_is_onedata.html) section.

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

This release provides te following versions of the OneData framework:
* Oneprovider 3.0.0.07
* Onezone 3.0.0.07
* Oneclient 3.0.0.07

Specific product release notes for the version included in INDIGO-1 release 
* **OneZone**:
  * Use wrappers for macaroon serialization
  * Update GUI
  * Add basic authorization (login and password)
  * Support for nested groups
  * Change levels for several datastore models
* **OneProvider** and **OneClient**:
  *  Update session management
  *  Improve oneclient stability
  *  New oneclient with faster proxy and SMB
  *  Improve automatic storage discovery
  *  Improved GUI
  *  Support for prefetching
  *  Support for S3
  *  Metadata synchronization between providers improved
  *  Support for nested groups
  *  Several op_worker stability improvements
  *  Extend op_worker system monitoring

Supported Platforms:
* **Oneclient**:
  * any platform that supports Docker Engine (>11.2)
  * Ubuntu 14.04, 15.10, 16.04
  * Centos 7
  * Fedora 23
* **OneProvider**:
  * Ubuntu 15.10
  * Fedora 23
* **OneZone**:
  * Ubuntu 15.10
  * Fedora 23

From [INDIGO-1 repositories](http://repo.indigo-datacloud.eu) **OneZone** and **OneProvider** are released as Docker containers, while **OneClient** as packages (rpm, deb) for CentOS7 and Ubuntu 14.04 and Docker container.

<a id="id3"></a>
#### List of RfCs 

* N/A 

<a id="id4"></a>
### Deployment Notes

* To quickly setup a Onedata deployment try [Administrator quickstart](https://indigo-dc.gitbooks.io/onedata-documentation-indigo-dc/content/doc/getting_started/admin_onedata_101.html) 
* or more detailed information see[ Administration guide](https://indigo-dc.gitbooks.io/onedata-documentation-indigo-dc/content/doc/admin_guide.html).
* 
<a id="id5"></a>
### Known Issues

* N/A


<a id="id7"></a>
### List of Artifacts

Packages
* Ubuntu 14.04 - oneclient_3.0.0.07-1_amd64.deb
* CentOS 7 - oneclient-3.0.0.07-1.el7.centos.x86_64.rpm

Docker images:
* [indigodatacloud/onezone:indigo_1](https://hub.docker.com/r/indigodatacloud/onezone/)
* [indigodatacloud/oneprovider:indigo_1](https://hub.docker.com/r/indigodatacloud/oneprovider/)
* [indigodatacloud/oneclient:indigo_1](https://hub.docker.com/r/indigodatacloud/oneclient/)

<a id="id6"></a>
### Documentation

* [OneData on GitBook]( https://www.gitbook.com/book/indigo-dc/onedata-documentation-indigo-dc/details)

<a id="id8"></a>
### Support

* Onedata provides live support chat: https://www.hipchat.com/g3ST0Aaci
* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
