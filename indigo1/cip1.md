# CloudInfoProvider

The **Cloud Information provider** generates a representation of cloud resources, to be published inside INDIGO - DataCloud CMDB.

**Summary**:
* Updates
  * [CloudInfoProvider v. 0.9.3](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/first_update_of_indigo-1.html#cip)

* [Release Notes  v. 0.8.5](#id1)
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

Highlights of the first release:
* The generated representation is described using a Mako template having access to the cloud middleware information.
* An Ansible role is available: https://galaxy.ansible.com/indigo-dc/cloud-info-provider/
* Retrieves images information from OpenNebula and OpenStack. 
* send-to-cmdb tool provided for inserting/updating image information inside the INDIGO CMDB (Does not touch images not present in the local cloud middleware).

Supported Platforms
* CentOS7 and Ubuntu 14.04 (trusty)

<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

installation & Configuration:
* Please read the detailed information in the [Deployment and Administration Guide](https://indigo-dc.gitbooks.io/cloud-info-provider/content/doc/admin.html)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* [cloud-info-provider-indigo-0.8.5-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/base/cloud-info-provider-indigo-0.8.5-1.el7.centos.noarch.rpm)
* [python-cloud-info-provider-indigo_0.8.5_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/main/binary-amd64/python-cloud-info-provider-indigo_0.8.5_all.deb)

<a id="id6"></a>
## Documentation

* [CloudInfoProvider GitBook](https://indigo-dc.gitbooks.io/cloud-info-provider/content/) 

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
