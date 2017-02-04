# Seventh Update of INDIGO-1 - 03.02.2017

The Seventh Update of INDIGO-1 release contains:
* [CloudProviderRanker v. 0.5.2](#cpr)


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
