# Monitoring


The **Monitoring Framework** is a set of tools which allow performing several monitoring operations in the platform resulting from the INDIGO-Datacloud project (https://www.indigo-datacloud.eu/). The Monitoring Framework is based on Zabbix, as the collector of the monitoring information coming from different sources, due to its maturity, its community support and its flexibility for different environments.

The Monitoring Framework is divided in several main parts:
* The **Zabbix server** (with the corresponding configuration and some support scripts);
* The **Zabbix wrapper**, created for enabling a REST API for Zabbix;
* Several **probes**, with different monitoring purposes (**OCCI, Heapster**, etc.).

The version of the **OCCI** and **Heapster** probes provided for the INDIGO-1 release is **v0.95**.

## Summary:

<!--
* Updates
  * [Zabbix probes v. 1.02](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/seventh_update_of_indigo-1.html#zp)
  * [Zabbix probes v. 1.01](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/third_update_of_indigo-1.html#zp)
-->

* [Zabbix probes](#id1)
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

Short summary of the improvements, new features and/or important fixes
* Added the openstack-zabbix-probe capable of checking the status of openstack cloud providers by questioning the native API
* Added the probe for Mesos/Marathon for checking information about the master/slaves/tasks deployment
* Added the probe for TOSCA, in order to check that a deployment is done correctly
* Integration of some probes with the IAM

Supported Platforms:
* Operating System and Cloud Management Frameworks - Please list all of them, starting with the mandatory ones [1]
  * openstack-zabbix-probe supported platform: Debian
  * OCCI, Heapster, Mesos/Marathon probes: deb and rpm
  
Version of the component/service
* openstack-zabbix-probe version 1.01
* OCCI probe version 2.0
* Mesos/Marathon probe version 1.01
* Heapster probe version 1.01
* TOSCA probe version 1.0

<a id="id3"></a>
#### List of RfCs 
* Complete list of development and bug fixes tasks/issues in the respective tracking system (OpenProject, GitHub)
  * Openstack zabbix probe: https://github.com/indigo-dc/Monitoring/tree/master/zabbix-probes/openstack-zabbix-probe
  * Issues are available at: https://github.com/indigo-dc/Monitoring/issues


<a id="id4"></a>
### Deployment Notes

* For clean and upgrade installations, from INDIGO-1 version, if it's the case
  * add references/links to the corresponding chapters in the documentation - that should be present under the indigo-dc GitBook organization
  * Openstack-zabbix-probe: https://github.com/indigo-dc/Monitoring/blob/master/doc/OPENSTACK.md; https://www.gitbook.com/book/indigo-dc/monitoring/details
  * The original documentation (in GitBook) includes sections about installation (see link below). 
 

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

The packages released are the following:
* Ubuntu:
  * [heapster-zabbix-probe-1.01.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/heapster-zabbix-probe-1.01.deb)
  * [mesos-zabbix-probe-1.01.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/mesos-zabbix-probe-1.01.deb)
  * [openstack-zabbix-probe-1.01.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/openstack-zabbix-probe-1.01.deb)
  * [occi-zabbix-probe-1.01.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/occi-zabbix-probe-1.01.deb)
* CentOS:
  * [openstack-zabbix-probe-1.01.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/openstack-zabbix-probe-1.01.rpm)
  * [HeapsterZabbixProbe-1.01-1.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/HeapsterZabbixProbe-1.01-1.rpm)
  * [MesosZabbixProbe-1.01-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/MesosZabbixProbe-1.01-1.noarch.rpm)
  * [OCCIZabbixProbe-1.01-1.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/OCCIZabbixProbe-1.01-1.rpm)

<!--
Docker Containers:
* [indigodatacloud/zabbix-wrapper:indigo_1](https://hub.docker.com/r/indigodatacloud/zabbix-wrapper/)
-->

<a id="id6"></a>
## Documentation

* Documentation on the INDIGO-DC Monitoring Framework is available from the [README](https://github.com/indigo-dc/Monitoring/blob/master/README.md) file in GitHub.
* INDIGO-DC Monitoring Documentation is available also from [GitBook](https://indigo-dc.gitbooks.io/monitoring/content/ )
  * specific documentation on [Zabbix Probes](https://indigo-dc.gitbooks.io/monitoring/content/zabbix_probes.html)

Documentation is divided in three main parts:
* Deployment and Administration Guide: Describes how to install and configure correctly the probes and their main dependencies (JVM and Zabbix Agent);
* User Guide: Provides information about how to use the probes and how to find the information they generate in Zabbix;
* Developer Guide: Describes some aspects of the implementation and instructions about validation, building and packaging

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)<br
or
* [https://github.com/indigo-dc/Monitoring/issues](https://github.com/indigo-dc/Monitoring/issues)
