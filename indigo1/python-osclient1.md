# OpenStack Client v. 3.0.0.dev278-indigo6


**OpenStackClient** (aka OSC) is a command-line client for OpenStack that brings the command set for Compute, Identity, Image, Object Store and Block Storage APIs together in a single shell with a uniform command structure.

The primary goal is to provide a unified shell command structure and a common language to describe operations in OpenStack.

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

This version adds OpenStack support for INDIGO developments (AAI, preemptible instances, etc.)

Supported Platforms:
* CentOS7, Ubuntu 14.04, OpenStack Liberty


<a id="id3"></a>
#### List of RfCs 

* [https://bugs.launchpad.net/python-openstackclient](https://bugs.launchpad.net/python-openstackclient)

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-liberty/rdo-release-liberty-5.noarch.rpm```<br>
  ```$ yum clean all```<br>
  ```$ yum install python-openstackclient```
* On Ubuntu 14.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:liberty```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install python-openstackclient```


For configuration please follow the "Configuration section in the [GitHub Documentation](https://github.com/indigo-dc/python-openstackclient/blob/3.0.0.dev278/README.rst)

<a id="id5"></a>
### Known Issues

* N/A


<a id="id7"></a>
### List of Artifacts

packages:
* python-openstackclient-3.0.0.dev278-0indigo.el7.centos.noarch.rpm
* python-openstackclient_3.0.0.dev278-indigo6_all.deb
* python-openstackclient-doc_3.0.0.dev278-indigo6_all.deb

<a id="id6"></a>
## Documentation

* [Online Documentation](http://docs.openstack.org/developer/python-openstackclient/)
* [Launchpad project](Launchpad project) 
* [Blueprints](https://blueprints.launchpad.net/python-openstackclient) - feature specifications

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)<br>
or
* [https://bugs.launchpad.net/python-openstackclient](https://bugs.launchpad.net/python-openstackclient)
