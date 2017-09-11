# Fourth Update of INDIGO-2 - 01/09/2017

The Fourth Update of INDIGO-2 release contains:
* [Accounting v. 1.4.0-1](#accounting)
* [CloudProviderRanker v. 0.6.0](#cpr)
* [IAM v. 1.0.0](#iam)
* [INDIGO-Kepler v. 1.2](#kepler)
* [Liferay Plugins v. 2.1.0](#lp)
* [Orchent v. 1.1.0](#orchent)
* [OOI v. 1.2.0](#ooi)
* [Synergy: Service v. 1.5.2 & Scheduler-Manager v. 2.5.0](#synergy)
* [WaTTs v. 1.2.0](#watts)


## <a name="cmdb"></a>Accounting (APEL) v. 1.4.0-1 

#### What's new
* Minor Changes:
  * Split the APEL REST Interface and APEL Server into two containers and use docker-compose to deploy: https://github.com/apel/rest/pull/31
  * Refactor test POST code into a single method that is called several times: https://github.com/apel/rest/pull/33
  * Fix a bug in the sender.py script: https://github.com/apel/rest/pull/34

* Bug Fixes:
  * Remove coveralls from the Docker Image: https://github.com/apel/rest/pull/38

#### Installation & Configuration
* Please read - [How to update an already deployed service from v. 1.3.2 to v. 1.4.0](https://github.com/indigo-dc/Accounting/blob/master/doc/admin.md#how-to-update-an-already-deployed-service-to-140-from-132)
* For more details please see [Instalation & Configuration Guide](https://indigo-dc.gitbooks.io/accounting/content/)

#### Artefacts
* [indigodatacloud/accounting:indigo_2](https://hub.docker.com/r/indigodatacloud/accounting/tags) - CentOS7 based image


## <a name="cpr"></a>CloudProviderRanker v. 0.6.0

#### What's new
* Added support to customize SLA ranking rules.

#### List of RfCs
* [Issue #23](https://github.com/indigo-dc/CloudProviderRanker/issues/23) - updated Dockerfile
- [Issue #24](https://github.com/indigo-dc/CloudProviderRanker/issues/24) - Make SLA targets ranking expression customizable
- [Issue #25](https://github.com/indigo-dc/CloudProviderRanker/issues/25) - Docker container is based on a deprecated image
- [Issue #26](https://github.com/indigo-dc/CloudProviderRanker/issues/26) - Add a CLI option parser
- [Issue #39](https://github.com/indigo-dc/CloudProviderRanker/issues/39) - Update documentation
- updated kubernetes template

#### Installation & Configuration
* Please read the updated documentation [CloudProviderRanker Guide](https://indigo-dc.gitbooks.io/cloud-provider-ranker/content/?q=)

#### Artefacts
* [indigodatacloud/cloudproviderranker:indigo_2](https://hub.docker.com/r/indigodatacloud/cloudproviderranker/tags)


## <a name="iam"></a>INDIGO IAM v. 1.0.0

#### What's new
This release provides improvements, bug fixes and new features:
* IAM now supports hierarchical groups. The SCIM group management API has been extended to support nested group creation and listing, and the IAM dashboard can now leverage these new API functions
* IAM now supports native X.509 authentication and the ability to link/unlink X.509 certificates to a user membership
* IAM now supports configurable on-demand account provisioning for trusted SAML IDPs; this means that the IAM can be configured to automatically on-board users from a trusted IdP/federation after a succesfull external authentication (i.e. no former registration or administration approval is required to on-board users)
* IAM now provides an enhanced token management and revocation API that can be used by IAM administrators to see and revoke active tokens in the system
* Account linking can be now be disabled via a configuration option
* IAM dashboard now correctly displays valid active access tokens for a user
* A problem that caused IAM registration access tokens to expire after the first use has been fixed
* IAM now provides an endpoint than can be used to monitor the service connectivity to external service (ie. Google)
* Improved SAML metadata handling and reloading
* The IAM audit log now provides fine-grained information for many events
* The IAM token introspection endpoint now correctly supports HTTP form authentication
* Notes in registration requests are now required to make life easier for VO administrators that wants to understand the reason for a registration request
* Password reset emails now contain the username of the user that has requested the password reset
* A stronger SAML account linking logic is now in place
* Starting from this release, we provide RPM and Deb packages and a puppet module to configure the IAM service
* The spring-boot dependency has been updated to version 1.3.8.RELEASE
* An issue that prevented access to the token revocation endpoint has been fixed

More details:
* https://github.com/indigo-iam/iam/releases/tag/v1.0.0

Supported Platforms:
* The **IAM** service is currently distributed as a docker image from Dockerhub, so in order to run the service, you will need Docker v. 1.11.1 or greater. If you want to use docker-compose to deploy the service, you will also need docker-compose v.1.7.0 or greater.

#### List of RfCs

* Milestone v1.0.0 on github:
  * https://github.com/indigo-iam/iam/milestone/3?closed=1

#### Installation & Configuration

<!--
* *How to upgrade already deployed service*:
  * If you've followed the gitbook guide (https://indigo-dc.gitbooks.io/iam/content/doc/admin.html), you could do as follows:</br>
```docker pull indigodatacloud/iam-login-service```</br>
```docker stop iam-login-service```</br>
```docker rm iam-login-service```</br>
```docker run \```</br>
```  --name iam-login-service --net=iam -p 8080:8080 \```</br>
```  --env-file=/path/to/iam-login-service/env \```</br>
```   -v /path/to/keystore.jks:/keystore.jks:ro \```</br>
```  indigodatacloud/iam-login-service```</br>
-->

* *Service Reference*
  * IAM gitbook: https://indigo-dc.gitbooks.io/iam/content/doc/admin.html

* Please read the [Deployment and Administration guide](https://indigo-dc.gitbooks.io/iam/content/doc/admin.html)

<a id="id7"></a>
#### Artefacts
* CentOS7
  * [iam-login-service-1.0.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/iam-login-service-1.0.0-1.el7.centos.noarch.rpm)
* Ubuntu16.04
  * [iam-login-service_1.0.0-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/iam-login-service_1.0.0-1_all.deb)
  
* Docker Container:
  * [indigodatacloud/iam-login-service:indigo_2](https://hub.docker.com/r/indigodatacloud/iam-login-service/tags)


## <a name="ik"></a>Indigo-Kepler v1.2

#### What's new
* Added mechanism to refresh an IAM token. It is used internally by every Kepler actor which communicates with FutureGateway, so that the workflow continues execution even after the original token expires.

#### List of RfCs
* [Issue #7](https://github.com/indigo-dc/indigokepler/issues/7) - Support OpenID

#### Installation & Configuration
The changes are internal to every Kepler actor. User switching to v1.2 does not need to do any changes in Kepler workflows created with prior version of the module.

#### Artefacts
* Sources
  * https://github.com/indigo-dc/indigoclient/releases/tag/v1.2
  * https://github.com/indigo-dc/indigokepler/releases/tag/v1.2
  * Ansible role for VM/Docker with VNC (also released in Ansible Galaxy and Docker Hub with v1.2 tag)
    * https://github.com/indigo-dc/ansible-role-kepler/releases/tag/v1.2
  * Ansible role for VM/Docker in a batch, non-GUI version (also released in Ansible Galaxy and Docker Hub with v1.2 tag)
    * https://github.com/indigo-dc/ansible-role-kepler-batch/releases/tag/v1.2


* CentOS7 source tarballs
  * [indigoclient-v1.2.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/indigoclient-v1.2.tar.gz)
  * [indigokepler-v1.2.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/indigokepler-v1.2.tar.gz) 

* Ubuntu16.04 source tarballs
  * [indigoclient-v1.2.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/indigoclient-v1.2.tar.gz)
  * [indigokepler-v1.2.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/indigokepler-v1.2.tar.gz) 

* Container
  * [indigodatacloudapps/kepler:indigo_2](https://hub.docker.com/r/indigodatacloudapps/kepler/tags/)
  * [indigodatacloudapps/kepler-batch:indigo_2](https://hub.docker.com/r/indigodatacloudapps/kepler-batch/tags/)


## <a name="lp"></a>LiferayPlugIns v. 2.1.0

#### What's new
* The new version include a deeply revised customisable portlet which better integrate with OneData allowing users to
access their information without cut&paste from OneData web interface.

#### List of RfCs
* [Issue-15](https://github.com/indigo-dc/LiferayPlugIns/issues/15) - OneData integration 
* [Issue-20](https://github.com/indigo-dc/LiferayPlugIns/issues/20) - Handle time synchronization problem robustly
* [Issue-22](https://github.com/indigo-dc/LiferayPlugIns/issues/22) - PTV Validation for external user
* [Issue-23](https://github.com/indigo-dc/LiferayPlugIns/issues/23) - Customisable portlet problem with string in json configuration 
* [Issue-25](https://github.com/indigo-dc/LiferayPlugIns/issues/25) - Customisable Application Portlet makes REST calls for unlogged user
* [Issue-26](https://github.com/indigo-dc/LiferayPlugIns/issues/26) - Improve error handling in Customisable Application Portlet
* [Issue-27](https://github.com/indigo-dc/LiferayPlugIns/issues/27) - Misleading errors in log file about problems parsing a valid token

#### Installation \& Configuration
* This is the same as previous release and included in the gitBook documentation. Previous components has to deactivated and
new version deployed and activated through the Liferay app console in the control panel.

* More information can be found in the "Upgrade to a new release" section of the [Administration Guide]https://indigo-dc.gitbooks.io/liferay-plugins/content/)

#### Artefacts
* CentOS 7
  * [LiferayPlugIns-binary-v2.1.0.tgz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/LiferayIAM-binary-v2.1.0.tgz)
* Ubuntu14.04
  * [LiferayPlugIns-binary-v2.1.0.tgz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/LiferayIAM-binary-v2.0.3.tgz)

## <a name="orchent"></a>Orchent v. 1.1.0

#### What's new
* Highlights of this update are:
  * added support for time and user based filtering #24
  * added support for alias in a local configuration file #25
  * add 'test' command to check if the url specified is backed by the orchestrator (to ensure the url has no typos etc) #20

#### List of RfCs
* (Issue #20)[https://github.com/indigo-dc/orchent/issues/20]
* (Issue #24)[https://github.com/indigo-dc/orchent/issues/24]
* (Issue #25)[https://github.com/indigo-dc/orchent/issues/25]

#### Installation & Configuration
* Documentation is avalable at - [Orchent GitBook](https://www.gitbook.com/book/indigo-dc/orchent/details)

#### Artefacts
* CentOS7
  * [orchent-0.1.0-1.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/orchent-0.1.0-1.el7.centos.x86_64.rpm)
* Ubuntu14.04
  * [orchent-0.1.0-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/orchent-0.1.0-1_amd64.deb)

* Container
  * [indigodatacloud/orchent:indigo_2](https://hub.docker.com/r/indigodatacloud/orchemt/tags/)
  
  
## <a name="ooi"></a>OOI v. 1.2.0

#### What's new
* The updated version provides:
  * New features: Implemented VM resize support.
  * Bug Fixes: Fix floating IP association issue with OpenStack Neutron and several OCCI rendering issues.

#### List of RfCs
* The complete list is at: https://launchpad.net/ooi/+milestone/1.2.0

* Floating IP association issue with OpenStack Neutron: https://bugs.launchpad.net/ooi/+bug/1709249
* mixins missing location attribute: https://bugs.launchpad.net/ooi/+bug/1687933
* os_tpl and resource_tpl mixins are missing `applies`: https://bugs.launchpad.net/ooi/+bug/1687938
* resource_tpl mixins missing default values: https://bugs.launchpad.net/ooi/+bug/1687943
* floatingippool mixins need a "parent" mixin: https://bugs.launchpad.net/ooi/+bug/1687935


#### Installation & Configuration
In order to update the packages please use:
* For CentOS 7:<br>
  ```yum clean all && yum update python-ooi```<br>
* For Ubuntu 14:04:<br>
  ```apt-get update && apt-get install python-ooi```<br>

* No extra actions are needed.


#### Artefacts
* CentOS7
  * [python-ooi-1.2.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/python-ooi-1.2.0-1.el7.centos.noarch.rpm)
* Ubuntu14.04
  * [python-ooi_1.2.0-1ubuntu1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/senial-updates/main/binary-amd64/python-ooi_1.2.0-1ubuntu1_all.deb)
  * [ooi-doc_0.3.2-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/ooi-doc_1.2.0-1_all.deb)


## <a name="synergy"></a>Synergy Service, v. 1.5.2  and Scheduler Manager, v. 2.5.0

#### What's new
This update brings many new features and bug fixes like
* New Synergy service features:
  * added security support
* New Synergy Scheduler Manager features:
  * added security support
  * implemented the new features required by the Partition Director (e.g. support for policy settings via API to define the list of projects allowed to use the share quota and the relevant shares; the number of user requests per Project, waiting in the priority queue)
  * added support to OpenStack Ocata

#### List of RfCs

* https://launchpad.net/synergy-service/+milestone/1.5.2
* https://launchpad.net/synergy-scheduler-manager/+milestone/2.5.0


* Complete list of issues is available at: https://review.openstack.org/#/q/projects:openstack/synergy

#### Installation & Configuration
* https://indigo-dc.gitbooks.io/synergy-doc/content/
* Service Reference Card: https://indigo-dc.gitbooks.io/synergy-doc/content/doc/service_reference_card.html
* Update/Upgrade Synergy packages: https://indigo-dc.gitbooks.io/synergy-doc/content/doc/admin.htm

#### Artefacts
* Supported Operating Systems platforms:
  * CentOS 7
  * Ubuntu 16.04
* Supported CMF (Cloud Management Framework) versions:
  * OpenStack v. Ocata
  * OpenStack v. Newton
  * OpenStack v. Mitaka (only CentOS 7)
  * OpenStack v. Liberty (only CentOS 7)

Packages:
* CentOS7
  * [python-synergy-service-1.5.2-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/python-synergy-service-1.5.2-1.el7.centos.noarch.rpm)
  * [python-synergy-scheduler-manager-2.5.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/python-synergy-scheduler-manager-2.5.0-1.el7.centos.noarch.rpm)
* Ubuntu 14.04
  * [python-synergy-service_1.5.2_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/xenial-updates/main/binary-amd64/python-synergy-service_1.5.2_all.deb)
  * [python-synergy-scheduler-manager_2.5.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/python-synergy-scheduler-manager_2.5.0_all.deb)


## <a name="tts"></a>WaTTS v. 1.2.0

#### What's new
* Mainly the release contains the newest Erlang VM under the hood witha faster startup time by running more concurrent and an enforced check of the user agent and peer ip of the clients. 

#### List of RfCs
* [Updated to newest Erlang Runtime System (ERTS) 20.0](https://github.com/indigo-dc/tts/issues/285)
* [support for RSP #281](https://github.com/indigo-dc/tts/issues/285)
* [ensure fast startup time, including logging of it #437](https://github.com/indigo-dc/tts/issues/437)
* [enforce checks of user agent and peer IP #394](https://github.com/indigo-dc/tts/issues/394)
* [https://github.com/indigo-dc/tts/issues/135](https://github.com/indigo-dc/tts/issues/135), [Issue-140](https://github.com/indigo-dc/tts/issues/140) - idh-single-user had issues with different providers, caused by local user cache

#### Installation & Configuration
   + Just apt install also documented here (maybe add two settings into the config, if updating from 1.0.0):
https://github.com/indigo-dc/tts/blob/master/gitbook/admin.md

Upgrading the TTS from version 0.2.2 to 0.4.0 is straight forward. As the configuration files are compatible the only actions to do are:
* stop the TTS:   ``` tts stop  ``` 
* install the new package
* start the newly installed TTS: ``` tts start  ``` 

#### Artefacts
* CentOS 7
  * [tts-0.4.0-1.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/tts-0.4.0-1.el7.centos.x86_64.rpm)
* Ubuntu 14.04
  * [tts_0.4.0-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/tts_0.4.0-1_amd64.deb)
* Docker Container:
  * [indigodatacloud/cdmi:indigo_1](https://hub.docker.com/r/indigodatacloud/cdmi/tags/)
