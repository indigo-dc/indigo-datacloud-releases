# Seventh Update of INDIGO-1 - 03.02.2017

The Seventh Update of INDIGO-1 release contains:
* [CloudProviderRanker v. 0.5.2](#cpr)
* [CloudInfoProvider v. 0.10.0](#cip)
* [Ophidia v. 0.11.0](#ophidia)
* [Monitoring - Zabbix-probes v. 1.02](#zp)


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
* It is enough to upgrade the package and restart the service:</br>
  ``` /etc/init.d/cloudproviderranker (stop/start) ```
* Service Reference Card is available [here](https://indigo-dc.gitbooks.io/cloud-provider-ranker/content/chapter6.html)

#### Artefacts
Packages:
* CentOS7
  * [CloudProviderRanker-0.5.2-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/CloudProviderRanker-0.5.2-1.noarch.rpm)
* Ubuntu 14.04
  * [CloudProviderRanker-0.5.2-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/CloudProviderRanker-0.5.2-1_all.deb)

## <a name="cip"></a>CloudInfoProvider: cloud-info-provider-indigo, v 0.10.0 & cloud-info-provider: 0.7.0

#### What's new
* This update provides <b>reepositories and packaging refactoring<b/>: 
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
  
* For more details please read the [Ophidia-0.11.0-0](https://indigo-dc.gitbooks.io/ophidia/content/release_notes.html)

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


