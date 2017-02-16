# Seventh Update of INDIGO-1 - 03.02.2017

The Seventh Update of INDIGO-1 release contains:
* [CloudProviderRanker v. 0.5.2](#cpr)
* [CloudInfoProvider v. 0.10.0](#cip)
* [Infrastructure Manager v1.5.0](#im)
* [Ophidia v. 0.11.0](#ophidia)
* [Monitoring - Zabbix-probes v. 1.02](#zp)
* [TOSCA-parser v. 0.7.1](#tp)
* [udocker v. 1.0.1](#ud)
* [WaTTSon v. 1.0.0](#wt)




## <a name="cpr"></a>CloudProviderRanker v.0.5.2

#### What's new
* This release provides new functionality like  the abbility to retrieve and set of priority and normalization parameters by mean of 4 new APIs:
  * /custom-paas-parameters
  * /get-paas-parameters
  * /get-sla-parameters
  * /custom-sla-parameters

#### List of RfCs
* Features:
  * [#5](https://github.com/indigo-dc/CloudProviderRanker/issues/5) - Need to get/modify normalization parameters  
* More information about bug fixes and other developments can be found on our [GitHub CloudProviderRanker issue tracker](https://github.com/indigo-dc/CloudProviderRanker/issues) 

#### Installation & Configuration
* It is enough to upgrade the package and restart the service:<br>
  ```/etc/init.d/cloudproviderranker (stop/start)```
* Service Reference Card is available [here](https://indigo-dc.gitbooks.io/cloud-provider-ranker/content/chapter6.html)

#### Artefacts
Packages:
* CentOS7
  * [CloudProviderRanker-0.5.2-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/CloudProviderRanker-0.5.2-1.noarch.rpm)
* Ubuntu 14.04
  * [CloudProviderRanker-0.5.2-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/CloudProviderRanker-0.5.2-1_all.deb)

## <a name="cip"></a>CloudInfoProvider: cloud-info-provider-indigo, v 0.10.0 & cloud-info-provider: 0.7.0

#### What's new
* This update provides <b>reepositories and packaging refactoring</b>: 
  * INDIGO-related content has been moved to a dedicated repository and the cloud-info-provider is now using the stock version as features developed in the context of INDIGO have been merged in it. 
  * With this update it is possible to have only the cloud-info-provider package to register site information in both the CMDB and a Site BDII just by using different arguments and templates. 
  * INDIGO-related templates are deployed by the cloud-info-provider-indigo package.

#### List of RfCs
* [#28](https://github.com/indigo-dc/cloud-info-provider/issues/28) - Splitting repositories/packages
* Documentation update related to new splitted packages
* Ansible role update to use new splitted packages

#### Installation & Configuration

* No manual intervention should be needed, but in case there are existing cron tasks they will have to take into account the following changes:
  * cloud-info-provider-indigo-service has been renamed to cloud-info-provider-service as cloud-info-provider is now using the stock version
  * /etc/cloud-info-provider-indigo has been renamed to /etc/cloud-info-provider as cloud-info-provider is now using the stock version. If needed copy any customization to the new directory.
* RHEL</br>
  ``` yum clean all && yum update cloud-info-provider-indigo```
* Ubuntu</br>
  ``` apt-get update && apt-get install -V python-cloud-info-prov```

#### Artefacts
* RedHat
  * [cloud-info-provider-indigo-0.10.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/cloud-info-provider-indigo-0.10.0-1.el7.centos.noarch.rpm) - All INDIGO-specific content (JSON templates, send-to-cmdb script and documentation). Dependent on cloud-info-provider.
  * [cloud-info-provider-0.7.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/cloud-info-provider-0.7.0-1.el7.centos.noarch.rpm) - Upstream version of the cloud-info-provider including changes made in the context of INDIGO.
* Ubuntu
  * [python-cloud-info-provider-indigo_0.10.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-cloud-info-provider-indigo_0.10.0_all.deb)
  * [python-cloud-info-provider_0.7.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-cloud-info-provider_0.7.0_all.deb)
* ansible-role-cloud-info-provider: 0.1.0. Ansible role has been updated to work with the splitted packages.


## <a name="im"></a>Infrastructure Manager v 1.5.0

#### What's new
* The updated version of the IM provides several bugfixes and improvements like:
  * Remove DATA_FILE from configuration. Only DB now.
  * Remove use of insecure Pickle data.
  * Support for Understanding VPC-related Network Information.
  * Support INDIGO Openstack sites as single site.
  * Several improvements and bugfixes.

#### List of RfCs
* [Issue #188](https://github.com/grycap/im/issues/188) - Add support for OpenStack pool name in OCCI connector
* [Issue #148](https://github.com/grycap/im/issues/148) - Add FW creation support in GCE connector
* [Issue #175](https://github.com/grycap/im/issues/175) - Kubernetes errors
* [Issue #171](https://github.com/grycap/im/issues/171) - Improve Docker connection with network management
* [Issue #167](https://github.com/grycap/im/issues/167) - Bugfix killing child processes
* [Issue #161](https://github.com/grycap/im/issues/161) - Error in GCE connector in case of multiples nodes
* [Issue #140](https://github.com/grycap/im/issues/140) - Move connectors from httplib to requests lib
* [Issue #110](https://github.com/grycap/im/issues/110) - Improve data management in DB to enable HA
* [Issue #141](https://github.com/grycap/im/issues/141) - Move Azure connector to Resource Groups API:
* [Issue #134](https://github.com/grycap/im/issues/134) - Try to change not maintainer SOAPpy lib
* [Issue #129](https://github.com/grycap/im/issues/129) - Save IM data in JSON format
* [Issue #111](https://github.com/grycap/im/issues/111) - Use Vault to improve security in recipes management:
* [Issue #119](https://github.com/grycap/im/issues/119) - Set restrictive permissions in the master VM data dir:
* [Issue #132](https://github.com/grycap/im/issues/132) - Support for Understanding VPC-related Network Information
* [Issue #122](https://github.com/grycap/im/issues/122) - Support INDIGO Openstack sites as single site

#### Installation & Configuration
* To upgrade to the last version first you have to install the new version using yum or apt tool:<br>
  ``` # yum update IM```<br>
  ``` # apt install python-im```<br>

* As there is a change in the DB format. Old 1.4.X data must be updated. Use the script: db_1_4_to_1_5.py to update the DB format:
  * In case that you were using a DATA_FILE to store the IM data (the default option in old version of IM), define the DATA_DB in the im.cfg file.
  * Execute the script db_1_4_to_1_5.py (https://raw.githubusercontent.com/grycap/im/master/scripts/db_1_4_to_1_5.py).
    * In case that you were using a DATA_FILE you have to specify it as the first parameter of the script.
    * If you were using a DATA_DB to store your data this parameter is not needed.
  * The data will be moved to the new format and old data will be renamed as table inf_list_XXXXXX.
  
* For containers  
  * Stop the old container:<br>
  ```# sudo docker stop im ```<br>
  * Remove the old container:<br>
  ```# sudo docker rm im ```<br>
  * Pull the new image version:<br>
  ```# sudo docker pull indigodatacloud/im``` <br> 
  * Start the new version:
  ```# sudo docker run -d -p 8899:8899 -p 8800:8800 -e IM_DATA_DB=mysql://username:password@server/db_name --name im indigodatacloud/im  ``` 
  <br>

#### Artefacts
* CentOS7
  * [IM-1.5.0-1.el7.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/IM-1.5.0-1.el7.noarch.rpm)
* Ubuntu14.04
  * [python-im_1.5.0-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-im_1.5.0-1_all.deb)
* Container
  * [indigodatacloud/im:indigo_1](https://hub.docker.com/r/indigodatacloud/im/tags/)


## <a name="ophidia"></a>Ophidia v. 0.11.0

#### What's new
* This version includes stronger support for custom missing values, the new "watch” command for the terminal to repeat periodically the submission (e.g. useful to control workflow status), a simplified configuration and some bug fixes and optimizations for massive and interactive operations.

#### List of RfCs

* Fixed:
  * Bug regarding metadatakey table update on cube deletion
  * Bug [#9](https://github.com/OphidiaBigData/ophidia-analytics-framework/issues/9)
  * Bug [#7](https://github.com/OphidiaBigData/ophidia-analytics-framework/issues/7)
  * Bug [#5](https://github.com/OphidiaBigData/ophidia-analytics-framework/issues/5)
  * Unit tests
  * Bug that raises an error message at the end of leaf tasks
  * Bug when an interactive task is terminated by OPH_CANCEL
  * Bugs in building the list of cubes to be processed by 'exit action’
  * Bug in oph_sub_array, oph_div_array, oph_dump ans oph_to_bin primitives
* Added:
  * Max and min operations to OPH_INTERCUBE operator
  * Argument 'status_filter' to OPH_RESUME operator XML file
  * Support for missing values to several operators and primitives
  * Support for base64-encoded dimensions [#10](https://github.com/OphidiaBigData/ophidia-analytics-framework/issues/10)
  * Watch command
  * Use of BASE_SRC_PATH as prefix of files involved in massive and interactive operations
 * Changed:
  * OPH_EXPORTNC2 to handle multiple row selection and export
  * OPH_INTERCUBE operator to allow comparison of cubes stored on different IO nodes
  * Configuration parameters names in oph_configuration (framework) and ophidiadb.conf (server)
  * Disabled usage of libSSH by default
  * Number of cores to execute each light task of final task to 1
  * View command to filter jobs based on their status
* Removed:
  * oph_dim_configuration from framework file (unified with oph_configuration)
  * OPH_IMPORTNC and OPH_IMPORTNC2 operators (deprecated)
  
* For more details please read the [Release Notes of Ophidia-0.11.0-0](https://indigo-dc.gitbooks.io/ophidia/content/release_notes.html)

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the Ophidia Upgrade Guide](https://indigo-dc.gitbooks.io/ophidia/content/upgrade.html)
* [Ophidia Service Reference Card](https://indigo-dc.gitbooks.io/ophidia/content/service_reference_card.html)

## Artefacts
Packages:
* Ubuntu 14.04
  * [ophidia-analytics-framework_0.11.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-analytics-framework_0.11.0-0_amd64.deb)
  * [ophidia-primitives_0.11.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-primitives_0.11.0-0_amd64.deb)
  * [ophidia-server_0.11.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-server_0.11.0-0_amd64.deb)
  * [ophidia-terminal_0.11.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/ophidia-terminal_0.11.0-0_amd64.deb)
* CentOS 7 
  * [ophidia-analytics-framework-0.11.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-analytics-framework-0.11.0-0.el7.centos.x86_64.rpm)
  * [ophidia-primitives-0.11.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-primitives-0.11.0-0.el7.centos.x86_64.rpm)
  * [ophidia-server-0.11.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-server-0.11.0-0.el7.centos.x86_64.rpm)
  * [ophidia-terminal-0.11.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/ophidia-terminal-0.11.0-0.el7.centos.x86_64.rpm)
  
## <a name="zp"></a>Monitoring  - Zabbix-probes v. 1.02

#### What's new
* The current update provides new probes - Mesos cluster probes which includes probes for Mesos, Marathon and Chronos

#### List of RfCs
* New feature:
  * Implemented Mesos, Chronos and Marathon probes

#### Installation & Configuration
* The Monitoring - Zabbix probes documentation has been updated and is available at https://www.gitbook.com/book/indigo-dc/monitoring/details
* New probe documentation is available at: https://indigo-dc.gitbooks.io/monitoring/content/doc/mesos.html

#### Artefacts
* CentOS7
  * [MesosZabbixProbe-1.01-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/MesosZabbixProbe-1.01-1.noarch.rpm)
* Ubuntu14.04
  * [mesos-zabbix-probe-1.01.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/mesos-zabbix-probe-1.01.deb)

## <a name="synergy"></a>Synergy Service, v. 1.4.0  and Scheduler Manager, v. 2.3.0

#### What's new
This update brings the support for the OpenStack <b>Mitaka</b> version and many new features and bug fixes like
* new **Synergy Service** features:
  * Synergy CLI command enhanced to support SSL
* new **Synergy Schedule Manager** features:
  * Retry mechanism improved
  * Added support for the automatic recycle of DB connections
  * Added support for Keystone domains
  * Added support for AMQP HA to NovaManager
  * Enable SSL for OpenStack Trust
  * NovaManager and KeystoneManager enhanced to support SSL


#### List of RfCs

* List of RfCs are available at:
  * [https://launchpad.net/synergy-service/+milestone/1.4.0](https://launchpad.net/synergy-service/+milestone/1.4.0)
  * [https://launchpad.net/synergy-scheduler-manager/+milestone/2.3.0](https://launchpad.net/synergy-scheduler-manager/+milestone/2.3.0)
  
#### Installation & Configuration
* [https://indigo-dc.gitbooks.io/synergy-doc/content/](https://indigo-dc.gitbooks.io/synergy-doc/content/)
* Service Reference Card: [https://indigo-dc.gitbooks.io/synergy-doc/content/doc/service_reference_card.html](https://indigo-dc.gitbooks.io/synergy-doc/content/doc/service_reference_card.html)
* Update/Upgrade Synergy packages: [https://indigo-dc.gitbooks.io/synergy-doc/content/doc/admin.html](https://indigo-dc.gitbooks.io/synergy-doc/content/doc/admin.html)

#### Artefacts
Packages:
* CentOS7
  * Liberty
    * [python-synergy-service-1.4.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/python-synergy-service-1.4.0-1.el7.centos.noarch.rpm)
    * [python-synergy-scheduler-manager-2.3.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/python-synergy-scheduler-manager-2.3.0-1.el7.centos.noarch.rpm)
  * Mitaka
    * [python-synergy-service-1.4.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/python-synergy-service-1.4.0-1.el7.centos.noarch.rpm)
    * [python-synergy-scheduler-manager-2.3.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/python-synergy-scheduler-manager-2.3.0-1.el7.centos.noarch.rpm)
* Ubuntu 14.04
  * Liberty
    * [python-synergy-service_1.4.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-synergy-service_1.4.0_all.deb)
    * [python-synergy-scheduler-manager_2.2.2_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-synergy-scheduler-manager_2.2.2_all.deb)
  * Mitaka
    * [python-synergy-service_1.4.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-synergy-service_1.4.0_all.deb)
    * [python-synergy-scheduler-manager_2.3.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-synergy-scheduler-manager_2.3.0_all.deb)


## <a name="tp"></a>TOSCA-parser v. 0.7.1

#### What's new
* The updated version of TOSCA-parser addresses minor bug fixes and integrates the changes made upstream (in openstack/tosca-parser v.0.7).

#### Installation & Configuration
In order to update the packages please use:
* For CentOS 7:<br>
  ``` # yum clean all && yum update tosca-parser```<br>
* For Ubuntu 14:04:<br>
  ```# apt-get update && apt-get install python-tosca-parser```<br>
  
#### Artefacts
* CentOS7
  * [tosca-parser-0.7.1-1.el7.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/centos7/x86_64/updates/tosca-parser-0.7.1-1.el7.noarch.rpm)
* Ubuntu14.04
  * [python-tosca-parser_0.7.1-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-tosca-parser_0.7.1-1_all.deb)

## <a name="ud"></a>udocker v. 1.0.1

#### What's new

* *udocker version 1.0.1* provides support for private docker repositories, better support for docker registry v2 API, verification of image layers integrity, improved download handling, Improved message handling, and packages for CentOS 7 and Ubuntu 14.04.

#### List of RfCs

* Bug fixes
  * Minor bugfixes
  * Executable name changed from udocker.py to udocker
  * Insecure flag fixed

* New features and improvements
  * Added support for login into docker repositories
  * Added support for private repositories
  * Added support for listing of v2 repositories catalog
  * Added checksum verification for sha256 layers
  * Improved download handling for v1 and v2 repositories
  * Improved installation tarball structure
  * Address seccomp change introduced on kernels >= 4.8.8
  * Utilities for packaging
  * [#24](https://github.com/indigo-dc/udocker/issues/24) - Improved verbose levels, messaging and output
  * [#29](https://github.com/indigo-dc/udocker/issues/29) - Fully implement support for registry selection --registry parameter
  * [#30](https://github.com/indigo-dc/udocker/issues/24) - Provide support for private repositories e.g. gitlab registries
  * [#31](https://github.com/indigo-dc/udocker/issues/24) - Provide --insecure command line parameter for SSL requests

#### Installation & Configuration

* GitBook available at: [https://www.gitbook.com/book/indigo-dc/udocker/details](https://www.gitbook.com/book/indigo-dc/udocker/details)
* in addition a udocker.1 man page is also distributed
* How to update/upgrade an already deployed service
  * The information is available in the installation_manual in GitBook
  * For the users using the tarball</br>
  ```curl http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/tgz/udocker-1.0.1.tar.gz > udocker-1.0.1.tar.gz```
  ```export UDOCKER_TARBALL=$(pwd)/udocker-1.0.1.tar.gz```
  ```tar xzvf $UDOCKER_TARBALL udocker```
  ```./udocker # automatically updates the installation from the tarball ```
  
#### Artefacts
* The binary tarball [udocker-1.0.1.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/tgz/udocker-1.0.1.tar.gz) is very important for the current users as they cannot rely on RPMs and DEBs.
* CentOS7
  * [udocker-1.0.1-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/udocker-1.0.1-1.noarch.rpm)
  * [udocker-preng-1.0.1-1.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/udocker-1.0.1-1.noarch.rpm)
* Ubuntu14.04
  * [udocker_1.0.1-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/udocker_1.0.1-1_all.deb)
  * [udocker-preng_1.0.1-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/udocker-preng_1.0.1-1_amd64.deb)


## <a name="wt"></a>TTSc -> WaTTSon v. 1.0.0

#### What's new

* WaTTSon is a complete reimplementation of the TTS client in the Go programming language.

#### List of RfCs

* As WaTTSon is used in functional testing of WaTTS and might also be used by other applications it has:
  * a flag to support pure json output (https://github.com/indigo-dc/wattson/issues/2)
  * supporting both protocols, for TTS v0.4 and for the upcomming WaTTS 1.0 (https://github.com/indigo-dc/wattson/issues/3)
  * supporting the upcoming advanced requests, which are request with parameter (https://github.com/indigo-dc/wattson/issues/8)
calles wattson, to have no name clash with ttsc, which might be still present on some systems (https://github.com/indigo-dc/wattson/issues/10)

#### Installation & Configuration

* Documentation is written as [README](https://github.com/indigo-dc/wattson/blob/master/README.md) and [GitBook](https://indigo-dc.gitbooks.io/wattson/content/)
* No need to upgrade/deploy it is just a single binary command line client to execute:
  * after enabling the INDIGO-DataCloud repositories jsut do:
    ```yum install wattson```<br/>
    ```apt-get install wattson```
 
 #### Artefacts
 * CentOS7
  * [wattson-1.0.0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/wattson-1.0.0.el7.centos.x86_64.rpm)
* Ubuntu14.04
  * [wattson-1.0.0-amd64.de](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/wattson-1.0.0-amd64.deb)
    
