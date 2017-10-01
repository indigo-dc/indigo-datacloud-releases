# CDMI S3 QoS


**INDIGO-DataCloud CDMI S3 QoS:**
* This project provides module which adheres to cdmi-spi defined interface. This interface is meant to be implemented by 
extension modules for INDIGO CDMI server.
  * The cdmi-s3-qos module aims at integrating RADOS gateway based S3 object storage with QoS management layer 
  of [INDIGO CDMI server](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo2/cdmi2.html).

## Summary
<!--
* Updates
  * [CDMI v. 1.1](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/second_update_of_indigo-1.html#cdmi)
  * [CDMI v. 0.2](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/first_update_of_indigo-1.html#cdmi)<br>
-->

* [Release Notes v. 2.0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)

* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 2.0


<a id="id2"></a>
### What's new

Highlights of the features provided in the INDIGO-2 release:
* support for data namespace browsing. The old version gives access only to QoS attributes of data-objects with well 
know URLs, so to be able to examine attributes of given data-object you had to know the exact URL upfront,
* support for CDMI export attribute, it allows to expose to the client information about configured data access protocols, thanks to that end user is able to find the data-object with WebDav for example, but to be well understand: export attribute only informs about alternative protocols, it doesn't provide them, if by any chance the data object is available through WebDAV then export attribute will tell it
* support for bunch of new QoS attributes including:
  * exposing information about data lifetime
  * exposing information about data retention policy
* removed dependency on cdmi-s3-qos-ceph-provider module, the information which was earlier provided by 
cdmi-s3-qos-ceph-provider now is partially read from configuration file (in case of static things) and partially is obtained directly from backed server through S3 protocol

Supported platforms:
* all with Java >= 1.8, tested on Ubuntu 14.04, Ubuntu 16.04, CentOS 7

<a id="id3"></a>
#### List of RfCs 

N/A

<a id="id4"></a>
### Deployment Notes

* Installation guide available at - https://indigo-dc.gitbooks.io/cdmi-s3-qos/content/

* Ansible role is available here: https://github.com/indigo-dc/ansible-role-cdmi-s3-qos
* Additionally I have prepared two separate testing environments to have the opportunity to check if the role is 
applied properly on Ubuntu and CentOS platforms.
  * The testing environment for Ubuntu 14.04 is based on docker and the procedure is 
  described here: https://github.com/indigo-dc/cdmi-s3-qos/blob/master/docker/README-UBUNTU-ANSIBLE.md
  * The testing environment for CentOS 7 is based on Vagrant box and the testing procedure is 
  described here: https://github.com/indigo-dc/cdmi-s3-qos/blob/master/vagrant/README.md

* Run with Docker
  * [https://indigo-dc.gitbooks.io/cdmi-s3-qos/content/doc/running_from_docker_image.html](https://indigo-dc.gitbooks.io/cdmi-s3-qos/content/doc/running_from_docker_image.html)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages
* [cdmi-s3-qos-2.0.0-1.el7.centos.x86_64](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/update/ccdmi-s3-qos-2.0.0-1.el7.centos.x86_64)
* [cdmi-s3-qos-2.0.0.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/cdmi-s3-qos-2.0.0.deb)

<a id="id6"></a>
## Documentation

* [INDIGO-DataCloud CDMI S3 QoS - Overview](https://indigo-dc.gitbooks.io/cdmi-s3-qos/content/)
* [Deployment & Administration Guide](https://indigo-dc.gitbooks.io/cdmi-s3-qos/content/doc/administrationmd.htmll)
* [User Guide](https://indigo-dc.gitbooks.io/cdmi-s3-qos/content/doc/userguide_md.html)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
