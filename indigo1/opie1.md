# OpenStack Preemptible Instances Extension (OPIE) v. 12.0.0


**OPIE** is the materialization of the [preemptible instances extension](https://blueprints.launchpad.net/openstack/?searchtext=preemptible-instances) serving as a reference implementation. This package provides a set of pluggable extensions for [OpenStack Compute (nova)](http://openstack.org/) making possible to execute premptible instances using a modified filter scheduler.

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

New features and fixes as from [commits/12.0.0](https://github.com/indigo-dc/opie/commits/12.0.0):
* Create a HostStatePartial and a new HostManager classes
* Introduce a preemptible instances filter scheduler
* Update tox.ini with upstream changes
* api: raise HTTP NotImplemented instead of returning empty 
* api: add unit testing


Supported Platforms:
* CentOS7 & Ubuntu 14.04
* OpenStack v. Liberty


<a id="id3"></a>
#### List of RfCs 

* [https://github.com/indigo-dc/opie/issues](https://github.com/indigo-dc/opie/issues)

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-liberty/rdo-release-liberty-5.noarch.rpm```<br>
  ```$ yum clean all```<br>
  ```$ yum install opie```<br>
* On Ubuntu 14.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:liberty```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install opie```<br>

* More details regarding installation can be found [here](https://opie.readthedocs.io/en/latest/installation.html)
* After the installation the service needs to be configured as described [here](https://opie.readthedocs.io/en/latest/configuration.html)

<a id="id5"></a>
### Known Issues
* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* opie-12.0.0-1.el7.centos.noarch.rpm
* opie-doc_12.0.0-1ubuntu0_all.deb
* opie_12.0.0-1ubuntu0_all.deb

<a id="id6"></a>
## Documentation

* [OPIE GitBook](https://indigo-dc.gitbooks.io/opie/content/)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)<br>
or
* [https://github.com/indigo-dc/opie/issues](https://github.com/indigo-dc/opie/issues)
