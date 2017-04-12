# OpenStack Client 


**OpenStackClient** (aka OSC) is a command-line client for OpenStack that brings the command set for Compute, Identity, Image, Object Store and Block Storage APIs together in a single shell with a uniform command structure.
The primary goal is to provide a unified shell command structure and a common language to describe operations in OpenStack.

## Summary:
* [Release Notes](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 0.0.1


<a id="id2"></a>
### What's new

There is not a full fledged client to be released, but only a client for the OpenStack client.

Supported Platforms:
* CentOS7, Ubuntu 16.04, OpenStack Newton


<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_2.md):
* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-newton/rdo-release-newton-4.noarch.rpm```<br>
  ```$ yum clean all```<br>
  ```$ yum install python-opie-cli```
* On Ubuntu 14.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:newton```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install python2-python-opie-cli```
  or
  ```$ apt-get install python3-opie-cli_0.0.1-1_all.deb```

<a id="id5"></a>
### Known Issues

* N/A


<a id="id7"></a>
### List of Artifacts

Packages:
* [python2-python-opie-cli-0.0.1-0.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/python2-python-opie-cli-0.0.1-0.el7.centos.noarch.rpm) 
* [python-opie-cli_0.0.1-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python-opie-cli_0.0.1-1_all.deb) 
* [python3-opie-cli_0.0.1-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python3-opie-cli_0.0.1-1_all.deb) 

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
