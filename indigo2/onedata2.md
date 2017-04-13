# ONEDATA v. 3.0.0-rc14


**Onedata** is a global data management system, providing easy access to distributed storage resources, supporting wide range of use cases from personal data management to data-intensive scientific computations.

For quick overview of basic concepts and functionality check out our [Getting started](https://indigo-dc.gitbooks.io/onedata-documentation/content/doc/getting_started/what_is_onedata.html) section.

## Summary:

* [Release Notes v. 3.0.0-rc14](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 3.0.0-rc14

<a id="id2"></a>

### What's new

This release provides te following versions of the OneData framework:
* Oneprovider 3.0.0.07
* Onezone 3.0.0.07
* Oneclient 3.0.0.07

Specific product release notes for the version included in INDIGO-2 release 
* specific product release notes for the version included in INDIGO-1 release (highlights on the improvements, new features and/or important fixes)
<pre>
* Onezone:
  * Spaces size in provider pop up in Onezone
  * Copy provider hostname to clipboard in Onezone
  * Get support token from drop-down menu of space
  * Reordered panels in Onezone sidebar, automatic context expand
  * Group management panel: list groups and join a group
  * Added "pending" status of provider
  * Enable graceful stop on SIGTERM 
  * Access token input is now readonly
  * Allow using external access token to authorize REST operations
 
* Oneprovider: 
  * Fixing hanging "Waiting for Onezone session" message
  * Improved performance of files list
  * Fixing missing file after upload (finalising file upload after RPC completion)
  * Provider name in top bar
  * Select files range with shift
  * Fixing infinite data-space loading when one of supporting providers does not work or there are no providers at all
  * Enable graceful stop on SIGTERM
 
* Onepanel:
  * Allow integer for provider geo long/lat
  * Add cookie authentication
  * Add mount in root and read-only options
 
* Oneclient:
  * Ported S3 and Swift helpers to OSX
  * Disabled directIO detection on macOS
  * Ported oneclient to OSX
  * Switch to low-level FUSE API and fibers.

Supported Platforms:
* **Oneclient**:
  * any platform that supports Docker Engine (>11.2)
  * Ubuntu 14.04, 15.04, 16.04
  * SL6
  * CentOS 7
  * Fedora 23
* **OneProvider & OneZone**
  * Ubuntu 16.04
  * Fedora 23

From [INDIGO-2 repositories](http://repo.indigo-datacloud.eu) **OneZone** and **OneProvider** are released as Docker containers, while **OneClient** as packages (rpm, deb) for CentOS7 and Ubuntu 16.04 and Docker container.

<a id="id3"></a>
#### List of RfCs 

* N/A 

<a id="id4"></a>
### Deployment Notes

* To quickly setup a Onedata deployment try [Administrator quickstart](https://indigo-dc.gitbooks.io/onedata-documentation-indigo-dc/content/doc/getting_started/admin_onedata_101.html) 
* or more detailed information see[ Administration guide](https://indigo-dc.gitbooks.io/onedata-documentation-indigo-dc/content/doc/admin_guide.html).

<a id="id5"></a>
### Known Issues

* N/A


<a id="id7"></a>
### List of Artifacts

The repo with packages: http://onedata-dev-packages.cloud.plgrid.pl 

Packages
* Ubuntu 14.04 - [oneclient_3.0.0.rc14-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/oneclient_3.0.0.rc14-1_amd64.deb)
* CentOS 7 - [oneclient-3.0.0.rc14-1.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/oneclient-3.0.0.rc14-1.el7.centos.x86_64.rpm)

Docker images:
* [indigodatacloud/onezone:indigo_2](https://hub.docker.com/r/indigodatacloud/onezone/)
* [indigodatacloud/oneprovider:indigo_2](https://hub.docker.com/r/indigodatacloud/oneprovider/)
* [indigodatacloud/oneclient:indigo_2](https://hub.docker.com/r/indigodatacloud/oneclient/)

<a id="id6"></a>
### Documentation

* [OneData on GitBook]( https://www.gitbook.com/book/indigo-dc/onedata-documentation-indigo-dc/details)

<a id="id8"></a>
### Support

* Onedata provides live support chat: https://www.hipchat.com/g3ST0Aaci
* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
