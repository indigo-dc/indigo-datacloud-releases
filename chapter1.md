# INDIGO-1 MidnightBlue

**The [INDIGO-DataCloud](https://www.indigo-datacloud.eu/) project is pleased to announce the general availability of its first public software release, codenamed MidnightBlue.**

This release comes after an initial phase of requirement gatherings which involved several European scientific collaborations in areas as diverse as structural biology, earth sciences, physics, bioinformatics, cultural heritage, astrophysics, life sciences, climatology, etc. This resulted in the development of many software components addressing existing technical gaps linked to easy and optimal usage of distributed data and compute resources. These components are now released into a consistent and modular suite, offered as a contribution toward the definition and implementation of an efficient European Open Science Cloud.

The first INDIGO-DataCloud release provides **open source components** for:
* **DataCenter solutions**, allowing data and compute resource centers to increase efficiency and services for customers.
* **Data solutions**, offering advanced access to distributed data.
* **Automated solutions**, allowing users to easily specify and deploy complex data and compute resource requirements.
* **User-level solutions**, integrating scientific applications in programmable front-ends and in mobile applications.
* **Common solutions**, enableing the integration of all INDIGO components into a comprehensive Authentication and Authorization Architecture.

**Key technical highlights:**

**The DataCenter Solutions**. INDIGO is providing many new features/services for resource centers: 
* *Improved scheduling* for allocation of resources by the popular open source Cloud platforms. OpenStack and OpenNebula. This provides both better scheduling algorithms and support for spot-instances.
* Support for improved IaaS resource orchestration capabilities using standards  orchestration engines through the use of the TOSCA standard, for both OpenStack and OpenNebula.
* Improved QoS capabilities of storage resources for better support of high-level storage requirements, such as flexible allocation of disk or tape storage space and support for data life cycle.
* Improved and transparent support for Docker containers. This includes for example the introduction of native container support in OpenNebula. 

**The Data Services**. INDIGO provides a complete set of data-related features that includes: 
* Distributed Data Federation through several protocols, in order to support both legacy application and advanced standard interfaces such as CDMI or just simple web interfaces.
* The possibility to federate diverse storage technologies (such as Posix, Object Storage, CEPH, etc) in a seamless way, letting users exploit data and storage resources wherever they are available.

**Automated Solutions**. INDIGO provides a rich set of high-level automated functionalities. Some of the most innovative are: 
* Improved capabilities in the geographical exploitation of Cloud resources. End users need not know where resources are located, because the INDIGO PaaS layer hides the complexity of both scheduling and brokering.
* Standard interface to access PaaS services. INDIGO uses the TOSCA standard to hide the difference on the different way of implementing services at the PaaS level.
* Support for data requirements in Cloud resource allocations: computational resources can be requested and allocated where data is stored.
* Integrated use of resources coming from both public and private Cloud infrastructures.
* Deployment, monitoring and automatic scalability of existing applications.
* Integrated support for high-performance Big Data analytics.
* Support for dynamic and elastic clusters of resources. HTCondor, Torque and Mesos cluster are supported. 

**High-level user oriented services**. Researchers and data managers are able to access resources through: 
* Toolkits (libraries) allowing usage of the INDIGO platform from Scientific Gateways and desktop applications.
* An open source Mobile Application Toolkit for the iOS and Android platforms, serving as the base for the development of Mobile Apps.
* User-friendly front ends for building programmable, general-purpose multi-domain Science Gateways.

All the INDIGO components are integrated into a comprehensive **Authentication and Authorization Architecture**, with support for user authentication through multiple methods (SAML, OpenID Connect and X.509), support for distributed authorization policies and a Token Translation Service, creating credentials for services that do not natively support OpenID Connect.

The **INDIGO-DataCloud software** is [released](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/) under the Apache 2.0 software license and can be deployed on both public and private Cloud infrastructures. It can be downloaded from [http://repo.indigo-datacloud.eu](http://repo.indigo-datacloud.eu/).

**Stay tuned**. Updates and new releases of the INDIGO services are expected to come in the forthcoming months. If you want to be notified when a new release is out, [register here](https://www.indigo-datacloud.eu/user/register). The first scientific applications and use cases adopting this first INDIGO release are expected starting from September 2016.

**INDIGO-DataCloud** is an Horizon 2020 project funded by the European Commission from April 2015 to September 2017. It involves 26 European partners, including research institutes, scientific collaborations, software developers, universities, e-infrastructures, private companies. Its main goal is to provide software solutions for science addressing several of the technology gaps in Cloud and Data technologies currently experienced by resource providers and scientists working in either small or big collaborations.

For more information, see [https://www.indigo-datacloud.eu](https://www.indigo-datacloud.eu).  


# Release Notes

The INDIGO-1 release consists in 32 Products divided in, mainly, Core Services, and Applications:
* 167 OS packages
  * 41 RPMS & SRPMS
  * 96 binary & source DEBS 
  * 21 binary & source tarballs
* 40 Docker containers
* 41 external/third-party dependencies

INDIGO-1 is fully supported
* on the following **Operating Systems** platforms:
  * **CentOS 7**
  * **Ubuntu 14.04**
  * Optionally PTs support also other OS platforms. You can find more information in the individual products documentation.
* on the following **CMFs (Cloud Management Framework)** versions:
  * **OpenStack v. Liberty,** with the exception of the "TOSCA in HEAT" (heat-translator), product, for which Mitaka HEAT must be used.
  * **OpenNebula v. 4.14**

You can find in the later chapters the full list of products, with detailed release notes and instructions for their installation/configuration. 


## Installation Notes 

All INDIGO - DataCloud products are distributed from standard OS repositories and DockerHub registry. 

The packages repositories have the following structure:
* INDIGO-DC **production** (stable): ```indigo/{1,2}/<platform>/<basearch>/{base|updates}```
  * stable and signed, well tested software components, recommended to be installed on production-sites
* Third-party: ```indigo/{1,2}/<platform>/<basearch>/third-party```
  * packages that are not part of INDIGO, or not part of the base OS or EPEL, but used as dependencies by other INDIGO components
* INDIGO-DC **testing**: ```indigo-testing/{1,2}/<platform>/<basearch>```
  * packages that will become part of the next stable distribution; in the certification and validation phase.
* INDIGO-DC **preview**: ```indigo-preview/{1,2}/<platform>/<basearch>```
  * signed packages that will become part of the next stable update, available for technical-previews

where
* ```<basearch>``` is currently: x86_64, SRPMS, tgz 
* ```<platform>``` is currently: centos7, ubuntu

All packages are signed with the INDIGO - DataCloud gpg key. The public key can be downloaded from [here](http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc), and the fingerprint from [here](http://repo.indigo-datacloud.eu/repository/INDIGODC_key_fingerprint.asc).

It is strongly recommended the use of the lastest version of the **indigodc-release** package containing the public key and the YUM and APT repository files.

On the [DockerHub Registry](https://hub.docker.com/), INDIGO - DataCloud has organized the repositories under two Organizations:
* [indigodatacloud](https://hub.docker.com/u/indigodatacloud/), for Core Services
* [indigodatacloudapps](https://hub.docker.com/u/indigodatacloudapps/), for Applications
Containers present in those repositories and released in INDIGO-1 are tagged with "*indigo-1*" tag and signed, leveraging the [Docker’s trust features](https://docs.docker.com/engine/security/) so that users can pull trusted images.

To understand how to install and configure INDIGO-1 products either refer to the [Generic Installation & Configuration Guide](generic_installation_and_configuration_guide_1.md) chapter or to each individual product documentation.


## Software

INDIGO-1 software can be downloaded from [INDIGO DataCloud repositories](http://repo.indigo-datacloud.eu/).


## Documentation

Please find INDIGO-1 documentation [here](https://www.gitbook.com/@indigo-dc/)


## Support

Most complex software contains bugs, we are not an exception. One of the features of free and open source software is the ability to report bugs, helping to fix or improve the software you use.

INDIGO - DataCloud project uses the [GGUS (Global Grid User Support)](https://ggus.eu/) tool as its user support system. It provides sophisticated search functionality, report generation, interfaces to bug tracking systems used by different middleware components, and automatic ticket reminder including escalation indication.
Please use the **INDIGO - DataCloud Catch-All** GGUS Support Unit or directly  contact us through the [indigo-su@lists.indigo-datacloud.eu](https://lists.indigo-datacloud.eu/sympa/info/indigo-su) mailing-list.

More details regarding  each product support channels are provided in the respective products release pages.


Developers, researchers and IT enthusiasts: feel free to write to [info@indigo-datacloud.eu](info@indigo-datacloud.eu) to ask for more information on how to deploy your PaaS based solution for your work. For automatic notifications you can register to the [INDIGO-DataCloud RSS release feed](http://repo.indigo-datacloud.eu/INDIGODataCloudNews.rss.xml) or subscribe to the [INDIGO-DataCloud Announce Mailing list](https://lists.indigo-datacloud.eu/sympa/info/indigo-announce). You can also socialize with us via [Twitter](https://twitter.com/indigodatacloud), [Facebook](https://www.facebook.com/indigodatacloud/?ref=bookmarks) and join our [LinkedIn group](https://www.linkedin.com/groups/8416266). 
