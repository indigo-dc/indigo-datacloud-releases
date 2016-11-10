# Third Update of INDIGO-1

The Third Update of INDIGO-1 release contains:
* [Accounting v. 1.2.1-1](#accounting)
* [LiferayIAM v. 1.2.0](#li)
* [Ophidia v. 0.10.6](#ophidia)
* [Orchent v. 0.1.0](#orchent)
* [Orchestrator v. 1.2.0-FINAL](#orchestrator)
* [Zabbix-probes v. 1.01](#zp)

<!--
* [CMDB v. 0.4.0](#cmdb)
* [FutureGateway](#fg):
  * [fgAPIServer v0.0.5](#fg)
  * [APIServerDaemon v0.0.5](#fg)
  * [PortalSetup v0.0.4](#fg)
-->  

## <a name="accounting"></a>Accounting v. 1.2.1-1

#### What's new
* This update provides some enhancemenets, like allowing deployment only of the server container and of locally built images, and few bug fixes, like the ones regarding GET/POST authZ/authN issues

#### List of RfCs
* New Features:
  * Accept APEL-Cloud v0.2 usage records via POST requests to the REST endpoint .../api/v1/cloud/record
  * Provide access to summaries via GET requests to REST endpoint .../api/v1/cloud/record/summary
  * Enhancements to the run_container.sh script, allowing for deploying only the server container and for deploying locally built images.
  * Django Rest Framework static files positioned assuming standalone use.
* Patches, Bug Fixes and Documentation updates:
  * GET/POST authZ/authN bugs fixed.
  * Added instructions to register the service with the Indigo Identity and Access Management (IAM).
  * Added "service reference card".
  * Increase in test coverage (to 87%)

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the [How to update an already deployed service to 1.2.0 (from <1.2.0)](https://github.com/indigo-dc/Accounting/blob/master/doc/admin.md#how-to-update-an-already-deployed-service-to-120-from-120)

#### Artefacts
* Docker Container:
  * [indigodatacloud/accounting:indigo_1](https://hub.docker.com/r/indigodatacloud/accounting/)
  

## <a name="li"></a>LiferayIAM v. 1.2.0

#### What's new
* The new version of LiferayIAM includes a new method to retrieve an access token using the user subject. This is requested to
allow other services interacting with the portal, like the FG APIs, to get a valid token before to interact with the orchestrator
and/or other components.

#### List of RfCs
* [Issue-12](https://github.com/indigo-dc/LiferayIAM/issues/12) - Error message for invalid token is not correctly formatted
* [Issue-13](https://github.com/indigo-dc/LiferayIAM/issues/13) - Error in remote API 
* [Issue-14](https://github.com/indigo-dc/LiferayIAM/issues/14) - Redirect link
* [Issue-16](https://github.com/indigo-dc/LiferayIAM/issues/16) - Make available the token by user subject

#### Installation \& Configuration
* In order to use the latest version, 1.2.0, it is requested:
  * Upgrade requires to reinstall the component as described in the documentation - please read [Upgrade to a new release](https://github.com/indigo-dc/LiferayIAM/blob/master/doc/admin.md#upgrade-to-a-new-release) for more information.
  * Current configuration will not be overwritten.

#### Artefacts
* CentOS 7
  * [LiferayIAM-binary-1.2.0.tgz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/tgz/LiferayIAM-binary-1.2.0.tgz)
* Ubuntu14.04
  * [LiferayIAM-binary-1.2.0.tgz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/LiferayIAM-binary-1.2.0.tgz)
  

## <a name="ophidia"></a>Ophidia v. 0.10.6

#### What's new
* This update adds new features for interleaving and interactive workflow interfaces. It also includes several improvements and bug fixes. Some operators have been extended to support the user community case studies.

#### List of RfCs
* New features and bug fixes:
  * first support for interactive workflow interfaces
  * first support for interleaved workflow interfaces
  * improved usability of the Ophidia terminal
  * improved stability of the Ophidia server
  * bug fixing and new features for several operators exploited in the WP2 case studies
    * [Issue #6](https://github.com/OphidiaBigData/ophidia-analytics-framework/issues/6) - ophidia-analytics-framework - "OPH_EXPORTNC2: the operator hangs when the number of cores is higher than the number of fragments of input cube"
    * [Issue #3](https://github.com/OphidiaBigData/ophidia-terminal/issues/3) - ophidia-terminal - "Unsupported image creation from compact output format"
    * Bug in gtk handler when window is closed while running in auto-view mode
    * Bug in handling wrong expression with OPH_IF
    * Bug in setting exit status of OPH_ENDFOR
    * Bug in OphidiaDB update when a massive operation is retried
    * Bug in handling OPH_IF when Matheval is not enabled
    * Bug in setting basic notification message for massive operations
    * Bug in building function 'oph_if_impl' when MathEval library is disabled
    * Bug in handling filter 'path' in massive operations
    * Bug in massive operation handler

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the Ophidia Upgrade Guide](https://indigo-dc.gitbooks.io/ophidia/content/upgrade.html)
* new documentation: [Ophidia Service Reference Card](https://indigo-dc.gitbooks.io/ophidia/content/service_reference_card.html)

#### Artefacts
Packages:
* Ubuntu 14.04
  * [ophidia-analytics-framework_0.10.6-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-analytics-framework_0.10.6-0_amd64.deb)
  * [ophidia-primitives_0.10.6-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-primitives_0.10.6-0_amd64.deb)
  * [ophidia-server_0.10.6-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-server_0.10.6-0_amd64.deb)
  * [ophidia-terminal_0.10.6-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-terminal_0.10.6-0_amd64.deb)
* CentOS 7 
  * [ophidia-analytics-framework-0.10.6-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-analytics-framework-0.10.6-0.el7.centos.x86_64.rpm)
  * [ophidia-primitives-0.10.6-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-primitives-0.10.6-0.el7.centos.x86_64.rpm)
  * [ophidia-server-0.10.6-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-server-0.10.6-0.el7.centos.x86_64.rpm)
  * [ophidia-terminal-0.10.6-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-terminal-0.10.6-0.el7.centos.x86_64.rpm)
  
## <a name="orchent"></a>Orchent v. 0.1.0

#### What's new
* The first command line client for the INDIGO DataCloud Orchestrator. With a lot of support at your fingertips: ```orchent help```
  * Supports the full REST interface of the orchestrator:<br>
  ```listing all deployments: ```<br>
   ```  showing a specific deployment ```<br>
   ```  showing the template of a specific deployment ```<br>
   ```  listing all resources of a deployment ```<br>
   ```  showing a specific resource of a deployment ```<br>
   ```  creating a new deployment ```<br>
   ```  updating a given deployment ```<br>
   ```  deleting a given deployment  ```<br>

#### List of RfCs
* N/A

#### Installation & Configuration
* Documentation is avalable at - [Orchent GitBook](https://www.gitbook.com/book/indigo-dc/orchent/details)

#### Artefacts
* CentOS7
  * [orchent-0.1.0-1.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/orchent-0.1.0-1.el7.centos.x86_64.rpm)
* Ubuntu14.04
  * [orchent-0.1.0-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/orchent-0.1.0-1_amd64.deb)

## <a name="orchestrator"></a>Orchestrator v. 1.2.0-FINAL

#### What's new
* The current update provides an enhanced TOSCA support.

#### List of RfCs
* Added:
  * [Issue #142](https://project.indigo-datacloud.eu/work_packages/142) - Support input substitution in listValue properties
  * [Issue #139](https://project.indigo-datacloud.eu/work_packages/139) - Support TOSCA extended node requirements definition in topology templates
* Removed:
  * [Issue #125](https://project.indigo-datacloud.eu/work_packages/125) - Removed deprecated occi proxy authentication 


#### Installation & Configuration
This release doesn't require any change of configuration or paramaters so the upgrade operations are:
* Stop the old container:<br>
  ```sudo docker stop orchestrator```<br>
* Remove the old container:<br>
  ```sudo docker rm orchestrator```<br>
* Pull the new image version:<br>
  ```sudo docker pull indigodatacloud/orchestrator:1.2.0-FINAL```<br>
* Start the new version:<br>
  ```docker run ...*same parameters*... indigodatacloud/orchestrator:1.2.0-FINAL```<br>

#### Artefacts
* Docker Container:
  * [indigodatacloud/orchestrator:indigo_1](https://hub.docker.com/r/indigodatacloud/orchestrator/)


## <a name="zp"></a>Zabbix-probes v. 1.01

#### What's new
* The current update is mainly focused on solving several bugs detected and on adding a feature to the OCCI probe for improving its adoption rate, since the former user/password authentication was not adequate enough for automating the whoel monitoring process.

#### List of RfCs
* [Issue #6](https://github.com/indigo-dc/Monitoring/issues/6) - Bug fix related to retrieving the config file info when the file is not available.
* [Issue #10](https://github.com/indigo-dc/Monitoring/issues/10) - Bug fix related to accessing to the Zabbix wrapper API, when creating new hosts
* Start to add IAM support for authentication in the OCCI probe (not completed yet)


#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the "2.5 Packages Update" section of the [Monitoring GitBook](https://indigo-dc.gitbooks.io/monitoring/content/)

#### Artefacts
* CentOS7
  * [HeapsterZabbixProbe-1.01-1.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/HeapsterZabbixProbe-1.01-1.rpm)
  * [OCCIZabbixProbe-1.01-1.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/OCCIZabbixProbe-1.01-1.rpm)
* Ubuntu14.04
  * [heapster-zabbix-probe-1.01.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/heapster-zabbix-probe-1.01.deb)
  * [occi-zabbix-probe-1.01.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/occi-zabbix-probe-1.01.deb)
  
  
* Docker Container:
  * [indigodatacloud/zabbix-wrapper:indigo_1](https://hub.docker.com/r/indigodatacloud/zabbix-wrapper/)
