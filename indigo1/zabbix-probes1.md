# Monitoring


The **Monitoring Framework** is a set of tools which allow performing several monitoring operations in the platform resulting from the INDIGO-Datacloud project (https://www.indigo-datacloud.eu/). The Monitoring Framework is based on Zabbix, as the collector of the monitoring information coming from different sources, due to its maturity, its community support and its flexibility for different environments.

The Monitoring Framework is divided in several main parts:
* The **Zabbix server** (with the corresponding configuration and some support scripts);
* The **Zabbix wrapper**, created for enabling a REST API for Zabbix;
* Several **probes**, with different monitoring purposes (**OCCI, Heapster**, etc.).

The version of the **OCCI** and **Heapster** probes provided for the INDIGO-1 release is **v0.95**.

**Summary**:

* Updates
  * [Zabbix probes v. 1.01](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo1/third_update_of_indigo-1.md#zp)<br>

* [Release Notes Zabbix probes v. 0.95-1](#id1)
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

Both probes are new and have been created from scratch, so all the features they provide are new. Future improvements will be made, according to the feedback received and other improvements that will be applied in the near future (i.e. integration with IAM).

The features released with the **Zabbix OCCI probe** are:
* Interaction with OpenStack Cloud providers through the OCCI API covering the VM lifecycle: create, inspect and delete VM.
* Interaction with Keystone for authorization with user and password (to be improved with IAM).
* Configurable multi-threading monitoring, so metrics gathering can be done in parallel for several Cloud providers at the same time.
* Automatic listing of providers and their services, thanks to the integration with the CMDB component.
* Automatic registration of metrics in the Zabbix Server.
* Metrics supported for each operation: availability, status code (HTTP response code) and response time.
* Metrics aggregation, providing a global value for availability, status code and response time.

The features released in this version of the **Heapster probe** are:
* Interaction with Heapster in order to obtain metrics from pods and from the containers included in a pod.
* Automatic registration of metrics in the Zabbix Server through the Zabbix Agent.
* Metrics supported for pods: RX Errors, RX Errors Rate, TX Errors, TX Errors Rate, Major Memory Page Faults, Memory Page Faults, Uptime.
* Metrics supported for containers: CPU Usage, CPU Usage Rate, Memory Usage, Memory Working Set, Major Memory Page Faults Rate, Memory Page Faults Rate, Uptime


Supported Platforms:
* Both probes rely on JVM, the Zabbix Agent and other existing REST services. Therefore, although the provided packages are for Ubuntu and CentOS, both probes can run on Windows 7 as well.
* The probes can be deployed in any Cloud system, but they require that such platform guarantees the access to the Zabbix Server and to the other REST services required (Heapster, OCCI APIs of the Cloud Providers, CMDB).


<a id="id3"></a>
#### List of RfCs 
* development activities followed through internal [OpenProject task #460](https://project.indigo-datacloud.eu/work_packages/460)

<a id="id4"></a>
### Deployment Notes

The current version can be installed using the deb and rpm packages available from the INDIGO - DataCloud repositories.

Detailed instructions on instalaltion and configuration can be found 
* for the Zabbix Probes - [here](https://indigo-dc.gitbooks.io/monitoring/content/zabbix_probes.html)
* for the Zabbix Wrapper - [here](https://indigo-dc.gitbooks.io/monitoring/content/zabbix_wrapper.html)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

The packages released are the following:
* Ubuntu:
  * [occi-zabbix-probe-0.95.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/main/binary-amd64/occi-zabbix-probe-0.95.deb)
  * [heapster-zabbix-probe-0.95.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/main/binary-amd64/heapster-zabbix-probe-0.95.deb)
* CentOS:
  * [OCCIZabbixProbe-0.95-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/base/OCCIZabbixProbe-0.95-1.noarch.rpm)
  * [HeapsterZabbixProbe-0.95-R1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/base/HeapsterZabbixProbe-0.95-1.noarch.rpm)
*Other OSs:
  * [occi-zabbix-probe-0.95-jar-with-dependencies.jar](https://github.com/indigo-dc/Monitoring/blob/master/zabbix-probes/occi-zabbix-probe/occi-zabbix-probe-0.95-jar-with-dependencies.jar)
  * [heapster-zabbix-probe-0.95-jar-with-dependencies.jar](https://github.com/indigo-dc/Monitoring/blob/master/zabbix-probes/heapster-zabbix-probe/heapster-zabbix-probe-0.95-jar-with-dependencies.jar)

Docker Containers:
* [indigodatacloud/zabbix-wrapper:indigo_1](https://hub.docker.com/r/indigodatacloud/zabbix-wrapper/)

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
