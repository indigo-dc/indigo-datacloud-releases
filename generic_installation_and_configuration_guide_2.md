# Generic Installation and Configuration Guide - INDIGO-2

This chapter provides information on how to enable and use the INDIGO DataCloud software repositories hsoting the second major release INDIGO-2 (ElectricIndigo).

Summary
* [Installing the Operating Systems and Cloud  Management Frameworks](#id1)
  * [Operating Systems](id2)
  * [Cloud Management Frameworks](#id3)
* [Enable the INDIGO - DataCloud packages repositories](#id4)
  * [Giving INDIGO - DataCloud  repositories precedence over EPEL](#id5)
* [Enable the INDIGO - DataCloud Containers repositories](#id6)
* [Important note on automatic updates](#id7)

<a id="id1"></a>
## Installing the Operating Systems and Cloud  Management Frameworks 

<a id="id2"></a>
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
%
%
% #### Ubuntu 14.04
%
% 

% Information to install this operating system can be found at [http://releases.ubuntu.com/trusty/](http://releases.ubuntu.com/trusty/) and % or at [Ubuntu Community Installation Guide ](https://help.ubuntu.com/community/Installation) and regarding Docker Containers at [Ubuntu  Official Docker repository](https://hub.docker.com/_/ubuntu/).

#### Ubuntu 16.04

% For more information on Ubuntu please check: [http://www.ubuntu.com/](http://www.ubuntu.com/)

Information to install this operating system can be found at [http://releases.ubuntu.com/trusty/](http://releases.ubuntu.com/xenial/) and or at [Ubuntu Community Installation Guide ](https://help.ubuntu.com/community/Installation) and regarding Docker Containers at [Ubuntu Official Docker repository](https://hub.docker.com/_/ubuntu/).

<a id="id3"></a>
### Cloud Management Frameworks

#### OpenStack Newton

Please follow the official OpenStack Liberty Installation Guides:
* for [RedHat & CentOS](https://docs.openstack.org/newton/install-guide-rdo/)
  * Please enable the use of Newton RDO repository by using:</br>
  ```$ sudo yum install -y https://repos.fedorapeople.org/openstack/openstack-newton/rdo-release-newton-4.noarch.rpm```</br>
  
* for [Ubuntu 16.04](https://docs.openstack.org/newton/install-guide-ubuntu/)
  * Please enable the use of Newton CloudArchive by using:<br>
  ```$ sudo add-apt-repository cloud-archive:newton```

#### OpenNebula 4.14 & 5.2.X

Please follow the official [OpenNebula 4.14 Installation Guide for CentOS & Ubuntu](http://docs.opennebula.org/4.14/design_and_installation/building_your_cloud/ignc.html) or [OpenNebula 5.X Installation Guide for CentOS & Ubuntu](http://docs.opennebula.org/5.0/deployment/index.html)



<a id="id4"></a>
## Enable the INDIGO - DataCloud packages repositories

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

* for CentOS7 save the key under */etc/pki/rpm-gpg/* <br>
```# rpm --import http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc```

* for Ubuntu: <br>
```# wget -q   -O - http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc | sudo apt-key add -```

<a id="id5"></a>
### Giving INDIGO - DataCloud  repositories precedence over EPEL

It is strongly recommended that INDIGO repositories take precedence over EPEL when installing and upgrading packages.
For manual configuration:
* you must install the **yum-priorities**** plugin and ensure that its configuration file, */etc/yum/pluginconf.d/priorities.conf* is as follows:<br>
```[ main ]```<br>
```enabled = 1```<br>
```check_obsoletes = 1```

For automatic configuration:
* we strongly recommend the use of **indigodc-release** package. Please follow the instructions given bellow on what version of the package to use, how to get and install it.

#### Configuring the use of INDIGO - DataCloud repositories

INDIGO-2 production repositories are available at:
* [http://repo.indigo-datacloud.eu/repository/indigo/2/](http://repo.indigo-datacloud.eu/repository/indigo/12)

YUM & APT configuration files are available at:
* CentOS7 - [http://repo.indigo-datacloud.eu/repos/2/indigo2.repo](http://repo.indigo-datacloud.eu/repos/2/indigo2.repo)
* Ubuntu 16.04 - [http://repo.indigo-datacloud.eu/repos/2/indigo2-ubuntu16_04.list](http://repo.indigo-datacloud.eu/repos/2/indigo2-ubuntu16_04.list) 

Install INDIGO - DataCloud repositories :
* CentOS7: <br>
```wget http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/indigodc-release-2.0.0-1.el7.centos.noarch.rpm```<br>
```yum localinstall -y indigodc-release-2.0.0-1.el7.centos.noarch.rpm``` 

* Ubuntu 16.04:<br>
```wget http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/indigodc-release_2.0.0-1_amd64.deb```<br>
```dpkg -i indigodc-release_2.0.0-1_amd64.deb``` 

These packages will install required dependencies, the INDIGO - DataCloud public key and ensures the precedence of INDIGO - DataCloud repositories over EPEL and Ubuntu. 

It is strongly recommended the use of the latest version of the **indigodc-release** package containing the public key and the YUM and APT repository files.

<a id="id6"></a>
## Enable the INDIGO - DataCloud Containers repositories

On the [DockerHub Registry](https://hub.docker.com/), INDIGO - DataCloud has organized the repositories under two Organizations:
* [indigodatacloud](https://hub.docker.com/u/indigodatacloud/), for Core Services
* [indigodatacloudapps](https://hub.docker.com/u/indigodatacloudapps/), for Applications
Containers present in those repositories and released in INDIGO-2 are tagged with "*indigo_2*" tag and signed, leveraging the [Docker’s trust features](https://docs.docker.com/engine/security/) so that users can pull trusted images.

Currently, content trust is disabled by default. You must enable it by setting the **DOCKER_CONTENT_TRUST** environment variable, like bellow:

```export DOCKER_CONTENT_TRUST=1```

For more details regarding the "Content Trust in Docker" please read [Docker's Documentation](https://docs.docker.com/engine/security/trust/content_trust/)

Content trust is associated with the TAG portion of an image.
For INDIGO-2 (ElectricIndigo) release the signed tag is ***indigo_2***. See example bellow if you want to ensure the correct use of INDIGO - DataCloud images:
* for Core Services

```
$ export DOCKER_CONTENT_TRUST=1
$ docker pull indigodatacloud/orchestrator:1.3.0-FINAL
No trust data for 1.3.0-FINAL
$ docker pull indigodatacloud/orchestrator:indigo_2
Pull (1 of 1): indigodatacloud/orchestrator:indigo_2@sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be
sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be: Pulling from indigodatacloud/orchestrator
93857f76ae30: Pull complete
[...]
e8c92b40b492: Pull complete
Digest: sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be
Status: Downloaded newer image for indigodatacloud/orchestrator@sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be
Tagging indigodatacloud/orchestrator@sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be as indigodatacloud/orchestrator:indigo_2
$ docker images
REPOSITORY                     TAG                 IMAGE ID            CREATED             SIZE
indigodatacloud/orchestrator   indigo_2            bdbe758d9f32        37 hours ago        843MB
```

* for Applications:

```
$ export DOCKER_CONTENT_TRUST=1
$ docker pull indigodatacloudapps/ophidia-all:latest
No trust data for latest
$ docker pull indigodatacloudapps/ophidia-all:indigo_2
Pull (1 of 1): indigodatacloudapps/ophidia-all:indigo_2@sha256:64df8c1f1103984536c28662baf2cc8da3dd3135e3b20f77335a73802d26e482
sha256:64df8c1f1103984536c28662baf2cc8da3dd3135e3b20f77335a73802d26e482: Pulling from indigodatacloudapps/ophidia-all
45a2e645736c: Pull complete
[...]
686a6aef9fe7: Pull complete
Digest: sha256:64df8c1f1103984536c28662baf2cc8da3dd3135e3b20f77335a73802d26e482
Status: Downloaded newer image for indigodatacloudapps/ophidia-all@sha256:64df8c1f1103984536c28662baf2cc8da3dd3135e3b20f77335a73802d26e482
Tagging indigodatacloudapps/ophidia-all@sha256:64df8c1f1103984536c28662baf2cc8da3dd3135e3b20f77335a73802d26e482 as indigodatacloudapps/ophidia-all:indigo2_
$ docker images |grep amber
indigodatacloudapps/ambertools             indigo_1            6c47a81b761d        11 days ago         1.826 GB
```

<a id="id7"></a>
## Important note on automatic updates 

The CentOS and Ubuntu Operating Systems both offer auto-updates mechanisms. Sometimes middleware updates require non-trivial configuration changes or a reconfiguration of the service. This could involve service restarts, new configuration files, etc, which makes it difficult to ensure that automatic updates will not break a service. Thus

**WE STRONGLY RECOMMEND NOT TO USE AUTOMATIC UPDATE PROCEDURE OF ANY KIND**

on the INDIGO - DataCloud  repositories (you can keep it turned on for the OS). You should read the update information provides by each service and do the upgrade manually when an update has been released! 






