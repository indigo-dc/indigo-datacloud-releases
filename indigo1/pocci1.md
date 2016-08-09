# pOCCI v. 1.0.2


Summary:
* [Release Notes](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [Documentation](#id6)
  * [List of Artifacts](#id7)
  * [Support](#id8)


<a id="id1"></a>
## Release Notes

<a id="id2"></a>
### What's new

Supported Platforms:
* OS Systems
  *  From INDIGO-DC repositories: - CentOS 7, Ubuntu 14/trusty
  *  [others](http://scientific.zcu.cz/cesnet/pOCCI/html/devel.html#packages), also native python egg (pypi.python.org)
* clouds: 
  * Amazon EC2, OpenNebula, OpenStack, rOCCI-server dummy backend for testing
  
<a id="id3"></a>
#### List of RfCs 

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](generic_installation_and_configuration_guide_1.md):
* On CentOS 7 

```$ yum clean all
$ yum install python-nova-docker
or
$ yum install python3-pOCCI```

* On Ubuntu 14.04 - after setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](generic_installation_and_configuration_guide_1.md):

```$ apt-get update
$ apt-get install python-pocci
or
$ apt-get install python3-pocci```

<a id="id5"></a>
### Known Issues

* N/A

<a id="id6"></a>
### Documentation

<a id="id7"></a>
### List of Artifacts

Packages:
* CentOS7:
  * python2-pOCCI-1.0.2-1.el7.centos.noarch.rpm
  * python-pOCCI-1.0.2-1.el7.centos.src.rpm
  * python-pOCCI-doc-1.0.2-1.el7.centos.noarch.rpm
* Ubuntu 14.04:
  * python3-pocci_1.0.2-1_all.deb
  * python-pocci_1.0.2-1_all.deb
  * python-pocci_1.0.2-1_amd64.changes
  * python-pocci_1.0.2-1.debian.tar.gz
  * python-pocci_1.0.2-1.dsc
  * python-pocci_1.0.2.orig.tar.gz
  * python-pocci-doc_1.0.2-1_all.deb

<a id="id8"></a>
### Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)