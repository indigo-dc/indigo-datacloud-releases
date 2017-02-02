# Ophidia v. 0.10.3

**Ophidia** is a research project on big data analytics for eScience. It provides a framework for parallel I/O and data analysis, an array-based storage model and a hierarchical storage organization to partition and distribute multidimensional scientific datasets. Since the storage model does not rely on any scientific dataset file format, it can be exploited in different scientific domains and with very heterogeneous sets of data

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

Highlights of the new features, improvements, bug fixes provided with this release:
* [ophidia-primitives](https://github.com/indigo-dc/ophidia-primitives/blob/master/HISTORY.md):
  * Fixed: bug in core function of oph_dump
  * Added: several warnings when building
* [ophidia-analytics-framework](https://github.com/indigo-dc/ophidia-analytics-framework/blob/master/HISTORY.md):
  * Fixed: several warnings when building
  * Added: support for selection statement
* [ophidia-server](https://github.com/indigo-dc/ophidia-server/blob/master/HISTORY.md):
  * Fixed: some bug in massive operation handler
  * Fixed: several warnings when building
  * Added: code coverage check
  * Added: unit tests
  * Added: support for selection statement
  * Changed: code indentation style
  * Changed: library 'known operators' to improve modularity
* [ophidia-terminal](https://github.com/indigo-dc/ophidia-terminal/blob/master/HISTORY.md):
  * Fixed: several warnings when building
  * Added: OPH_IF: graphical support for OPH_IF

Supported Platforms
* CentOS7, Ubuntu14.04

<a id="id3"></a>
#### List of RfCs 

Please see the commits for each of the components:
* [https://github.com/indigo-dc/ophidia-primitives/commits/v0.10.3](https://github.com/indigo-dc/ophidia-primitives/commits/v0.10.3)
* [https://github.com/indigo-dc/ophidia-analytics-framework/commits/v0.10.3](https://github.com/indigo-dc/ophidia-analytics-framework/commits/v0.10.3)
* [https://github.com/indigo-dc/ophidia-server/commits/v0.10.3](https://github.com/indigo-dc/ophidia-server/commits/v0.10.3)
* [https://github.com/indigo-dc/ophidia-terminal](https://github.com/indigo-dc/ophidia-terminal)

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md) please follow the instructions present in the [Ophidia Admin Guide]( http://ophidia.cmcc.it/documentation/admin/index.html)


* installation and configuration can be done also using[ ansible-role-ophidia-all](https://github.com/indigo-dc/ansible-role-ophidia-all)


<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* Ubuntu 14.04
  * [ophidia-analytics-framework_0.10.3-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-analytics-framework_0.10.3-0_amd64.deb)
  * [ophidia-primitives_0.10.3-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-primitives_0.10.3-0_amd64.deb)
  * [ophidia-server_0.10.3-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-server_0.10.3-0_amd64.deb)
  * [ophidia-terminal_0.10.3-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-terminal_0.10.3-0_amd64.deb)
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
