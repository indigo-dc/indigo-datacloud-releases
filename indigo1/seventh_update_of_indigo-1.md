# Seventh Update of INDIGO-1 - 03.02.2017

The Seventh Update of INDIGO-1 release contains:
* [CloudProviderRanker v. 0.5.2](#cpr)
* [CloudInfoProvider v. 0.10.0](#cip)

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



