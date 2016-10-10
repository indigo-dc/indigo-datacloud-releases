# OpenStack NOVA Client v. 5.0.1.dev3

This is a client for the OpenStack Nova API. There's a Python API (the novaclient module), and a command-line script (nova). Each implements 100% of the OpenStack Nova API.

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

This version adds in OpenStack Nova support for INDIGO developments (preemptible instances, etc.)

Supported Platforms:
* CentOS7, Ubuntu14.04, OpenStack
 
<a id="id3"></a>
#### List of RfCs 

* N/A


<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-liberty/rdo-release-liberty-5.noarch.rpm```<br>
  ```$ yum clean all```<br>
  ```$ yum install python2-novaclient```<br>
* On Ubuntu 14.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:liberty```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install python-novaclient```<br>

* See the [OpenStack CLI guide](http://docs.openstack.org/cli-reference/nova.html) for information on how to use the nova command-line tool. You may also want to look at the [OpenStack API documentation](http://developer.openstack.org/api-ref-compute-v2.1.html).

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* python2-novaclient-5.0.1.dev3-0indigo.el7.centos.noarch.rpm
* python3-novaclient_5.0.1.dev3-indigo2_all.deb
* python-novaclient_5.0.1.dev3-indigo2_all.deb
* python-novaclient-doc_5.0.1.dev3-indigo2_all.deb

<a id="id6"></a>
## Documentation

* The product extends the current set of operations of python-novaclient by adding the preemptible option, needed by OPIE product. The documentation included in [OpenStack Preemptible Instances Extension (OPIE)](indigo1/opie1.md) cover this new functionality added to the API.

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
