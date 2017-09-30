# Fifth Update of INDIGO-2 - 30/09/2017

The Fourth Update of INDIGO-2 release contains:
* [Accounting v. 1.5.0-1](#accounting)
* [IAM v. 1.1.0](#iam)
* [IM v. 1.6.1](#im)
* [IM Java API v. 0.4.10](#imjavaapi)
* [INDIGO-Kepler v. 1.3](#kepler)
* [Synergy: Service v. 1.5.3 & Scheduler-Manager v. 2.6.0](#synergy)
* [Liferay Plugins v. 2.2.1](#lp)
* [CLUES v. 2.2.1](#clues)
* [Orchent v. 1.1.0](#orchent)
* [OOI v. 1.2.0](#ooi)
* [Synergy: Service v. 1.5.2 & Scheduler-Manager v. 2.5.0](#synergy)
* [WaTTs v. 1.2.0](#watts)


## <a name="accounting"></a>Accounting (APEL) v. 1.5.0-1 

#### What's new
* New Features and Minor Changes
  * Add token introspection and Caching: https://github.com/apel/rest/pull/37
  * Add files to enable ansible deployment: https://github.com/apel/rest/pull/43
* Patches and Bug Fixes
  * GET Test Case Refactor: https://github.com/apel/rest/pull/35
  * POST Test Case Refactor: https://github.com/apel/rest/pull/36
  * Add branch coverage to coveralls check: https://github.com/apel/rest/pull/39
  * Upgrade base Docker image to CentOS7: https://github.com/apel/rest/pull/40
  * Update documentation in docker/README.md: https://github.com/apel/rest/pull/41
  * Update Partition range for new deployments: https://github.com/apel/rest/pull/42
  * Improve documentation following second round of 'Early Adopter' testing: https://github.com/apel/rest/pull/44

#### Installation & Configuration
* https://github.com/indigo-dc/Accounting/blob/1.5.0-1/README.md
* https://github.com/indigo-dc/Accounting/tree/1.5.0-1/doc

Upgrading an already deployed instance
* https://github.com/indigo-dc/Accounting/blob/1.5.0-1/doc/admin.md#how-to-update-an-already-deployed-service-to-150-from-140

#### Artefacts
* [indigodatacloud/accounting:indigo_2](https://hub.docker.com/r/indigodatacloud/accounting/tags) - CentOS7 based image

## <a name="im"></a>Infrastructure Manager v. 1.6.1

#### What's new
* Add Support OTC.
* Support "DependsOn" TOSCA relationship.
* Enable to specify a port range in endpoint ports.
* Fix error loading an infrastructure from DB in case of invalid TOSCA.
* Fix error getting IP info in OCCI conn.
* Fix error in Azure conn creating a VM with only a public net attached.
* Fix error in contextualization nodes with private leys.
* More bugfixes and improvements...

#### List of RfCs
* Improve getting Public network name in OCCI: https://github.com/grycap/im/issues/398.
* Improve Ansible contextualization to scale more than 50 VMs: https://github.com/grycap/im/issues/393.
* Add Support Custom instance types in Google Conn: https://github.com/grycap/im/issues/389.
* Implements Delete SGs in ONE conn only in last VM: https://github.com/grycap/im/issues/390.
* Fix error getting contmsg output in case of use colors: https://github.com/grycap/im/issues/387.
* Fix error in SSH module in sftp_put_dir if src dir ends with /: https://github.com/grycap/im/issues/385.
* Fix SSL verification error in windows: https://github.com/grycap/im/issues/381.
* Enable to add IPs in OCCI conn in AlterVM: https://github.com/grycap/im/issues/333.
* Fix error in OpenStack conn trying to assing a floating IP to VM with public IP: https://github.com/grycap/im/issues/379.
* Wait SSH access to VMs only in one ctxt task: https://github.com/grycap/im/issues/376.
* Create only one storage account per Infrastructure instead of per VM in Azure conn: https://github.com/grycap/im/issues/362.
* Improve save data in VM creation process: https://github.com/grycap/im/issues/358.
* Fix Error creating NGS in Azure conn: https://github.com/grycap/im/issues/352.
* Return false if VM does not exists in updateVMInfo: https://github.com/grycap/im/issues/354.
* Update Ansible roles in Master node in reconfiguration: https://github.com/grycap/im/issues/349.
* Fix error in Azure conn creating subnet: https://github.com/grycap/im/issues/351.
* Fix error in Context. process in basic test in SSH tests: https://github.com/grycap/im/issues/348.
* Add compatiblity with Ansible 2.4.0: https://github.com/grycap/im/issues/410.
* Fix error in ctxt process in some cases in OpenStack sites: https://github.com/grycap/im/issues/408.
* Enable to specify private network_name without .PRIVATE at the end: https://github.com/indigo-dc/im/issues/196.
* Fix Error using funtions to set a value of a BlockStorage: https://github.com/indigo-dc/im/issues/193.
* Enable to specify not using a private ip in a Cumpute node: https://github.com/indigo-dc/im/issues/191.

#### Installation & Configuration
* The supported platforms
  * CentOS 7
  * Ubuntu 14.04
  * Ubuntu 16.04

#### Documentation
* https://indigo-dc.gitbooks.io/im/content/
        
#### Artefacts
* CentOS 7
  * [IM-1.6.1-1.el7.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/IM-1.6.1-1.el7.noarch.rpm)
* Ubuntu 14.04
  * [python-im_1.6.1-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/python-im_1.6.1-1_all.deb)
* Ubuntu 16.04
  * [python-im_1.6.1-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/python-im_1.6.1-1_all.deb)
* Docker Container:
  * [indigodatacloud/im:indigo_2](https://hub.docker.com/r/indigodatacloud/im/tags/)

## <a name="imjavaapi"></a>Infrastructure Manager Java API v. 0.4.10

#### What's new
* Allow to set up custom ids for authN headers

#### List of RfCs
* Allow to set up custom ids for authN headers https://github.com/indigo-dc/im-java-api/pull/41
* Fix wrong auth_version value for Openstack V3 (with password) authorization header https://github.com/indigo-dc/im-java-api/pull/41
* Support subscription_id param in Azure auth header https://github.com/indigo-dc/im-java-api/pull/44

#### Installation & Configuration
* The supported platforms
  * CentOS 6
  * CentOS 7
  * Ubuntu 14.04
  * Ubuntu 16.04

#### Installation & Configuration

* To know how install the im-java-api library please read the documentation available in:
  * https://indigo-dc.gitbooks.io/im-java-api/content/
* To update the library you only need to substitute the im-java-api-X.X.X.jar
        
#### Artefacts
Tarballs:
* [im-java-api-0.4.10.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/im-java-api-v0.4.10.tar.gz)
* [im-java-api-0.4.10-jar-with-dependencies.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/im-java-api-0.4.10-jar-with-dependencies.tar.gz)


## <a name="kepler"></a>Indigo-Kepler v 1.3

#### What's new
* A CLI client built on top of existing library to communicate with FutureGateway. It allows to submit & monitor tasks, upload & download files and query for available applications

#### List of RfCs
* A CLI client exposing basic FutureGateway functionality to the command line
* Updated workflows and scripts to support ENES use case
* Fixed a bug with incorrect handling of timezone offset when parsing timestamps

#### Installation & Configuration
How to update: use provided Docker images versioned equally to the main libraries.

#### Artefacts

* Sources
  * https://github.com/indigo-dc/indigoclient/releases/tag/v1.3
  * https://github.com/indigo-dc/indigokepler/releases/tag/v1.3
* Ansible role indigo-dc/kepler v1.3 pushed to Ansiible Galaxy
* Ansible role indigo-dc/kepler-batch v1.3 pushed to Ansible Galaxy
* Docker image indigodatacloudapps/kepler:1.3 pushed to Docker Hub
* Docker image indigodatacloudapps/kepler-batch:1.3 pushed to Docker Hub

* CentOS7 source tarballs
  * [indigoclient-v1.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/indigoclient-v1.3.tar.gz)
  * [indigokepler-v1.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/indigokepler-v1.3.tar.gz) 

* Ubuntu16.04 source tarballs
  * [indigoclient-v1.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/indigoclient-v1.3.tar.gz)
  * [indigokepler-v1.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/indigokepler-v1.3.tar.gz) 

* Container
  * [indigodatacloudapps/kepler:indigo_2](https://hub.docker.com/r/indigodatacloudapps/kepler/tags/)
  * [indigodatacloudapps/kepler-batch:indigo_2](https://hub.docker.com/r/indigodatacloudapps/kepler-batch/tags/)


## <a name="synergy"></a>Synergy Service, v. 1.5.3  and Scheduler Manager, v. 2.6.0

#### What's new
This update brings many new features and bug fixes like
* New Synergy service features:
  * added security support
* New Synergy Scheduler Manager features:
  * Added improvement on queue management algorithm ( Synergy should scale up the oldest user requests from the queue)
  * Added a mechanism that performs user actions before Synergy deletes the VMs

#### List of RfCs

* https://launchpad.net/synergy-service/+milestone/1.5.3
* https://launchpad.net/synergy-scheduler-manager/+milestone/2.6.0


* Complete list of issues is available at: https://review.openstack.org/#/q/projects:openstack/synergy

#### Installation & Configuration
* https://github.com/indigo-dc/synergy-doc
* https://indigo-dc.gitbooks.io/synergy-doc/content/
* Service Reference Card: https://indigo-dc.gitbooks.io/synergy-doc/content/doc/service_reference_card.html
* Update/Upgrade Synergy packages: https://indigo-dc.gitbooks.io/synergy-doc/content/doc/admin.html

#### Artefacts
* Supported Operating Systems platforms:
  * CentOS 7
  * Ubuntu 16.04
* Supported CMF (Cloud Management Framework) versions:
  * OpenStack v. Ocata
  * OpenStack v. Newton
  * OpenStack v. Mitaka (only CentOS 7)
  * OpenStack v. Liberty (only CentOS 7)

Packages:
* CentOS7
  * [python-synergy-service-1.5.3-2.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/python-synergy-service-1.5.3-2.el7.centos.noarch.rpm)
  * [python-synergy-scheduler-manager-2.6.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/python-synergy-scheduler-manager-2.6.0-1.el7.centos.noarch.rpm)
* Ubuntu 14.04
  * [python-synergy-service_1.5.3_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/python-synergy-service_1.5.3_all.deb)
  * [python-synergy-scheduler-manager_2.5.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/python-synergy-scheduler-manager_2.6.0_all.deb)


## <a name="lp"></a>LiferayPlugIns v. 2.2.1

#### What's new
* The new version includes:
  * the autogeneration of the UI for TOSCA based application
  * the access to runtime data in the UI.
  * Improved token management reducing the communication with IAM endpoints.
  * several bug fixes.

#### List of RfCs
* [Issue-28](https://github.com/indigo-dc/LiferayPlugIns/issues/28) - Support Runtime Data of the tasks 
* [Issue-30](https://github.com/indigo-dc/LiferayPlugIns/issues/30) - Ajax call should be async
* [Issue-31](https://github.com/indigo-dc/LiferayPlugIns/issues/31) - Default paramter file generation
* [Issue-32](https://github.com/indigo-dc/LiferayPlugIns/issues/32) - Javascript dependency error 
* [Issue-34](https://github.com/indigo-dc/LiferayPlugIns/issues/34) - Remove or improve alert messages
* [Issue-36](https://github.com/indigo-dc/LiferayPlugIns/issues/36) - Caching keys for token validation
* [Issue-38](https://github.com/indigo-dc/LiferayPlugIns/issues/38) - Default values in TOSCA template should be selected in Customisable Application Portlet
* [Issue-40](https://github.com/indigo-dc/LiferayPlugIns/issues/40) - Float field in the UI should accept integer
* [Issue-42](https://github.com/indigo-dc/LiferayPlugIns/issues/42) - Admin portlet should list task for all users
* [Issue-43](https://github.com/indigo-dc/LiferayPlugIns/issues/43) - UserInfo endpoint called with expired token
* [Issue-49](https://github.com/indigo-dc/LiferayPlugIns/issues/49) - OneProvider dns only name

#### Installation \& Configuration
* Provided details in the documentation. In short administrator should add the new modules from the Liferay control panel and disable/remove the previous.

* More information can be found in the "Upgrade to a new release" section of the [Administration Guide](https://indigo-dc.gitbooks.io/liferay-plugins/content/)

#### Artefacts
* CentOS 7
  * [LiferayPlugins-binary-2.2.1.tgz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/LiferayPlugins-binary-2.2.1.tgz)
* Ubuntu14.04
  * [LiferayPlugIns-binary-2.2.1.tgz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/LiferayPlugins-binary-2.2.1.tgz)

## <a name="clues"></a>CLUES v. 1.0.0

#### What's new
* Several bugfixes

#### List of RfCs
* Assure not to delete non existing resources -> https://github.com/indigo-dc/clues-indigo/pull/47
* Show statusReason in clues log -> https://github.com/indigo-dc/clues-indigo/pull/47
* Bugfix deleting nodes -> https://github.com/indigo-dc/clues-indigo/pull/48
* Fix error in mesos plugin in case no data returned by _obtain_mesos_jobs -> https://github.com/indigo-dc/clues-indigo/pull/50

#### Installation & Configuration
* Ansible role available in (always install latest version):
  * https://github.com/indigo-dc/ansible-role-clues
* Documentation
  * https://www.gitbook.com/book/indigo-dc/clues-indigo/details

#### Artefacts
The supported platforms
* CentOS 7
* Ubuntu 14.04
* Ubuntu 16.04

* CentOS 7
  * [clues-indigo-v1.0.0.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/clues-indigo-v1.0.0.tar.gz)
* Ubuntu 16.04
  * [clues-indigo-v1.0.0.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/clues-indigo-v1.0.0.tar.gz)
