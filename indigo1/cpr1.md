# CloudProviderRanker v. 0.4.2-1

**CloudProviderRanker** is a standalone REST WEB Service which ranks cloud providers basing on rules implemented with the [Drools framework]( http://drools.org/)

**Summary**:
* [Release Notes](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [Documentation](#id6)
  * [List of Artifacts](#id7)
  * [Support](#id8)


<a id="id1"></a>
## Release Notes

<a id="id2"></a>
### What's new

This is the first release of the service offering
* Experimental basic ranking algorithm
  * ranking based, first of all, on user's priorities then based on monitoring data if missing priorities
* support for plain and SSL http connection
* zero configuration stand alone http server (no tomcat/JBoss container required)
* embedded jar file provided (all dependencies, but JDK, are included in the provided jar)
* required JDK >= 1.8.0 (resolved as dependency by package installation)
* Dockerfile for container build
* yaml file for deployment in Kubernetes cluster

Supported platforms
* Any Linux operating system supporting JRE >= 1.8 (CentOS, Ubuntu, etc.)

<a id="id3"></a>
#### List of RfCs 
* N/A

<a id="id4"></a>
### Deployment Notes
* Provided RPM and DEB packages.
* Both provide */etc/init.d/cloudproviderranker start/stop* script. 
* Installation of RPM also starts the service; de-installation stops the service

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](generic_installation_and_configuration_guide_1.md):
* On CentOS 7 <br>
  ```$ yum clean all```<br>
  ```$ yum install tts```

* On Ubuntu 14.04 - after setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](generic_installation_and_configuration_guide_1.md):<br>
  ```$ apt-get update```<br>
  ```$ apt-get install tts```

* More details regarding the installation and **configuration** can be found in the [TTS Deployment And Administration Guide](https://indigo-dc.gitbooks.io/token-translation-service/content/admin.html)

<a id="id5"></a>
### Known Issues
* N/A

<a id="id6"></a>
### Documentation

* [CloudProviderRanker GitBook](https://www.gitbook.com/book/indigo-dc/cloud-provider-ranker/details) 

<a id="id7"></a>
### List of Artifacts
Packages
* CloudProviderRanker-0.4.2-1.deb
* CloudProviderRanker-0.4.2-1_1.noarch.rpm

Docker Container
* [indigodatacloud/cloudproviderranker:indigo_1](https://hub.docker.com/r/indigodatacloud/cloudproviderranker/)

<a id="id8"></a>
### Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
