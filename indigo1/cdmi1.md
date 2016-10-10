# CDMI Server


**INDIGO-DataCloud CDMI Server with QoS:**
* This project provides the official reference implementation of the **SNIA Cloud Data Management Interface (CDMI)**, an ISO standard, and also a Spring Boot application port of the SNIA CDMI-Server.
* The **CDMI server** has been extended to support Quality-of-Service (QoS) and Data Life-cycle (DLC) operations for multiple storage back-ends like dCache, Ceph, GPFS, Gemss+TSM, StoRM and HPSS.
* the service offers improved QoS capabilities of storage resources.
  * a better support of high-level storage requirements such as flexible allocation of disk or tape storage space and support for data life cycle. This is an enhancement also with respect to what is currently available in public clouds, such as Amazon Glacier and Google Cloud Storage.

**Summary:**

* Updates
  * [CDMI v. 1.1](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/second_update_of_indigo-1.html#cdmi)
  * [CDMI v. 0.2](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/first_update_of_indigo-1.html#cdmi)<br>

* [Release Notes v. 0.1](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)

* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 0.1

<a id="id2"></a>
### What's new

Highlights of the features provided in the INDIGO-1 release:
* Manage objects/files via CDMI that were uploaded via OneData (or any
  other transfer mechanism)
* Request storage quality of objects/files
* Simulate backend tape system storage (Data and QoS)
* Support backend object storage system (QoS)

Supported platforms:
* all with Java >= 1.8, tested on Ubuntu 14.04, Ubuntu 16.04, CentOS 7

<a id="id3"></a>
#### List of RfCs 

* [https://github.com/indigo-dc/CDMI/issues](https://github.com/indigo-dc/CDMI/issues)

<a id="id4"></a>
### Deployment Notes

Build from source with maven
* [https://indigo-dc.gitbooks.io/cdmi-qos/content/doc/building_from_sources.html](https://indigo-dc.gitbooks.io/cdmi-qos/content/doc/building_from_sources.html)

Install via packages: cdmi-server-0.1.deb, cdmi-server-0.1-1.x86_64.rpm
* [https://indigo-dc.gitbooks.io/cdmi-qos/content/doc/installing_cdmi-qos.html](https://indigo-dc.gitbooks.io/cdmi-qos/content/doc/installing_cdmi-qos.html)

Run with Docker
* [https://indigo-dc.gitbooks.io/cdmi-qos/content/doc/running_cdmi-qos_as_a_docker_container.html](https://indigo-dc.gitbooks.io/cdmi-qos/content/doc/running_cdmi-qos_as_a_docker_container.html)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages
* [cdmi-server-1.0-2.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/base/cdmi-server-1.0-2.noarch.rpm)
* [cdmi-server-0.1.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/main/binary-amd64/cdmi-server-0.1.deb)

<a id="id6"></a>
## Documentation

* [INDIGO-DataCloud CDMI Server with QoS - Overview](https://indigo-dc.gitbooks.io/cdmi-qos/content/)
* [Developers Guide](https://indigo-dc.gitbooks.io/cdmi-qos/content/doc/developer.html)
* [Deployment Guide](https://indigo-dc.gitbooks.io/cdmi-qos/content/doc/administrator.html)
* [User Guide](https://indigo-dc.gitbooks.io/cdmi-qos/content/doc/user.html)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
