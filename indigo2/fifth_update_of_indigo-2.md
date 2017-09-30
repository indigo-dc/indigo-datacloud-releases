# Fifth Update of INDIGO-2 - 30/09/2017

The Fourth Update of INDIGO-2 release contains:
* [Accounting v. 1.5.0-1](#accounting)
* [CloudProviderRanker v. 0.6.0](#cpr)
* [IAM v. 1.0.0](#iam)
* [INDIGO-Kepler v. 1.3](#kepler)
* [Liferay Plugins v. 2.1.0](#lp)
* [Orchent v. 1.1.0](#orchent)
* [OOI v. 1.2.0](#ooi)
* [Synergy: Service v. 1.5.2 & Scheduler-Manager v. 2.5.0](#synergy)
* [WaTTs v. 1.2.0](#watts)


## <a name="cmdb"></a>Accounting (APEL) v. 1.5.0-1 

#### What's new
* New Features and Minor Changes
  * Add token introspection and Caching: https://github.com/apel/rest/pull/37
  * Add files to enable ansible deployment: https://github.com/apel/rest/pull/43
* Patches and Bug Fixes
  * GET Test Case Refactor: https://github.com/apel/rest/pull/35
  * POST Test Case Refactor: https://github.com/apel/rest/pull/36
  * Add branch coverage to coveralls check: https://github.com/apel/rest/pull/39
  * Upgrade base Docker image to CentOS7: https://github.com/apel/rest/pull/40
  * Update documentation in docker/README.md: https://github.com/apel/rest/pull/41
  * Update Partition range for new deployments: https://github.com/apel/rest/pull/42
  * Improve documentation following second round of 'Early Adopter' testing: https://github.com/apel/rest/pull/44

#### Installation & Configuration
* https://github.com/indigo-dc/Accounting/blob/1.5.0-1/README.md
* https://github.com/indigo-dc/Accounting/tree/1.5.0-1/doc

Upgrading an already deployed instance
* https://github.com/indigo-dc/Accounting/blob/1.5.0-1/doc/admin.md#how-to-update-an-already-deployed-service-to-150-from-140

#### Artefacts
* [indigodatacloud/accounting:indigo_2](https://hub.docker.com/r/indigodatacloud/accounting/tags) - CentOS7 based image

## <a name="kepler"></a>Indigo-Kepler v 1.3

#### What's new
* A CLI client built on top of existing library to communicate with FutureGateway. It allows to submit & monitor tasks, upload & download files and query for available applications

#### List of RfCs
* A CLI client exposing basic FutureGateway functionality to the command line
* Updated workflows and scripts to support ENES use case
* Fixed a bug with incorrect handling of timezone offset when parsing timestamps

#### Installation & Configuration
How to update: use provided Docker images versioned equally to the main libraries.

#### Artefacts

* Sources
  * https://github.com/indigo-dc/indigoclient/releases/tag/v1.3
  * https://github.com/indigo-dc/indigokepler/releases/tag/v1.3
* Ansible role indigo-dc/kepler v1.3 pushed to Ansiible Galaxy
* Ansible role indigo-dc/kepler-batch v1.3 pushed to Ansible Galaxy
* Docker image indigodatacloudapps/kepler:1.3 pushed to Docker Hub
* Docker image indigodatacloudapps/kepler-batch:1.3 pushed to Docker Hub


* CentOS7 source tarballs
  * [indigoclient-v1.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/indigoclient-v1.3.tar.gz)
  * [indigokepler-v1.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/indigokepler-v1.3.tar.gz) 

* Ubuntu16.04 source tarballs
  * [indigoclient-v1.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/indigoclient-v1.3.tar.gz)
  * [indigokepler-v1.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/indigokepler-v1.3.tar.gz) 

* Container
  * [indigodatacloudapps/kepler:indigo_2](https://hub.docker.com/r/indigodatacloudapps/kepler/tags/)
  * [indigodatacloudapps/kepler-batch:indigo_2](https://hub.docker.com/r/indigodatacloudapps/kepler-batch/tags/)

* Container
  * [indigodatacloudapps/kepler:indigo_2](https://hub.docker.com/r/indigodatacloudapps/kepler/tags/)
  * [indigodatacloudapps/kepler-batch:indigo_2](https://hub.docker.com/r/indigodatacloudapps/kepler-batch/tags/)

