# INDIGO-2 ElectricIndigo

The [INDIGO-DataCloud](https://www.indigo-datacloud.eu/) is delighted to announce ElectricIndigo, the second and final major release of the project,. ElectricIndigo will be presented and demonstrated through several use cases at the [INDIGO Summit 2017, 9-12/5/2017](https://www.indigo-datacloud.eu/news/indigo-summit-2017-9-12-may-2017-catania-italy).
 
**ElectricIndigo** builds and expands on the first version of the software generated  by the project, called MidnightBlue, In this respect, it enhances  **stability**, adding more **programmability, scalability, automation and flexible network management**, to help resource providers and scientific communities address challenging problems and deliver new services.


<table> 
<tr><td><img src="Picture1_indigo2.png"/></td>
<td><b>Application-level Interfaces for Cloud Providers and Automated Service Composition</b></br>Easily port applications to public and private Clouds using open programmable interfaces, user-level containers, and standards-based languages to automate definition, composition and instantiation of complex set-ups.</td>
</tr>
<tr><td><b>Flexible Identity and Access Management</b></br>
Manage access and policies to distributed resources using multiple methods such as OpenID-Connect, SAML, X.509 digital certificates, through programmable interfaces and web front-ends.</td>
<td><img src="Picture2_indigo2.png"/></td>
</tr>
<tr><td><img src="Picture3_indigo2.png"/>
</td>
<td><b>Data Management and Data Analytics Solutions</b></br>
Distribute and access data through multiple providers via virtual file systems and automated replication and caching, exploiting scalable, high-performance data mining and analytics.
</td>
</tr>
<tr><td><b>Programmable Web Portals, Mobile Applications</b></br>
Create and interface web portals or mobile apps, exploiting distributed data as well as compute resources located in public and private Cloud infrastructures.
</td>
<td><img src="Picture4_indigo2.png"/></td>
</tr>
<tr><td><img src="Picture5_indigo2.png"/>
</td>
<td><b>Enhanced and Scalable Services for Data Centers and Resource Providers</b></br>
Increase the efficiency of existing Cloud infrastructures based on OpenStack or OpenNebula through advanced scheduling, flexible cloud / batch management, network orchestration and interfacing of high-level Cloud services to existing storage systems.
</td>
</tr>
</table>

**New to ElectricIndigo:**
 
**ElectricIndigo** includes more than 40 modular components, distributed via 170 software packages and 50 ready-to-use Docker containers, adding the following new features to the previous INDIGO release:
* FairShare Scheduler for OpenNebula
* Network Orchestrator Wrapper (NOW) for Intra-site Networking Management in OpenNebula 
* Command Line Interface for submitting TOSCA Templates to the INDIGO PaaS
 
All the ElectricIndigo components support the CentOS 7 and Ubuntu 16.04 operating systems, as well as open source Cloud management frameworks such as OpenStack Newton and OpenNebula 5.X.
 
# Release Notes

The INDIGO-2 release consists in 43 Products divided in, mainly, Core Services, and Applications:
* 170 OS packages
  * 53 RPMS & SRPMS
  * 97 binary & source DEBS 
  * 20 binary & source tarballs
* 50 Docker containers
* 243 external/third-party dependencies

INDIGO-2 is fully supported
* on the following **Operating Systems** platforms:
  * **CentOS 7**
  * **Ubuntu 16.04**
  * Optionally PTs support also other OS platforms. You can find more information in the individual products documentation.
* on the following **CMFs (Cloud Management Framework)** versions:
  * **OpenStack v. Newton,** 
  * **OpenNebula v. 4.14**

You can find in the later chapters the full list of products, with detailed release notes and instructions for their installation/configuration. 


## Installation Notes 

All INDIGO - DataCloud products are distributed from standard OS repositories and DockerHub registry. 

The packages repositories have the following structure:
* INDIGO-DC **production** (stable): ```indigo/2/<platform>/<basearch>/{base|updates}```
  * stable and signed, well tested software components, recommended to be installed on production-sites
* Third-party: ```indigo/2/<platform>/<basearch>/third-party```
  * packages that are not part of INDIGO, or not part of the base OS or EPEL, but used as dependencies by other INDIGO components
* INDIGO-DC **testing**: ```indigo-testing/2/<platform>/<basearch>```
  * packages that will become part of the next stable distribution; in the certification and validation phase.
* INDIGO-DC **preview**: ```indigo-preview/2/<platform>/<basearch>```
  * signed packages that will become part of the next stable update, available for technical-previews

where
* ```<basearch>``` is currently: x86_64, SRPMS, tgz 
* ```<platform>``` is currently: centos7, ubuntu

All packages are signed with the INDIGO - DataCloud gpg key. The public key can be downloaded from [here](http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc), and the fingerprint from [here](http://repo.indigo-datacloud.eu/repository/INDIGODC_key_fingerprint.asc).

It is strongly recommended the use of the lastest version of the **indigodc-release** package containing the public key and the YUM and APT repository files.

On the [DockerHub Registry](https://hub.docker.com/), INDIGO - DataCloud has organized the repositories under two Organizations:
* [indigodatacloud](https://hub.docker.com/u/indigodatacloud/), for Core Services
* [indigodatacloudapps](https://hub.docker.com/u/indigodatacloudapps/), for Applications
Containers present in those repositories and released in INDIGO-2 are tagged with "*indigo-2*" tag and signed, leveraging the [Docker’s trust features](https://docs.docker.com/engine/security/) so that users can pull trusted images.

To understand how to install and configure INDIGO-1 products either refer to the [Generic Installation & Configuration Guide](generic_installation_and_configuration_guide_1.md) chapter or to each individual product documentation.


## Software

INDIGO-2 software can be downloaded from [INDIGO DataCloud repositories](http://repo.indigo-datacloud.eu/).


## Documentation

Please find INDIGO-1 documentation [here](https://www.gitbook.com/@indigo-dc/)


## Support

Most complex software contains bugs, we are not an exception. One of the features of free and open source software is the ability to report bugs, helping to fix or improve the software you use.

INDIGO - DataCloud project uses the [GGUS (Global Grid User Support)](https://ggus.eu/) tool as its user support system. It provides sophisticated search functionality, report generation, interfaces to bug tracking systems used by different middleware components, and automatic ticket reminder including escalation indication.
Please use the **INDIGO - DataCloud Catch-All** GGUS Support Unit or directly  contact us through the [indigo-su@lists.indigo-datacloud.eu](https://lists.indigo-datacloud.eu/sympa/info/indigo-su) mailing-list.

More details regarding  each product support channels are provided in the respective products release pages.


Developers, researchers and IT enthusiasts: feel free to write to [info@indigo-datacloud.eu](info@indigo-datacloud.eu) to ask for more information on how to deploy your PaaS based solution for your work. For automatic notifications you can register to the [INDIGO-DataCloud RSS release feed](http://repo.indigo-datacloud.eu/INDIGODataCloudNews.rss.xml) or subscribe to the [INDIGO-DataCloud Announce Mailing list](https://lists.indigo-datacloud.eu/sympa/info/indigo-announce). You can also socialize with us via [Twitter](https://twitter.com/indigodatacloud), [Facebook](https://www.facebook.com/indigodatacloud/?ref=bookmarks) and join our [LinkedIn group](https://www.linkedin.com/groups/8416266). 

