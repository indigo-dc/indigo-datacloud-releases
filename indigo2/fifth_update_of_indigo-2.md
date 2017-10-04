# Fifth Update of INDIGO-2 - 30/09/2017

The Fifth Update of INDIGO-2 release contains:
* [Accounting v. 1.5.0-1](#accounting)
* [IAM v. 1.1.0](#iam)
* [IM v. 1.6.1](#im)
* [IM Java API v. 0.4.10](#imjavaapi)
* [INDIGO-Kepler v. 1.3](#kepler)
* [Synergy: Service v. 1.5.3 & Scheduler-Manager v. 2.6.0](#synergy)
* [Liferay Plugins v. 2.2.1](#lp)
* [CLUES v. 2.2.1](#clues)
* [CDMI Server v. 1.2.1](#cdmi)
* [CDMI S3 QoS v. 2.0](#cdmi-s3)
* [CDMI STORM plugin v. 0.1.0](#cdmi-storm)
* [OIDC-Agent v. 1.1.1](#oidca)
* [Orchent v. 1.2.0](#orchent)
* [Orchestrator v. 1.5.0-FINAL](#orchestrator)
* [OOI v. 1.2.0](#ooi)
* [Synergy: Service v. 1.5.2 & Scheduler-Manager v. 2.5.0](#synerg)
* [SLAM v 1.3.1](#slam)
* [TOSCA-parser v. 0.8.3](#tp)
* [TOSCA types v. 2.1.0](#tt)
* [udocker v. 1.2.1](#watts)
* [WaTTs v. 1.1.0](#ud)
* [WaTTSon v. 1.2.1](#wattson)
* [Monitoring - Zabbix-probes v. 1.03](#zp)



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

* To know how install the im-java-api library please read the documentation available in:
  * https://indigo-dc.gitbooks.io/im-java-api/content/
* To update the library you only need to substitute the im-java-api-X.X.X.jar
        
#### Artefacts
Tarballs:
* [im-java-api-0.4.10.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/im-java-api-v0.4.10.tar.gz)
* [im-java-api-0.4.10-jar-with-dependencies.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/im-java-api-0.4.10-jar-with-dependencies.tar.gz)

## <a name="iam"></a>INDIGO IAM v.1.1.0

#### What's new
This release provides fixes to some outstanding bugs and improvements:
* New Features
  * The login button text can now be customized for local and SAML login
  * A privacy policy can now be linked to the IAM login page
  * Improved error pages rendering
  * SAML metadata can now be filtered according to certain conditions (e.g., SIRTFI compliance)
  * The organisation name is now included in the IAM dashboard top bar
  * IAM now implements a scope policy management API that allows to restrict the use of OAuth scopes only to selected users or group of users
* Fixes
  * IAM now correctly enforces SAML metadata signature checks
  * The subject of IAM notification messages now includes the organization name


More details:
https://github.com/indigo-iam/iam/releases/tag/v1.1.0

#### List of RfCs
  
* More information about bug fixes and other developments can be found on our [GitHub IAM issue tracker](https://github.com/indigo-iam/iam/releases/tag/v1.1.0) 

#### Installation & Configuration
* IAM Login Service can be deployed in two different ways:
  * as Docker container
  * as systemd daemon from precompiled packages

Also a Puppet module is provided to simplify the installation and setup. This module leveraging on the precompiled packages.
https://github.com/indigo-iam/puppet-indigo-iam

* the IAM service is provided on the following DockerHub repositories:
  * indigoiam/iam-login-service
  * indigodatacloud/iam-login-service

The IAM service is executed by starting the docker container with the following command:

<pre>
$ docker run --name iam-login-service \
  --net=iam -p 8080:8080 \
  --env-file=/path/to/iam-login-service/env \
   -v /path/to/keystore.jks:/keystore.jks:ro \
  indigodatacloud/iam-login-service
</pre>

See the gitbook admin guide [[https://indigo-dc.gitbooks.io/iam/content/doc/admin.html]] for all configuration variables description.

##### Deployment with precompiled packages

Since IAM 1.0.0, precompiled packages are available to install IAM Login services
Supported platforms:
* CentOS 7
* Ubuntu 16.04

Packages and repo files are hosted on https://repo.cloud.cnaf.infn.it/repository/indigo-iam public repository.

* *Installation*
  * Installed the required Indigo IAM repository, install the IAM login service package.
    * On CentOS: <pre>$ sudo yum install -y iam-login-service</pre></br>
    * On Ubuntu: <pre>$ sudo apt-get install -y iam-login-service</pre>

* *Run the service*
  * The service is managed by Systemd, so to run it use: <pre>$ sudo systemctl start iam-login-service</pre>

* *Service Reference*
  * IAM gitbook: https://indigo-dc.gitbooks.io/iam/content/doc/admin.html

* Please read the [Deployment and Administration guide](https://indigo-dc.gitbooks.io/iam/content/doc/admin.html)

<a id="id7"></a>
#### Artefacts
* Stable, certified rpm/deb releases suitable for use in production can be found at: https://repo.cloud.cnaf.infn.it/repository/indigo-iam/index.html

* Docker image can be found at:
https://hub.docker.com/r/indigodatacloud/iam-login-service/tags/ tag v1.1.0-latest

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

## <a name="slam"></a>SLAM v. 1.3.1

#### What's new
* introducing SLA for storage resources
* integration with ONEDATA to obtain user space
* enable CMDB-based recognition of service provider
* improved performance and UX
* fixing reported bugs

#### List of RfCs
* add onedata space metric to storage SLA - https://github.com/indigo-dc/slam/issues/19
* fix storage class select  - https://github.com/indigo-dc/slam/issues/18
* upgrade engine 1.3 -- authority redesing - https://github.com/indigo-dc/slam/issues/17
* adding ONEDATA URL option to docker https://github.com/indigo-dc/slam/pull/22
* fixing type of resource for computing SLA https://github.com/indigo-dc/slam/pull/21
* adding Storage SLA https://github.com/indigo-dc/slam/pull/20
* adding recognision of CMDB authorities https://github.com/indigo-dc/slam/pull/19
* OneData integration: fetching user spaces https://github.com/indigo-dc/slam/pull/18

#### Installation & Configuration

* FOr upgrade please read the section "Upgrade procedure" in https://indigo-dc.gitbooks.io/slam/content/installation.html
        
#### Artefacts
Container:
  * [indigodatacloudapps/slam:indigo_2](https://hub.docker.com/r/indigodatacloudapps/slam/tags/)


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

## <a name="cdmi"></a>CDMI Server v. 1.2.1

#### What's new
* Improved support for storage plugins

#### List of RfCs
* SLF4J: Class path contains multiple SLF4J bindings. -> https://github.com/indigo-dc/CDMI/issues/111

#### Installation & Configuration
* Upgrade Guide: https://indigo-dc.gitbooks.io/cdmi-qos/content/doc/updating_cdmi-qos.html
* Documentation
  * https://indigo-dc.gitbooks.io/cdmi-qos/content/
  * https://github.com/indigo-dc/CDMI/wiki/Service-Reference-Card

#### Artefacts

* [cdmi-server-1.2-1.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/cdmi-server-1.2-1.x86_64.rpm)
* [cdmi-server-1.2_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-upèdates/main/binary-amd64/cdmi-server-1.2_all.deb)
  
## <a name="cdmi-s3"></a>CDMI S3 QoS v. 2.0

#### What's new
* support for data namespace browsing. 
* support for CDMI export attribute, it allows to expose to the client information about configured data access protocols, thanks to that end user is able to find the data-object with WebDav for example, but to be well understand: export attribute only informs about alternative protocols, it doesn't provide them, if by any chance the data object is available through WebDAV then export attribute will tell it
* support for bunch of new QoS attributes including:
  * exposing information about data lifetime
  * exposing information about data retention policy
* removed dependency on cdmi-s3-qos-ceph-provider module, the information which was earlier provided by 
cdmi-s3-qos-ceph-provider now is partially read from configuration file (in case of static things) and partially is obtained directly from backed server through S3 protocol

#### Installation & Configuration

* Installation guide available at - https://indigo-dc.gitbooks.io/cdmi-s3-qos/content/
* Ansible role is available here: https://github.com/indigo-dc/ansible-role-cdmi-s3-qos
* Run with Docker
  * [https://indigo-dc.gitbooks.io/cdmi-s3-qos/content/doc/running_from_docker_image.html](https://indigo-dc.gitbooks.io/cdmi-s3-qos/content/doc/running_from_docker_image.html)
  
#### Artefacts

Packages
* [cdmi-s3-qos-2.0.0-1.el7.centos.x86_64](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/update/cdmi-s3-qos-2.0.0-1.el7.centos.x86_64.rpm)
* [cdmi-s3-qos-2.0.0.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/cdmi-s3-qos-2.0.0.deb)


## <a name="cdmi-storm"></a>CDMI STORM Plugin v. 0.1.0

#### What's new
* This is the first public release of the INDIGO CDMI StoRM plugin.
* For more details please read https://github.com/italiangrid/cdmi-storm/blob/master/CHANGELOG.md

#### Installation & Configuration

* Documentation is available at: https://www.gitbook.com/book/indigo-dc/cdmi-storm
#### Artefacts
The CDMI StoRM plugin is currently released as a RHEL7 rpm.
* [cdmi-storm-0.1.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/update/cdmi-storm-0.1.0-1.el7.centos.noarch.rpm)

## <a name="oidca"></a>OIDC-Agent v. 1.1.1

#### What's new
* *oidc-agent* is a new system service ensuring that always a valid access token is available for
the command line.
* for more information please see: https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo2/oidc-agent2.html

## <a name="orchent"></a>Orchent v. 1.2.0

#### What's new
* Highlights of this update are:
  * interface to the newly release oidc-agent

#### List of RfCs
* [Issue #29](https://github.com/indigo-dc/orchent/issues/29) - add oidc-agent support


#### Installation & Configuration
* Documentation is avalable at - [Orchent GitBook](https://github.com/indigo-dc/orchent/blob/master/gitbook/user.md) chapter "Setting the Access Token"

#### Artefacts
* CentOS 7
  * [orchent-1.2.0-1.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/orchent-1.2.0.el7.centos.x86_64.rpm)
* Ubuntu 16.04
  * [orchent-1.2.0-amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/orchent-1.2.0-amd64.deb)

* Container
  * [indigodatacloud/orchent:indigo_2](https://hub.docker.com/r/indigodatacloud/orchent/tags)

## <a name="orchestrator"></a>Orchestrator v. 1.5.0-FINAL

#### What's new
* The current update adds support for Azure, increased support for Openstack and better configuration experience

#### List of RfCs
* Enable the users to retrieve the underlining IaaS IDs ([#237](https://github.com/indigo-dc/orchestrator/issues/237))
* Evaluation of the TOSCA Concat function ([#239](https://github.com/indigo-dc/orchestrator/issues/239))
* Retrieval of TOSCA attributes for Marathon Deployments ([#243](https://github.com/indigo-dc/orchestrator/issues/243))
* Deploy on Azure ([#244](https://github.com/indigo-dc/orchestrator/issues/244))
* Support for Openstack regions different from the default ones ([#245](https://github.com/indigo-dc/orchestrator/issues/245))
* Add support for local volumes for Mesos tasks ([#246](https://github.com/indigo-dc/orchestrator/issues/246))

#### Installation & Configuration
* Please read the "Upgrade guide": https://indigo-dc.gitbooks.io/indigo-paas-orchestrator/content/how_to_upgrade.html

#### Artefacts
* Docker Container:
  * [indigodatacloud/orchestrator:indigo_2](https://hub.docker.com/r/indigodatacloud/orchestrator/)


## <a name="tp"></a>TOSCA-parser v. 0.8.3

#### What's new
* The updated version of TOSCA-parser addresses some minor bugfixes


#### List of RfCs
* Fix error getting relationshps in case of custom_def capability: https://bugs.launchpad.net/tosca-parser/+bug/1687598
* Fix error getting a boolean capability property with value false: https://bugs.launchpad.net/tosca-parser/+bug/1697856


#### Installation & Configuration
In order to update the packages please use:
* For CentOS 7:<br>
  ``` yum clean all && yum update tosca-parser```<br>
* For Ubuntu 14:04/16.04:<br>
  ```apt-get update && apt-get install python-tosca-parser```<br>
  
  
#### Artefacts
* CentOS7
  * [tosca-parser-0.8.3-.el7.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/tosca-parser-0.8.2-1.el7.noarch.rpm)
* Ubuntu 14.04
  * [python-tosca-parser_0.8.3-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/python-tosca-parser_0.8.3-1_all.deb)
  * Ubuntu 16.04
  * [python-tosca-parser_0.8.3-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/python-tosca-parser_0.8.3-1_all.deb)
  
## <a name="tp"></a>TOSCA types v. 2.1.0

#### What's new
* The updated version of TOSCA types contains various improvements and adds some use cases


#### List of RfCs
* Add configuration parameters for Chronos and Marathon nodes
* Update template for Long-Running Services
* Improve Galaxy configuration.
* Fixing properties types for Spark
* Major improvements for Dariah use-case
* Update tosca types for cms use-case
* Added type for spark on mesos.
* Update Mesos types
* Updated Marathon app definition


#### Installation & Configuration
* Please see the https://github.com/indigo-dc/tosca-types/blob/master/README.md
  
  
#### Artefacts
* CentOS7
  * [tosca-types-v2.1.0.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/tosca-types-v2.1.0.tar.gz)
* Ubuntu 14.04
  * [tosca-types-v2.1.0.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/tosca-types-v2.1.0.tar.gz)
  * Ubuntu 16.04
  * [tosca-types-v2.1.0.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/tosca-types-v2.1.0.tar.gz)
  


## <a name="ud"></a>udocker v. 1.1.0

#### What's new
* udocker 1.1.0 includes additional container execution engines based on fakechroot and runC
which provide alternative methods to execute the containers based on different approaches.
These new engines can also deliver additional performance for applications that make intensive
use of system calls.


#### List of RfCs

* Bug fixes and new features:
  * Support image names prefixed by registry similarly to docker 
  * Add execution engine selection logic 
  * Add fr execution engine based on shared library interception 
  * Add rc execution engine based on rootless namespaces 
  * Improve proot tmp files cleanup on non ext filesystems 
  * Improve search returning on Docker repositories 
  * Improve runC execution portability 
  * Add environment variable UDOCKER_KEYSTORE
  * Prevent creation of .udocker when UDOCKER_KEYSTORE is used

#### Installation & Configuration
* Information for installation and upgrade is available in the GitBook documentation at
https://indigo-dc.gitbooks.io/udocker/content/doc/installation_manual.html

#### Artefacts
* Binary Tarball
  * [udocker-1.1.0.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/udocker-1.1.0.tar.gz)
* CentOS 7
  * [udocker-1.1.0-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/udocker-1.1.0-1.noarch.rpm)
  * [udocker-freng-1.1.0-1.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/udocker-freng-1.1.0-1.x86_64.rpm)
  * [udocker-preng-1.1.0-1.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/udocker-preng-1.1.0-1.x86_64.rpm)
  * [udocker-rceng-1.1.0-1.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/udocker-rceng-1.1.0-1.x86_64.rpm)

* Ubuntu 14.04
  * [udocker-freng_1.1.0-1.debian.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker-freng_1.1.0-1.debian.tar.gz)
  * [udocker-freng_1.1.0-1.dsc](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker-freng_1.1.0-1.dsc)
  * [udocker-freng_1.1.0-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/udocker-freng_1.1.0-1_amd64.deb)
  * [udocker-freng_1.1.0.orig.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker-freng_1.1.0.orig.tar.gz)
  * [udocker-preng_1.1.0-1.debian.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker-preng_1.1.0-1.debian.tar.gz)
  * [udocker-preng_1.1.0-1.dsc](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker-preng_1.1.0-1.dsc)
  * [udocker-preng_1.1.0-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/udocker-preng_1.1.0-1_amd64.deb)  
  * [udocker-preng_1.1.0.orig.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker-preng_1.1.0.orig.tar.gz)
  * [udocker-rceng_1.1.0-1.debian.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker-rceng_1.1.0-1.debian.tar.gz)
  * [udocker-rceng_1.1.0-1.dsc](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker-rceng_1.1.0-1.dsc)
  * [udocker-rceng_1.1.0-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/udocker-rceng_1.1.0-1_amd64.deb)
  * [udocker-rceng_1.1.0.orig.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker-rceng_1.1.0.orig.tar.gz)
  * [udocker_1.1.0-1.debian.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker_1.1.0-1.debian.tar.gz)
  * [udocker_1.1.0-1.dsc](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker_1.1.0-1.dsc)
  * [udocker_1.1.0-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/udocker_1.1.0-1_all.deb)
  * [udocker_1.1.0.orig.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/wattson-1.2.0-amd64.deb)

* Ubuntu 16.04
  * [udocker-freng_1.1.0-1.debian.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/udocker-freng_1.1.0-1.debian.tar.gz)
  * [udocker-freng_1.1.0-1.dsc](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/udocker-freng_1.1.0-1.dsc)
  * [udocker-freng_1.1.0-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/udocker-freng_1.1.0-1_amd64.deb)
  * [udocker-freng_1.1.0.orig.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/udocker-freng_1.1.0.orig.tar.gz)
  * [udocker-preng_1.1.0-1.debian.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/udocker-preng_1.1.0-1.debian.tar.gz)
  * [udocker-preng_1.1.0-1.dsc](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/udocker-preng_1.1.0-1.dsc)
  * [udocker-preng_1.1.0-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/udocker-preng_1.1.0-1_amd64.deb)  
  * [udocker-preng_1.1.0.orig.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/udocker-preng_1.1.0.orig.tar.gz)
  * [udocker-rceng_1.1.0-1.debian.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/udocker-rceng_1.1.0-1.debian.tar.gz)
  * [udocker-rceng_1.1.0-1.dsc](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker-rceng_1.1.0-1.dsc)
  * [udocker-rceng_1.1.0-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/udocker-rceng_1.1.0-1_amd64.deb)
  * [udocker-rceng_1.1.0.orig.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker-rceng_1.1.0.orig.tar.gz)
  * [udocker_1.1.0-1.debian.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker_1.1.0-1.debian.tar.gz)
  * [udocker_1.1.0-1.dsc](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/udocker_1.1.0-1.dsc)
  * [udocker_1.1.0-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/udocker_1.1.0-1_all.deb)
  * [udocker_1.1.0.orig.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/wattson-1.2.0-amd64.deb)
  
## <a name="watts"></a>WaTTS v. 1.2.1

#### What's new
* This update is just a bug fix release:
  * if caching is uses (which is done by default) access tokens are invalidated way to fast, this is now fixed
a workaroung is to disable caching by setting: oidc.cache_duration = none (version 1.1.0 to 1.2.0)

#### List of RfCs
* [new release](https://github.com/indigo-dc/tts/issues/2459)
* [caching issue with access token](https://github.com/indigo-dc/tts/issues/455)
* [use github to download erlang from, as it provides https instead of http](https://github.com/indigo-dc/tts/issues/456)

#### Installation & Configuration
   + Just update/install also documented here - https://github.com/indigo-dc/tts/blob/master/gitbook/admin.md

#### Artefacts
* CentOS 7
  * [tts-1.2.1-1.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/tts-1.2.1-1.el7.centos.x86_64.rpm)
* Ubuntu 14.04
  * [tts_1.2.1-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/tts_1.2.1-1_amd64.deb)
* Ubuntu 16.04
  * [tts_1.2.1-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/tts_1.2.1-1_amd64.deb)

## <a name="wattson"></a>WaTTSon v. 1.2.0

#### What's new
* This update provides integration with oidc-agent, so it can be used instead of storing an access token in an environmental varible

#### Installation & Configuration
   + Just update/install install also documented here - https://github.com/indigo-dc/wattson/tree/master/gitbook

#### Artefacts
* CentOS 7
  * [wattson-1.2.0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/wattson-1.2.0.el7.centos.x86_64.rpm)
* Ubuntu 14.04
  * [wattson-1.2.0-amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/wattson-1.2.0-amd64.deb)
* Ubuntu 16.04
  * [wattson-1.2.0-amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/wattson-1.2.0-amd64.deb)
* Docker container.
  * [indigodatacloud/wattson:indigo_2](https://hub.docker.com/r/indigodatacloud/wattson/tags/)

## <a name="zp"></a>Monitoring  - Zabbix-probes v. 1.03

#### What's new
* Authentication for Onedata through IAM service and automatic process for refreshing token.

#### List of RfCs
* Some connection errors broke up the process and were catched and fixed.
* A null lenght of oneprovider metrics broke up the process and were validated and fixed.
* Authentication for Onedata can be done with a valid IAM token. This token and a refresh token is requested by a script (Client application credentials are required) and passed to the monitoring agent as input parameters.

####  Installation and Configuration
* For Centos 6/7 and Ubuntu 14/16 download the respective installer and execute it. For other Linux distributions, download and copy into desired directory where monitoring agent is installed.
  * Centos:
    * https://github.com/indigo-dc/Monitoring/blob/master/zabbix-probes/onedata-zabbix-probe/doc/centos-installer.md
  * Ubuntu:
    * https://github.com/indigo-dc/Monitoring/blob/master/zabbix-probes/onedata-zabbix-probe/doc/ubuntu-installer.md


#### Artefacts

* CentOS7
  * [onedatazabbix-agent-1.0-1.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/onedatazabbix-agent-1.0-1.el7.centos.x86_64.rpm)
* Ubuntu16.04
  * [onedatazabbix-agent-1.0-Ubuntu16.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/monedatazabbix-agent-1.0-Ubuntu16.deb)

 
