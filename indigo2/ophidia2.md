# Ophidia v. 1.0.0

**Ophidia** is a research project on big data analytics for
eScience. It provides a framework for parallel I/O and data analysis, an array-based 
storage model and a hierarchical storage organization to partition and distribute 
multidimensional scientific datasets. Since the storage model does not rely on any 
scientific dataset file format, it can be exploited in different scientific domains and with very heterogeneous sets of data

## Summary:
* [Release Notes v. 1.0.0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v.1.0.0

<a id="id2"></a>
### What's new

Highlights of the new features, improvements, bug fixes provided with this release:
* This Ophidia major release provides a number of bug fixes to increase robustness, the application 
of the same code style for all components and the removal of some obsolete functionalities.

Supported Platforms
* CentOS7, Ubuntu14.04

<a id="id3"></a>
#### List of RfCs 

History of commits since last release:
https://github.com/indigo-dc/ophidia-server/compare/v0.11.0...v1.0.0
https://github.com/indigo-dc/ophidia-terminal/compare/v0.11.0...v1.0.0
https://github.com/indigo-dc/ophidia-primitives/compare/v0.11.0...v1.0.0
https://github.com/indigo-dc/ophidia-analytcis-framework/compare/v0.11.0...v1.0.0

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic
Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md)
please follow the instructions present in the [Ophidia Admin Guide]( http://ophidia.cmcc.it/documentation/admin/index.html)


* installation and configuration can be done also using[ ansible-role-ophidia-all](
https://github.com/indigo-dc/ansible-role-ophidia-all)

* https://indigo-dc.gitbooks.io/ophidia/content/upgrade.html

<a id="id5"></a>
### Known Issues

* N/A


<a id="id7"></a>
### List of Artifacts

Packages:
* Ubuntu 14.04
  * [ophidia-analytics-framework_1.0.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-analytics-framework_0.10.3-0_amd64.deb)
  * [ophidia-primitives](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-primitives_0.10.3-0_amd64.deb)
  * [ophidia-server_)(https://www.gitbook.com/book/indigo-dc/ophidia/details_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-server_0.10.3-0_amd64.deb)
  * [ophidia-terminal_https://www.gitbook.com/book/indigo-dc/ophidia/details.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-terminal_0.10.3-0_amd64.deb)
* CentOS 7 
  * [ophidia-analytics-framework-0.10.3-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-analytics-framework-0.10.3-0.el7.centos.x86_64.rpm)
  * [ophidia-primitives-0.10.3-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-primitives-0.10.3-0.el7.centos.x86_64.rpm)
  * [ophidia-server-0.10.3-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-server-0.10.3-0.el7.centos.x86_64.rpm)
  * [ophidia-terminal-0.10.3-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-terminal-0.10.3-0.el7.centos.x86_64.rpm)

<a id="id6"></a>
## Documentation

* [Ophidia GitBook](https://www.gitbook.com/book/indigo-dc/ophidia/details)

<a id="id8"></a>
## Support
* [ophidia-info@lists.cmcc.it](ophidia-info@lists.cmcc.it)<br>
or
* [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
