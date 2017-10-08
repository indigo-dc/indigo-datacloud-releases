# Third Update of INDIGO-2 - 05/08/2017

The Third Update of INDIGO-2 release contains:
* [CMDB](#CMDB)
* [Kubernetes](#kube)
* [Monitoring - Zabbix-probes v. 1.1](#zp)
* [Onedata v. 17.06.0-rc2](#onedata)
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
* OCCI probe: https://indigo-dc.gitbooks.io/monitoring/doc/OCCI.html
* OpenStack probe: https://indigo-dc.gitbooks.io/monitoring/doc/OPENSTACK.html
* IM probe: https://indigo-dc.gitbooks.io/monitoring/zabbix-probes/im-zabbix-probe/doc/im-zabbix-agent.html

The only upgraded probe is the OCCI probe. To upgrade just install the new probe packages over the old ones. It should work in the same way however:
* The IAM information is needed in the configuration file as explained in the Configuration section of the documentation.
* The CMDB content should have the extra information needed by the new version of the probe or the probe should be set to standalone as explained in the Configuration section of the documentation.


#### Artefacts
* CentOS7
  * [imzabbix-agent-1.0-1.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/imzabbix-agent-1.0-1.el7.centos.x86_64.rpm)
  * [OCCIZabbixProbe-1.1-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/OCCIZabbixProbe-1.1-1.noarch.rpm)
  * [openstack-zabbix-probe-1.1.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/openstack-zabbix-probe-1.1.rpm)
* Ubuntu16.04
  * [imzabbix-agent-1.0-Ubuntu-14.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/imzabbix-agent-1.0-Ubuntu-14.deb)
  * [occi-zabbix-probe-1.1.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/occi-zabbix-probe-1.1.deb)
  * [openstack-zabbix-probe-1.1.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/openstack-zabbix-probe-1.1.deb)

* Docker:
  * Zabbix-wrapper: [indigodatacloud/zabbix-wrapper:indigo_2](https://hub.docker.com/r/indigodatacloud/zabbix-wrapper/tags/)


## <a name="onedata"></a>Onedata v. 17.06.0-rc2

#### What's new
* The new version of Onedata includes major performance upgrades, stability improvements and many highly demanded new features.

#### List of RfCs
* Enabled native GlusterFS support on OSX
* Multiuser tests implemented
* add additional logging to performance tests
* Fix space support with missing storage ID
* setup luma when adding storage
* Increase default RAM quota of couchbase buckets
* Improve dbsync changes filtering and queue size control
* Remove file_location links.
* Move periodic cleanup of permission cache to fslogic_worker, refactor file_meta.
* Adjust changes stream test to delayed creation of file_location.
* implementation of reverse_luma and luma_cache_behaviour, update of luma tests
* Enabled native GlusterFS support on OSX
VFS-3458 Make sure user's connected accounts are popagated through subscriptions, - use md5 rather than base64 to encode user and group ids 
* User base64 url rather than base64 in user id encoding
* Fix a bug in groups encoding from SAML assertions, do base64 of user ids from IdPs
* Update esaml reference to point to repo in onedata's github
* Add support for GlusterFS
* Update couchbase version to 4.5.1
* Improve dbsync changes aggregation
Make sure that new permissions can be safely added to the system without breaking - gui compliance
* Remove deprecated privilege names
* Fix dbsync recovery stream
* Decode cacert from pem into der format, when opening websocket connection.
* Make sure user aliases in subscriptions are precomputed every time a space name - changes, decrease changes intervals
* Cluster_worker update (update node monitoring logging)
* Showing hashes for conflicting space, group and provider names in Onezone
* Truncating long provider names in sidebar
* Loader indicator when creating space
* New support space modal with support token, deploy provider command and expose - data command
* Extend oneclient fsync with flushing events and fsyncing files on provider side.
* Add flush of all event streams
* Add support for sig v2 to AWS S3 helper
* Moved extended attribute messages from provider to fuse namespace
* Added extended attributes support
* Add copy/remove tests.
* Check if mtime and ctime are equal after rename (in previous implemetation of - rename they were greater).
* Use only storage ID in space support request
* Change provider deregistration behaviour
* Update provider name after modify
* Copy/remove files during move when non posix storage is used
* Implement rename operation.
* Rewrite current remove implementation and delete rename operation.
* Rename auth_rhea module to auth_keycloak module
* Add support for RHEA KeyCloak OpenID Connect
* Disable storage helpers buffering
* Integrate with new datastore
* Integrate with refactored datastore
* Handle chmod, truncate and updating timestamps in storage_sync
* Refactor storage_import and space_sync_worker
* Update datastore models to use new datastore API
* Remove space-storage mapping on space support revoke
* Enable release docker to log to stdout
* Add libcouchbase package dependency
* Create new test files while verifying storage availability
* Display Provider software version
* Displaying Zone name and version in Onezone and login view
* Fix blocking message when at least one provider is offline
* Added RHEA social icon

#### Installation & Configuration
* Clean installation:
  * https://onedata.org/docs/doc/getting_started/downloading_onedata.html
  * https://onedata.org/docs/doc/getting_started/admin_onedata_101.html

#### Artefacts
* Oneclient:
  * any platform that supports Docker Engine (>11.2)
  * Ubuntu 16.04 (also 14.04, 15.04 in [Onedata repositories](http://onedata-dev-packages.cloud.plgrid.pl)) 
    * [oneclient_17.06.0.rc2-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/oneclient_17.06.0.rc2-1_amd64.deb)
    * remember to download also the [Onedata Ubuntu-Xenial-list file](http://repo.indigo-datacloud.eu/repos/2/onedata-xenial.list) and download the onedata-key:<br>
      ```# wget -q -O - http://onedata-dev-packages.cloud.plgrid.pl/onedata.gpg.key | sudo apt-key add -```<br>
  * CentOS 7 (remember to download the [onedata-Centos7-repo file](http://onedata-dev-packages.cloud.plgrid.pl/yum/onedata_centos_7x.repo)
    * [oneclient-17.06.0.rc2-1.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/oneclient-17.06.0.rc2-1.el7.centos.x86_64.rpm)
  * Fedora 23 - in [Onedata repositories](http://onedata-dev-packages.cloud.plgrid.pl)
* Onezone and Oneprovider:
  * any platform that supports Docker Engine (>11.2)
  * Fedora 23 in [Onedata repositories](http://onedata-dev-packages.cloud.plgrid.pl)
  * Ubuntu 16.04
    * [oneprovider_17.06.0.rc2-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/oneprovider_17.06.0.rc2-1_amd64.deb)
    * [onezone_17.06.0.rc2-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/onezone_17.06.0.rc2-1_amd64.deb)
* Docker Container (1.4.0-FINAL):
  * [indigodatacloud/onezone:17.06.0-rc2](https://hub.docker.com/r/indigodatacloud/onezone/tags)
  * [indigodatacloud/oneprovider:17.06.0-rc2](https://hub.docker.com/r/indigodatacloud/oneprovider/tags)
  * [indigodatacloud/oneclient:17.06.0-rc2](https://hub.docker.com/r/indigodatacloud/oneclient/tags)

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
* Docker Container (1.4.0-FINAL):
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



