# FutureGateway API Server


The **FutureGateway** aids the creation of Science Gateways or enable existing community oriented interfaces to become a Science Gateway, thus accessing any distributed computing resource using a simple set of REST APIs.

The **FutureGateway API Server** project implements the interface of a RESTful API Server, compliant with [CSGF APIs](http://docs.csgfapis.apiary.io/#reference/v1.0/application/create-a-task) specifications. Any activity processed by this interface will be then processed and orchestrated by the [FutureGateway API Server Daemon](indigo1/fgapiserverdaemon1.md) component.

This service offers the same capabilities of the [API Server](https://github.com/FutureGateway/APIServer) project with the following differences:
* It exploits the [CSGF](https://www.catania-science-gateways.it/)' GridEngine system to target its supported distributed ifnrastructures
* It may support other executors services just developing the right interface classes into the [API Server Daemon][APIServerDaemon]

The Principal advantages of this solutions are:
* Backward compatibility with existing systems based on the CSGF
* Fast provisioning of ready to go solutions
* Fast prototyping when designing new features and components (including APIServer itself)
* Ideal solution for existing development environments already using CSGF.

**Summary**:
* Updates
  * [fgAPIServer v0.0.6](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo1/fifth_update_of_indigo-1.md#fg) 
  * [fgAPIServer v0.0.5](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo1/second_update_of_indigo-1.md#fg) 
  * [fgAPIServer v0.0.4](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo1/first_update_of_indigo-1.md#fgapis) 

* [Release Notes v. v0.0.3](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)

* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 0.0.3

<a id="id2"></a>
### What's new

First official implementation fo the FutureGateway APIServer front-end

Supported Platforms:
* Linux(ELx/Deb), MacOSx
* Ubuntu 14.04 Server, CentOSX, MacOSx


<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

Installation methods
* Clone from [GitHub](https://github.com/indigo-dc/fgAPIServer) or install it through [PortalSetup scripts](https://github.com/indigo-dc/PortalSetup)
* Download [tarball](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/fgAPIServer_v0.0.3.tar.gz) from the INDIGO-DC repositories.


<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Tarballs:
* CentOS 7 - [fgAPIServer_v0.0.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/fgAPIServer_v0.0.3.tar.gz)
* Ubuntu 14.04 - [fgAPIServer_v0.0.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/main/source/fgAPIServer_v0.0.3.tar.gz)

<a id="id6"></a>
## Documentation

* Please refer to [FutureGateway documentation](https://indigo-dc.gitbooks.io/futuregateway/content/)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
