# Generic Installation and Configuration Guide

This chapter provides information on how to enable and use the INDIGO DataCloud software repositories.


## Installing the Operating Systems and Cloud  Management Frameworks 

### Operating Systems

#### CentOS 7 

For more information on CentOS please check: [https://www.centos.org/](https://www.centos.org/)

All the information to install this operating system can be found at https://wwwhttps://www.centos.org/download/[](https://www.centos.org/download/)

You will find there information on CentOS [packages](http://mirror.centos.org/centos/7/) and [Docker Containers](https://hub.docker.com/_/centos/).

##### The EPEL repository
If not present by default on your nodes, you should enable the EPEL repository (https://fedoraproject.org/wiki/EPEL)

EPEL has an 'epel-release' package that includes gpg keys for package signing and repository information. Installing the latest version of epel-release package available on EPEL7 repositories like:
* [http://download.fedoraproject.org/pub/epel/7/x86_64/e/](http://download.fedoraproject.org/pub/epel/7/x86_64/e/) 

allows you to use normal tools, such as **yum**, to install packages and their dependencies. By default the stable EPEL repo should be enabled.

#### Ubuntu 14.04

For more information on Ubuntu please check: [http://www.ubuntu.com/](http://www.ubuntu.com/)

Information to install this operating system can be found at [http://releases.ubuntu.com/trusty/](http://releases.ubuntu.com/trusty/) and or at [Ubuntu Community Installation Guide ](https://help.ubuntu.com/community/Installation) and regarding Docker Containers at [Ubuntu Official Docker repository](https://hub.docker.com/_/ubuntu/).

## Enable the INDIGO - DataCloud repositories

INDIGO - DataCloud products are distributed from standard OS repositories and DockerHub registry. 

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

All packages are signed with the INDIGO - DataCloud gpg key. The public key can be downloaded from [here](http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc), and the fingerprint from [here](http://repo.indigo-datacloud.eu/repository/INDIGODC_key_fingerprint.asc). Please import the key **BEFORE** starting! 

* for CentOS7 save the key under */etc/pki/rpm-gpg/* 
```# rpm --import http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc```

* for Ubuntu: 
```# wget -q   -O - http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc | sudo apt-key add -```

### Giving INDIGO - DataCloud  repositories precedence over EPEL

It is strongly recommended that INDIGO repositories take precedence over EPEL when installing and upgrading packages.
For manual configuration:
* you must install the **yum-priorities**** plugin and ensure that its configuration file, */etc/yum/pluginconf.d/priorities.conf* is as follows:
```[main]
enabled = 1
check_obsoletes = 1```

For automatic configuration:
* we strongly recommend the use of **indigodc-release** package. Please follow the instructions given bellow on what version of the package, how to get and install it.

#### Configuring the use of INDIGO - DataCloud repositories

INDIGO-1 production repositories are available at:
* http://repo.indigo-datacloud.eu/repository/indigo/1/ 

YUM & APT configuration files are available at:
* CentOS7 - [http://repo.indigo-datacloud.eu/repos/1/indigo1.repo](http://repo.indigo-datacloud.eu/repos/1/indigo1.repo)
* Ubuntu 14.04 - [http://repo.indigo-datacloud.eu/repos/1/indigo1-ubuntu14_04.list](http://repo.indigo-datacloud.eu/repos/1/indigo1-ubuntu14_04.list) 

Install INDIGO - DataCloud repositories :
* CentOS7: 

```yum install http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/base/indigodc-release-1.0.0-1.el7.centos.noarch.rpm``` 

* Ubuntu 14.04:

```wget http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/main/binary-amd64/indigodc-release_1.0.0-1_amd64.deb

dpkg -i indigodc-release_1.0.0-1_amd64.deb``` 

These packages will install required dependencies, the INDIGO - DataCloud public key and ensures the precedence of INDIGO - DataCloud repositories over EPEL and Ubuntu. 

It is strongly recommended the use of the latest version of the **indigodc-release** package containing the public key and the YUM and APT repository files.

On the [DockerHub Registry](https://hub.docker.com/), INDIGO - DataCloud has organized the repositories under two Organizations:
* [indigodatacloud](https://hub.docker.com/u/indigodatacloud/), for Core Services
* [indigodatacloudapps](https://hub.docker.com/u/indigodatacloudapps/), for Applications
Containers present in those repositories and released in INDIGO-1 are tagged with "*indigo-1*" tag and signed, leveraging the [Docker’s trust features](https://docs.docker.com/engine/security/) so that users can pull trusted images.

## Important note on automatic updates 

The CentOS and Ubuntu Operating Systems both offer auto-updates mechanisms. Sometimes middleware updates require non-trivial configuration changes or a reconfiguration of the service. This could involve service restarts, new configuration files, etc, which makes it difficult to ensure that automatic updates will not break a service. Thus

**WE STRONGLY RECOMMEND NOT TO USE AUTOMATIC UPDATE PROCEDURE OF ANY KIND**

on the INDIGO - DataCloud  repositories (you can keep it turned on for the OS). You should read the update information provides by each service and do the upgrade manually when an update has been released! 






