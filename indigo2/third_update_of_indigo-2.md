# Third Update of INDIGO-2 - XX/08/2017

The Third Update of INDIGO-2 release contains:
* [CMDB](#CMDB)
* [Kubernetes](#kube)
* [Monitoring - Zabbix-probes v. 1.1](#zp)
* [Ophidia v. 1.1.0](#ophidia)
* [Orchestrator v. 1.4.0-FINAL](#orchestrator)
* [SLAM v. 1.2.2](#slam)


## <a name="cmdb"></a>CMDB v. 0.4 

#### What's new
* Some of the features of the new release are:
  * management of following CI: providers, computing and storage services, images
  * support for public cloud providers
  * access control on relevant level
  * support of IAM authentication
  * support of hierarchical ownership in authorization schema (support of federated organizations)
    possibility to extend CI schema

* Depends on other components features:
  * IAM
* Other componets dependent on new features:
  * SLAM
  * Monitoring
  * CloudInfoProvider

#### Installation & Configuration
* Information regarding deployment is avalable in the [Deployment Guide](https://indigo-dc.gitbooks.io/cmdb/content/deployment.html)
* Information regarding the migrating of data is available in the [DataMigration Procedure](https://indigo-dc.gitbooks.io/cmdb/content/data-migration.html)


#### Artefacts
* [indigodatacloud/cmdb:v0.4](https://hub.docker.com/r/indigodatacloud/cmdb/tags/)


## <a name="kube"></a>Kubernetes 

#### What's new
* Updated documentation on how to setup a **Kubernetes Cluster** together with a shell script and Ansible playbook for the installation, uploaded to the git: [https://github.com/indigo-dc/kubernetes](https://github.com/indigo-dc/kubernetes)
  * Feature hub between versions Kybernetes 1.2, 1.3, 1.5
  * repeatable Installation Guide (already uploaded in Git)

#### Artefacts
* [Documentation](https://indigo-dc.gitbooks.io/kubernetes/content/)

## <a name="zp"></a>Monitoring  - Zabbix-probes v. 1.1

#### What's new
* Some of the highlights of the new versions are:
  * Openstack and OCCI Probe contain the integration with IAM.
  * new IM probe
  * Zabbix-wrapper validates the hostgroups belonging to hosts

#### List of RfCs
* N/A

#### Installation & Configuration
* The Monitoring - Zabbix probes documentation has been updated and is available at https://www.gitbook.com/book/indigo-dc/monitoring/details
* New probe documentation is available at: https://indigo-dc.gitbooks.io/monitoring/content/doc/mesos.html

#### Artefacts
* CentOS7
  * [MesosZabbixProbe-1.01-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/MesosZabbixProbe-1.01-1.noarch.rpm)
* Ubuntu14.04
  * [mesos-zabbix-probe-1.01.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/mesos-zabbix-probe-1.01.deb)


## <a name="ophidia"></a>Ophidia v. 1.1.0

#### What's new
* This Ophidia minor release fixes several bugs and provides the following new main features: 
  * WPS-enabled oph_term; 
  * support for OpenID authZ/authN; 
  * support for FITS data format; 
  * operator for file system browsing; 
  * multi-user installation; 
  * and monitoring of workflow status.
  
#### List of RfCs
* Bugs in some operators and primitives
* Bug in strncpy calls in framework
* Bugs in primitives core library
* [Bug #15](https://github.com/OphidiaBigData/ophidia-analytics-framework/issues/15)
* [Bug #14](https://github.com/OphidiaBigData/ophidia-analytics-framework/issues/14)
* [Bug #8](https://github.com/OphidiaBigData/ophidia-server/issues/8)
* [Bug #7](https://github.com/OphidiaBigData/ophidia-server/issues/7)
* [Bug #2](https://github.com/OphidiaBigData/ophidia-primitives/issues/2)

  
* For more details please read the [Release Notes of Ophidia-1.1.0-0](https://indigo-dc.gitbooks.io/ophidia/content/release_notes.html)

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the Ophidia Upgrade Guide](https://indigo-dc.gitbooks.io/ophidia/content/upgrade.html)
* [Ophidia Service Reference Card](https://indigo-dc.gitbooks.io/ophidia/content/service_reference_card.html)

## Artefacts
Packages:
* Ubuntu 14.04
  * [ophidia-analytics-framework_1.1.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/senial-updates/main/binary-amd64/ophidia-analytics-framework_1.1.0-0_amd64.deb)
  * [ophidia-primitives_1.1.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/ophidia-primitives_1.1.0-0_amd64.deb)
  * [ophidia-server_1.1.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/ophidia-server_1.1.0-0_amd64.deb)
  * [ophidia-terminal_1.1.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/ophidia-terminal_1.1.0-0_amd64.deb)
* CentOS 7 
  * [ophidia-analytics-framework-1.1.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/ophidia-analytics-framework-1.1.0-0.el7.centos.x86_64.rpm)
  * [ophidia-primitives-1.1.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/ophidia-primitives-1.1.0-0.el7.centos.x86_64.rpm)
  * [ophidia-server-1.1.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/ophidia-server-1.1.0-0.el7.centos.x86_64.rpm)
  * [ophidia-terminal-1.1.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/ophidia-terminal-1.1.0-0.el7.centos.x86_64.rpm)

## <a name="orchestrator"></a>Orchestrator v. 1.4.0-FINAL

#### What's new
* Support for the deployment of hybrid clusters has been added; Users can also retrieve their own deployents through REST APIs

#### List of RfCs
* Improvements:
  * [Issue #232](https://project.indigo-datacloud.eu/work_packages/232) - Fix IM header generation for IAM federated OpenStacks
  * [Issue #231](https://project.indigo-datacloud.eu/work_packages/231) - Support for deployment of hybrid clusters
  * [Issue #230](https://project.indigo-datacloud.eu/work_packages/230) - [Docker] Validate DB connection before starting wildfly
  * [Issue #229](https://project.indigo-datacloud.eu/work_packages/232) - Add information of who created the deployments in REST response
  * [Issue #222](https://project.indigo-datacloud.eu/work_packages/232) - Allow filtering of deployment though param in REST APIs


#### Installation & Configuration
No special operations will be required for the upgrade. Thus, the upgrade operations are:
* Stop the old container:</br>
  ```sudo docker stop orchestrator```</br>
* Remove the old container:</br>
  ```sudo docker rm orchestrator```</br>
* Pull the new image version:<br>
  ```sudo docker pull indigodatacloud/orchestrator:1.4.0-FINAL```</br>
* Start the new version:</br>
  ```docker run ...*parameters*... indigodatacloud/orchestrator:1.4.0-FINAL```</br>
* More details are available in the Upgrade guide: https://indigo-dc.gitbooks.io/indigo-paas-orchestrator/content/how_to_upgrade.html 

#### Artefacts
* Docker Container:
  * [indigodatacloud/orchestrator:indigo_2](https://hub.docker.com/r/indigodatacloud/orchestrator/)


## <a name="slam"></a>SLAM v. 1.2.2

#### What's new
* Some of the highlights of this update are:
  * UX has been greatly improved
  + added possibility to specify preference of the user using drag-and-drop technique
  + the current version is compliant with CMDB v0.4
  + improvement in authorization on REST API
  + some minor fixes in business logic and QoS

#### List of RfCs
* N/A

#### Installation & Configuration
* It is enough to replace service docker, with databases from old version.

#### Artefacts
* Docker Container
  * [docker pull indigodatacloud/slam:v1.2.2](https://hub.docker.com/r/indigodatacloud/slam/)



