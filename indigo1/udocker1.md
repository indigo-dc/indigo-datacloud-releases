# udocker v. 1.0.0


**udocker** - A basic user tool to execute simple docker containers in user space without requiring root privileges. 
* Enables basic download and execution of docker containers by non-privileged users in Linux systems were docker is not available. 
* It can be used to access and execute the content of docker containers in Linux batch systems and interactive clusters that are managed by other entities such as grid infrastructures or externaly managed batch or interactive systems.

The Indigo **udocker** does not require any type of privileges nor the deployment of services by system administrators. It can be downloaded and executed entirely by the end user.

**udocker** is a wrapper around several tools to mimic a subset of the docker capabilities including pulling images and running then with minimal functionality.

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

This is the first release of the tool

Supported Platforms: 
* CentOS 6 and 7, Fedora 23, Ubuntu 14.04

<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

Installation can be done from [GitHub](https://github.com/indigo-dc/udocker) or [tarball](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/tgz/udocker-v1.0.0.tar.gz)
* an [Ansible playbook ](https://github.com/indigo-dc/udocker/blob/master/ansible_install.yaml)is also available 

* More details regarding the installation and configuration can be found in the [Installation & Configuration Guide](https://indigo-dc.gitbooks.io/udocker/content/doc/installation_manual.html)

<a id="id5"></a>
### Known Issues

* N/A


<a id="id7"></a>
### List of Artifacts

Tarballs:
* [udocker-v1.0.0-linux-x86_64.tgz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/tgz/udocker-v1.0.0.tar.gz)

<a id="id6"></a>
## Documentation

* [udocker in GitBook](https://www.gitbook.com/book/indigo-dc/udocker)
  * [Installation & Configuration Guide](https://indigo-dc.gitbooks.io/udocker/content/doc/installation_manual.html)
  * [User Guide](https://indigo-dc.gitbooks.io/udocker/content/doc/user_manual.html)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
* developers can be contacted also using udocker@lip.pt
