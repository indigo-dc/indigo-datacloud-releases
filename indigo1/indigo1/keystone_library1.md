# OpenStack Identity Authentication Library v. 2.10.0

**OpenStack Identity Authentication Library** - **Keystoneauth** - provides a standard way to do authentication and service requests within the OpenStack ecosystem. It is designed for use in conjunction with the existing OpenStack clients and for simplifying the process of writing new clients.

The version release in INDIGO-1 adds support for INDIGO AAI developments

This package contains tools for authenticating to an OpenStack-based cloud. These tools include:
* Authentication plugins (password, token, and federation based)
* Discovery mechanisms to determine API version support
* A session that is used to maintain client settings across requests (based on the requests Python library)

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
This library implements all the Keystone authentication libraries. 
* Refactored and fixed the whole OpenID Connect support
  * patches have been sent upstream [[1](https://review.openstack.org/#/q/project:openstack/keystoneauth+owner:%22Alvaro+Lopez+Garcia+%253Caloga%2540ifca.unican.es%253E%22)]
* Currently there is support for two OpenID Connect grant types (password
and authorization code) as well as the reusal of an existing
access_token (so three different auth plugins) 

* Please see also the details included in [UPSTREAM CHANGELOG](http://docs.openstack.org/developer/keystoneauth/history.html#id1)
<a id="id3"></a>

#### List of RfCs 

* [https://bugs.launchpad.net/keystoneauth](https://bugs.launchpad.net/keystoneauth)

<a id="id4"></a>
### Deployment Notes
After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-liberty/rdo-release-liberty-5.noarch.rpm```<br>
  ```$ yum clean all```<br>
  ```$ yum install python2-keystoneauth1```<br>
* On Ubuntu 14.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:liberty```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install python3-keystoneauth1```<br>
or <br>
  ```$ apt-get install python-keystoneauth1```<br>

<a id="id5"></a>
### Known Issues

* see list of unsolved bugs at [https://bugs.launchpad.net/keystoneauth](https://bugs.launchpad.net/keystoneauth)

<a id="id7"></a>
### List of Artifacts
Packages:
* CentOS 7
  * python2-keystoneauth1-2.10.1-0.el7.centos.noarch.rpm
* Ubuntu 14.04
  * python3-keystoneauth1_2.10.0-indigo1_all.deb
  * python-keystoneauth1_2.10.0-indigo1_all.deb
  * python-keystoneauth1-doc_2.10.0-indigo1_all.deb
  * python-keystoneauth1_2.10.0-indigo1.debian.tar.xz
  * python-keystoneauth1_2.10.0-indigo1.dsc
  * python-keystoneauth1_2.10.0.orig.tar.gz
  
<a id="id6"></a>
### Documentation

* [GitHub README](https://github.com/indigo-dc/keystoneauth/blob/master/README.rst)
* [Official OpenStack Identity Authentication Library Documentation](http://docs.openstack.org/developer/keystoneauth/)

<a id="id8"></a>
### Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)












