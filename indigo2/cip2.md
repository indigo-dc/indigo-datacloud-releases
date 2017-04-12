# CloudInfoProvider

The **Cloud Information provider** generates a representation of cloud resources, to be published inside INDIGO - DataCloud CMDB.

## Summary:
<!--
* Updates
  * [CloudInfoProvider v. 0.10.0](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/seventh_update_of_indigo-1.html#cip)
  * [CloudInfoProvider v. 0.9.3](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/first_update_of_indigo-1.html#cip)
-->

* [Release Notes](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)

* [Documentation](#id6)
* [Support](#id8)

<a id="id1"></a>
## Release Notes - cloud-info-provider-indigo v. 0.10.0 & cloud-info-provider v. 0.7.0

<a id="id2"></a>
### What's new

Highlights of the INDIGO-2 release:
* This update provides <b>repositories and packaging refactoring</b>: 
* INDIGO-related content has been moved to a dedicated repository and the cloud-info-provider is now using the stock version as features developed in the context of INDIGO have been merged in it. 
* With this update it is possible to have only the cloud-info-provider package to register site information in both the CMDB and a Site BDII just by using different arguments and templates. 
* INDIGO-related templates are deployed by the cloud-info-provider-indigo package.

Supported Platforms
* CentOS7 and Ubuntu 14.04 (trusty)

<a id="id3"></a>
#### List of RfCs 

* [#28](https://github.com/indigo-dc/cloud-info-provider/issues/28) - Splitting repositories/packages
* Documentation update related to new splitted packages
* Ansible role update to use new splitted packages

<a id="id4"></a>
### Deployment Notes

installation & Configuration:

* No manual intervention should be needed, but in case there are existing cron tasks they will have to take into account the following changes:
  * cloud-info-provider-indigo-service has been renamed to cloud-info-provider-service as cloud-info-provider is now using the stock version
  * /etc/cloud-info-provider-indigo has been renamed to /etc/cloud-info-provider as cloud-info-provider is now using the stock version. If needed copy any customization to the new directory.
* RHEL</br>
  ``` yum clean all && yum update cloud-info-provider-indigo```
* Ubuntu</br>
  ``` apt-get update && apt-get install -V python-cloud-info-prov```

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

* RedHat
  * [cloud-info-provider-indigo-0.10.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/cloud-info-provider-indigo-0.10.0-1.el7.centos.noarch.rpm) - All INDIGO-specific content (JSON templates, send-to-cmdb script and documentation). Dependent on cloud-info-provider.
  * [cloud-info-provider-0.7.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/cloud-info-provider-0.7.0-1.el7.centos.noarch.rpm) - Upstream version of the cloud-info-provider including changes made in the context of INDIGO.
* Ubuntu
  * [python-cloud-info-provider-indigo_0.10.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/main/binary-amd64/python-cloud-info-provider-indigo_0.10.0_all.deb)
  * [python-cloud-info-provider_0.7.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/main/binary-amd64/python-cloud-info-provider_0.7.0_all.deb)
* [ansible-role-cloud-info-provider: 0.1.0](https://github.com/indigo-dc/ansible-role-cloud-info-provider). Ansible role has been updated to work with the splitted packages.

<a id="id6"></a>
## Documentation

* [CloudInfoProvider GitBook](https://indigo-dc.gitbooks.io/cloud-info-provider/content/) 

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
