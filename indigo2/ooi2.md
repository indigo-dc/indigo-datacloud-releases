# OpenStack OCCI Interface 1.0.0

**OOI** is an implementation of the [Open Cloud Computing Interface (OCCI)](http://www.occi-wg.org/) for [OpenStack]( http://openstack.org). 

<br>
## Summary:

<!--
* Updates
  * [OOI v. 0.3.2](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/second_update_of_indigo-1.html#ooi)
-->

* [Release Notes v. 1.0.0](#id1)
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
Highlights of changes as present in the [commits description](https://github.com/indigo-dc/ooi/commits/1.0.0):
* OCCI 1.2 implementation 


Ssupported Platforms:
* CentOS 7, Ubuntu 14.04, 16.04
* OpenStack Nova >= Kilo < Ocata

<a id="id3"></a>
#### List of RfCs 

* https://launchpad.net/ooi/+milestone/1.0.0

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-newton/rdo-release-newton-4.noarch.rpm```<br>
  ```$ yum clean all```<br>
  ```$ yum install python-ooi```<br>
* On Ubuntu 14.04/16.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:newton```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install python-ooi```<br>

* More details are available in the [1.0.0 Installation Guide](http://ooi.readthedocs.io/en/stable/user/installation.html)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* [python-ooi_1.0.0-1ubuntu1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python-ooi_1.0.0-1ubuntu1_all.deb)
* [python-ooi-1.0.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/python-ooi-1.0.0-1.el7.centos.noarch.rpm)

<a id="id6"></a>
## Documentation

* [OOI GitBook](https://indigo-dc.gitbooks.io/ooi/content/)

<a id="id8"></a>
## Support

* [https://blueprints.launchpad.net/ooi](https://blueprints.launchpad.net/ooi)
* [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
