# First Update of INDIGO-2

The First Update of INDIGO-2 release contains:
* [LiferayPlugings v. 2.0.2](#lp)
* [INDIGO Kepler v. 1.1.1](#ik)

## <a name="li"></a>LiferayIAM v. 2.0.2

#### What's new
* The update fixes some bugs found in the second version of the LiferayPlugins package.

#### List of RfCs
* [Issue-3](https://github.com/indigo-dc/LiferayPlugins/issues/3) - Javascript load error
* [Issue-4](https://github.com/indigo-dc/LiferayPlugins/issues/4) - Version mismatch
* [Issue-7](https://github.com/indigo-dc/LiferayPlugins/issues/7) - Resource details error
* [Issue-8](https://github.com/indigo-dc/LiferayPlugins/issues/8) - Upload files for new application
* [Issue-10](https://github.com/indigo-dc/LiferayPlugins/issues/10) - offline_access not always requested

#### Installation & Configuration
* Documentation on update/upgrade available on gitbook. The artifcat have to be deployed on Liferay
and old versions disabled/removed following Liferay plugin deployment guidelines.
* More details here: https://indigo-dc.gitbooks.io/liferay-plugins/content/doc/service_reference.html

#### Artefacts
* CentOS 7
  * [LiferayPlugins-binary-2.0.2.tgz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/LiferayPlugins-binary-2.0.2.tgz)
* Ubuntu14.04
  * [LiferayPlugins-binary-2.0.2.tgz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/LiferayPlugins-binary-2.0.2.tgz)

## <a name="ik"></a>Indigo-Kepler v 1.1.1

#### What's new
* This minor update of INDIGO-Kepler is an adaptation to the latest changes in FutureGateway.
* New versions of the artifacts:
  * indigoclient v1.1.1 https://github.com/indigo-dc/indigoclient/releases/tag/v1.1.1
  * indigokepler v1.1.1 https://github.com/indigo-dc/indigokepler/releases/tag/v1.1.1
  * Ansible role for 'kepler' Docker image https://github.com/indigo-dc/ansible-role-kepler/releases/tag/v1.1.1
  * Ansible role for 'kepler-batch' Docker image https://github.com/indigo-dc/ansible-role-kepler-batch/releases/tag/v1.1.1

#### List of RfCs
* [Issue #24](https://github.com/indigo-dc/ansible-role-kepler/issues/24) - Including init.sh in the execution of the role
* Authorization header was missing for PATCH calls to the FutureGateway
* [Issue #50](https://github.com/indigo-dc/fgAPIServer/issues/50) - "Wrong parameter in Applications". The issue was created for fgAPIServer component, but it affects INDIGO-Kepler as well 

#### Installation & Configuration
In order to update the packages please use:
* The Ansible role is deployed in Ansible Galaxy as indigo-dc/kepler and so the usual steps are required:<br>
  ``` ansible-galaxy install indigo-dc.kepler```<br>
  ``` ansible-playbook /etc/ansible/roles/indigo-dc.kepler/tests/kepler.yml```<br>
* The Docker image is available in Docker Hub as indigodatacloudapps/kepler so the usual steps are required:<br>
  ``` docker pull indigodatacloudapps/kepler```<br>
  ``` docker run -it -p 5900:5900 indigodatacloudapps/kepler```<br>

#### Artefacts
* CentOS7 source tarballs
  * [indigoclient-1.1.1.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/indigoclient-1.1.1.tar.gz)
  * [indigokepler-1.1.1.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/indigokepler-1.1.1.tar.gz) 

* Ubuntu14.04 source tarballs
  * [indigoclient-1.1.1.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/xenial-updates/main/source/indigoclient-1.1.1.tar.gz)
  * [indigokepler-1.1.1.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/xenial-updates/main/source/indigokepler-1.1.1.tar.gz) 

* Container
  * [indigodatacloudapps/kepler:indigo_2](https://hub.docker.com/r/indigodatacloudapps/kepler/tags/)
