# OpenStack Preemptible Instances Extension (OPIE) v. 12.0.0


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

**OPIE** is the materialization of the [preemptible instances extension](https://blueprints.launchpad.net/openstack/?searchtext=preemptible-instances) serving as a reference implementation. This package provides a set of pluggable extensions for [OpenStack Compute (nova)](http://openstack.org/) making possible to execute premptible instances using a modified filter scheduler.

<a id="id2"></a>
### What's new

Supported Platforms:
* CentOS7 & Ubuntu 14.04
* OpenStack v. Liberty


<a id="id3"></a>
#### List of RfCs 

* [https://github.com/indigo-dc/opie/issues](https://github.com/indigo-dc/opie/issues)

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](generic_installation_and_configuration_guide_1.md):
* On CentOS 7 

```$ yum clean all
$ yum install opie```

* On Ubuntu 14.04 - after setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](generic_installation_and_configuration_guide_1.md):

```$ apt-get update
$ apt-get install opie```

* More details regarding installation and configuration can be found [here](https://opie.readthedocs.io/en/latest/installation.html)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id6"></a>
### Documentation

* [OPIE GitBook](https://indigo-dc.gitbooks.io/opie/content/)

<a id="id7"></a>
### List of Artifacts

Packages:
* opie-12.0.0-1.el7.centos.noarch.rpm
* opie-doc_12.0.0-1ubuntu0_all.deb
* opie_12.0.0-1ubuntu0_all.deb

<a id="id8"></a>
### Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
or
* [https://github.com/indigo-dc/opie/issues](https://github.com/indigo-dc/opie/issues)