# OpenStack OCCI Interface 

**OOI** is an implementation of the [Open Cloud Computing Interface (OCCI)](http://www.occi-wg.org/) for [OpenStack]( http://openstack.org). 
<br>
**Summary**:
* Updates
  * [OOI v. 0.3.2](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/second_update_of_indigo-1.html#ooi)

* [Release Notes v. 0.3.1-1](#id1)
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
Highlights of changes as present in the [commits description](https://github.com/indigo-dc/ooi/commits/0.3.1):
* fix nova <-> OCCI state mapping 
* fix state transitions for OCCI actions 
* Add support for SSH key injection
* Handle multiple content-types into one header field
* Catch exception if image is not found when showing a server
* Support linking storage on compute creation 
* do not access token info to obtain tenant
* Solved OCCI validation using osnetwork mixin
* 


Ssupported Platforms:
* CentOS 7, Ubuntu 14.04
* OpenStack (Kilo onwards)

<a id="id3"></a>
#### List of RfCs 

* h[ttps://launchpad.net/ooi](ttps://launchpad.net/ooi)
* [https://bugs.launchpad.net/ooi](https://bugs.launchpad.net/ooi)
* [https://blueprints.launchpad.net/ooi](https://blueprints.launchpad.net/ooi)

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-liberty/rdo-release-liberty-5.noarch.rpm```<br>
  ```$ yum clean all```<br>
  ```$ yum install python-ooi```<br>
* On Ubuntu 14.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:liberty```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install python-ooi```<br>

* More details are available in the [0.3.1 Installation Guide](http://ooi.readthedocs.io/en/stable/user/installation.html)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* python-ooi_0.3.1-1_all.deb
* python-ooi-0.3.1-1.el7.centos.noarch.rpm

<a id="id6"></a>
## Documentation

* [OOI GitBook](https://indigo-dc.gitbooks.io/ooi/content/)

<a id="id8"></a>
## Support

* [https://blueprints.launchpad.net/ooi](https://blueprints.launchpad.net/ooi)
* [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
