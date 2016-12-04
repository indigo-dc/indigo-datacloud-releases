# FutureGateway API Server Daemon


The **[FutureGateway API Server]([FutureGateway API Server](indigo1/fgapiserver1.md))** project implements the interface of a RESTful API Server, compliant with [CSGF APIs](http://docs.csgfapis.apiary.io/#reference/v1.0/application/create-a-task) specifications. Any activity processed by this interface will be then processed and orchestrated by the **FutureGateway API Server Daemon**  component.

The **APIServerDaemon** is a polling daemon working as a java servlet operating under Tomcat8. This daemon polls on top of the REST queue table and process the requests accordingly

**Summary**:
* Updates
  * [APIServer Daemon v0.0.6](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo1/fifth_update_of_indigo-1.md#fg) 
  * [APIServer Daemon v0.0.5](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo1/second_update_of_indigo-1.md#fg) 
  * [APIServer Daemon v0.0.4](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo1/first_update_of_indigo-1.md#fgapisd) 

* [Release Notes v0.0.3](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v0.0.3

<a id="id2"></a>
### What's new

First official FutureGateway release.

Supported Platforms:
* Linux(ELx/Deb), MacOSx
* Ubuntu 14.04 Server, CentOSX, MacOSx

<a id="id3"></a>
#### List of RfCs 

* * N/A

<a id="id4"></a>
### Deployment Notes

Installation methods
* Clone from [GitHub](https://github.com/indigo-dc/APIServerDaemon) or install it through [PortalSetup scripts](https://github.com/indigo-dc/PortalSetup)
* Download [tarball](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/APIServerDaemon-v0.0.3.tar.gz) from the INDIGO-DC repositories.

<a id="id5"></a>
### Known Issues

* N/A

<a id="id6"></a>
### Documentation

* Please refer to [FutureGateway documentation](https://indigo-dc.gitbooks.io/futuregateway/content/)

<a id="id7"></a>
### List of Artifacts

Tarballs:
* CentOS 7 - [APIServerDaemon_v0.0.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/APIServerDaemon_v0.0.3.tar.gz)
* Ubuntu 14.04 - [APIServerDaemon_v0.0.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/main/source/APIServerDaemon_v0.0.3.tar.gz)

<a id="id8"></a>
### Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
