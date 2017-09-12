# CloudProviderRanker

**CloudProviderRanker** is a standalone REST WEB Service which ranks cloud providers basing on rules implemented with the [Drools framework]( http://drools.org/)

The CloudProviderRanker checks if preferences have been specified; if they have, then they have absolute priority over any other provider's information (like monitoring data).

If preferences are not specified, for each provider the rank is calculated as sum of SLA's rank and a combination of monitoring data, each of them conveniently normalized with weight specified in a Ranker's configuration file.


# Summary:
* Updates
  * [CloudProviderRanker v. 0.6.0](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo2/fourth_update_of_indigo-2.md#cpr)

* [Release Notes v. 0.5.4-1](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 0.5.4-1

<a id="id2"></a>
### What's new

Highlights of INDIGO-2 version:
* This version fixes exceptions raised by badly JSON parsing which prevented the client from receiving the correct ranking.

Supported platforms
* Any Linux operating system supporting JRE >= 1.8 (CentOS, Ubuntu, etc.)

<a id="id3"></a>
#### List of RfCs 
* [#14](https://github.com/indigo-dc/CloudProviderRanker/issues/14) - Bug in Preference.java
* [#15](https://github.com/indigo-dc/CloudProviderRanker/issues/15) - Need to get/modify normalization parameters 
* [#16](https://github.com/indigo-dc/CloudProviderRanker/issues/16) - Bug in Sla.java
* [#17](https://github.com/indigo-dc/CloudProviderRanker/issues/17) - Bug in Service.java
* [#18](https://github.com/indigo-dc/CloudProviderRanker/issues/18) - Incorrect parameter label names in CustomPaaSParamHandler.java
* [#19](https://github.com/indigo-dc/CloudProviderRanker/issues/19) - Incorrect parameter label names in Restrictions.java

<a id="id4"></a>
### Deployment Notes

* Provided RPM and DEB packages.
* Both provide */etc/init.d/cloudproviderranker start/stop* script. 
* Installation of RPM also starts the service; de-installation stops the service

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-newton/rdo-release-newton-4.noarch.rpm``<br>
  ```$ yum clean all```<br>
  ```$ yum install CloudProviderRanker```<br>
* On Ubuntu 14.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:newton```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install CloudProviderRanker```

* More details regarding the installation and **configuration** can be found in the [CloudProviderRanker Deployment And Administration Guide](https://indigo-dc.gitbooks.io/cloud-provider-ranker/content/chapter1.html)

<a id="id5"></a>
### Known Issues
* N/A

<a id="id7"></a>
### List of Artifacts
Packages
* [CloudProviderRanker-0.5.4-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/CloudProviderRanker-0.5.4-1.noarch.rpm)
* [CloudProviderRanker-0.5.4-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/CloudProviderRanker-0.5.4-1_all.deb)

Docker Container
* [indigodatacloud/cloudproviderranker:indigo_2](https://hub.docker.com/r/indigodatacloud/cloudproviderranker/)

<a id="id6"></a>
## Documentation

* [CloudProviderRanker GitBook](https://www.gitbook.com/book/indigo-dc/cloud-provider-ranker/details) 

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
