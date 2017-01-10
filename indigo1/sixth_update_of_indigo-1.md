# Sixth Update of INDIGO-1 - 30.12.2016

The Sixth Update of INDIGO-1 release contains:
* [INDIGO IAM v. 0.5.0](#iam)
* [LiferayIAM v. 1.2.1](#li)
* [Onedata v. 3.0.0.11](#onedata) 
* [Orchestrator v. 1.2.1-FINAL](#orchestrator)
* [Synergy Service, v. 1.3.0 and Scheduler Manager, v. 2.2.2](#synergy)

## <a name="iam"></a>INDIGO IAM v.0.5.0

#### What's new
* This release provides new functionality and some bug fixes like the possible for users to link external authentication accounts
  (Google, SAML) to the user IAM account and to register at the IAM starting from an external authentication

#### List of RfCs
* Features:
  * [#39](https://github.com/indigo-iam/iam/issues/39) - As an authenticated user, I can link an external SAML or OIDC account to my IAM account  
  * [#40](https://github.com/indigo-iam/iam/issues/40) - As an autenticated user, I can change my password  
  * [#44](https://github.com/indigo-iam/iam/issues/44) - It is now possible to register at the IAM using one of supported external authentication mechanism 
  * [#46](https://github.com/indigo-iam/iam/issues/46) - The IAM now exposes an authority management endpoint (integrated in the dashboard) that allows to assign/remove administrative rights to/from users
  * [#59](https://github.com/indigo-iam/iam/issues/59) - The IAM now provides a refactored SAML WAYF service that remembers the identity provider chosen by the user.
* Bug fixes: 
  * [#32](https://github.com/indigo-iam/iam/issues/32) - The IAM now provides a refactored SAML WAYF service that remembers the identity provider chosen by the user.
  * [#34](https://github.com/indigo-iam/iam/issues/34) - Group creation in the dashboard now behaves as expected
  * [#49](https://github.com/indigo-iam/iam/issues/49) - Editing first name/family name fails on the dashboard
  * [#51](https://github.com/indigo-iam/iam/issues/51), [#52](https://github.com/indigo-iam/iam/issues/52) -Improved token exchange documentation
  * [#53](https://github.com/indigo-iam/iam/issues/53) - SCIM: the SCIM create group endpoint should not require clients to provide a uuid
  * [#56](https://github.com/indigo-iam/iam/issues/56) - The IAM discovery endpoint does not advertise support for the resource owner password credential flow 
  * [#65](https://github.com/indigo-iam/iam/issues/65) - It is now possible to set custom SAML maxAssertionTime and maxAuthenticationAge to customize how the SAML filter should check incoming SAML responses and assertions

* More information about bug fixes and other developments can be found on our [HitHub IAM issue tracker](https://github.com/indigo-iam/iam/releases/tag/v0.5.0) 

#### Installation & Configuration
* If the installation was done following the the instructions available in the [INDIGO-IAM Deployment and Administration Guide](https://indigo-dc.gitbooks.io/iam/content/doc/admin.html), please follow the following steps to upgrade:<br>
     ``` docker pull indigodatacloud/iam-login-service ``` <br>
     ``` docker stop iam-login-service ``` <br>
     ``` docker rm iam-login-service ``` <br>
     ``` docker run \  ``` <br>
     ```   --name iam-login-service --net=iam -p 8080:8080 \  ``` <br>
     ```   --env-file=/path/to//iam-login-service/env \  ``` <br>
     ```   -v /path/to//keystore.jks:/keystore.jks:ro \  ``` <br>
     ```   indigodatacloud/iam-login-service:indigo_1   ``` <br>
* Service Reference Card is available [here](https://indigo-dc.gitbooks.io/iam/content/doc/admin.html)

#### Artefacts
* Docker Container:
  * [indigodatacloud/iam-login-service:indigo_1](https://hub.docker.com/r/indigodatacloud/iam-login-service/tags/)
  
## <a name="li"></a>LiferayIAM v. 1.2.1

#### What's new
* This update fixes an important bug which prevent the correct validation of the token in some conditions.

#### List of RfCs
* [Issue-21](https://github.com/indigo-dc/LiferayIAM/issues/21) -  Token validation across portal failure


#### Installation \& Configuration
* In order to use the latest version, 1.2.1, it is requested:
  * To upgrade a running service people have to remove previous `jar` files and deploy upload the new packages.
  * No configuration is requested, it is preserved from the previous installation.
  * For more details on installation and upgrade see [Service Reference Card](https://indigo-dc.gitbooks.io/liferay-iam-connector/content/doc/service_reference.html)
* *Note*: to remove the old version and copy the new files it is possible to use the Ansible Playbookavailable at:
  * https://github.com/indigo-dc/ansible-role-liferay-iam/releases/tag/1.2.1

#### Artefacts
* CentOS 7
  * [LiferayIAM-binary-1.2.1.tgz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/tgz/LiferayIAM-binary-1.2.1.tgz)
* Ubuntu14.04
  * [LiferayIAM-binary-1.2.1.tgz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/LiferayIAM-binary-1.2.1.tgz)

## <a name="onedata"></a>Onedata v. 3.0.0.11

#### What's new
Onedata 3.0.0.11 INDIGO - DataCloud release improved performance and stability of all Onedata services, as compared to the initial release. New features, such as public shares and file/directory/space metadata support were added. Furthermore, data stored in Onezone and Oneprovider is now automatically processed when upgrading to new version.

#### List of RfCs
A complete changelog reflecting all bug fixed and new features is included in every Onedata repository on github in CHANGELOG.md. Furthermore, most notable issues were features were selected and included in this document.
* Onezone
  * VFS-2633 Use specific package builders
  * VFS-2582 Using GUI fix for blank notifications
  * VFS-2390 Upgrade rebar to version 3
  * Update one panel for extended configuration options
  * Add ONEPANEL_DEBUG_MODE env variable to release docker entrypoint
* Oneclient
  * VFS-2400 Update to new ceph and aws libraries
  * Fix storage detection in case of unsupported space
  * VFS-1963 Improve automatic storage discovery
  * VFS-2316 Integrate new etls version.
  * VFS-2250 Add base62 encoding and decoding to tokenHandler
  * VFS-2272 Give precendence to env AUTHORIZATION_TOKEN.
  * VFS-2270 Print out the hostname of client's provider.
  * VFS-2215 Remove the file immediately on unlink.
* Oneprovider
  * VFS-2617 Changed metadata submenu to metadata panel
  * VFS-2180 Improve links conflict resolution
  * VFS-2180 Improve dbsync implementation
  * VFS-2180 Use gen_server2 instead of erlang's gen_server module
  * VFS-2390 Fix handlers specification in REST API
  * VFS-2390 Update rebar to version 3
  * VFS-2180 Allow for concurrent file creation
  * Update interfaces
  * Increase system performance
  * Update one panel for extended configuration options
  * Add ONEPANEL_DEBUG_MODE env variable to release docker entrypoint
  * VFS-2395 Added scrolling to element when clicking settings icon.
  * Turn off HSTS by default, allow configuration via app.config
  * Update file consistency management
  * Enable metadata caching
  * Extend support for user-defined metadata
  * Update Web_GUI and REST API
  * Enable Symmetric Multiprocessing
  * VFS-2773 Listen to more changes in /changes api and add a few new tests.
  * VFS-2764 Fix directories having 0B size in GUI
  * VFS-2764 Fix size of files being zero right after upload
  * VFS-2662 Append new files to the beginning of the files list
  * VFS-2662 Implement file creation compatible with pagination model
  * VFS-2400 Update to new ceph and aws libraries
  * VFS-2524 Improve translation of acl and xattr records.
  * VFS-2524 Add basic attributes to /attributes endpoint.
  * VFS-2524 Fix wrong file owner in cdmi.
  * VFS-2524 Add copy operation to cdmi interface.
  * VFS-2573 Repair custom metadata propagation
  * VFS-2659 Rework user and group models
  * VFS-2625 Fix public share view not retrieving fiels correctly
  * VFS-2524 Add move operation to cdmi, split move and copy tests.
  * VFS-2594 Add remove_metadata operation.
  * VFS-2180 Implement support for read only spaces
  * VFS-2456 Add metadata to public view
  * VFS-2456 Implement first version of metadata backend
  * VFS-2555 Add shares field to file attr.
  * VFS-2405 Adjust to new shares API in OP
  * VFS-2555 Improve share permissions and guest user management.
  * VFS-2472 Convert metadata to from proplists to maps.
  * VFS-2472 Unify file identifiers in REST interface.
  * VFS-2472 Add listing and getting inherited xattrs to REST API.
  * VFS-2309 oz test mock updated to match actual implementation
  * VFS-2311 Add private RPC to retrieve file download URL
  * VFS-2189 Close connection after file upload failure
  * VFS-2303 Add metadata-id endpoint.
  * VFS-2303 Add filters for getting metadata.
  * VFS-2303 Add query-index rest endpoint.
  * VFS-2269 Enable Symmetric Multiprocessing
  * VFS-2303 Adjust metadata changes stream to the new metadata organization.
  * VFS-2319 Reimplement monitoring using events
  * VFS-2303 Add basic metadata operations.
  * VFS-2049 Make file_consistency work after system restart.
  * VFS-2049 Improve file_consistency model.
  * VFS-2303 Add support for rdf metadata.
  * VFS-2361 Turn off HSTS by default, allow configuration via app.confi

The list of open and closed issues can be found also in  GitHub:
* https://github.com/indigo-dc/onedata/issues (8 open/6 closed)
* https://github.com/indigo-dc/onezone/issues (0 open/0 closed)
* https://github.com/indigo-dc/oneclient/issues (0 open/0 closed)
* https://github.com/onedata/getting-started/issues (0 open/3 closed)

#### Installation & Configuration

* Update procedure
  * There is no way to upgrade from previous release, the clean installation is needed. 
* Documentation on clean installation is available at:
  * https://onedata.org/docs/doc/getting_started/downloading_onedata.html
  * https://onedata.org/docs/doc/getting_started/admin_onedata_101.html

#### Artefacts

* Recomended operating system for all Onedata services is Ubuntu 16.04.
  * Oneclient:
    * any platform that supports Docker Engine (>1.11)
    * Ubuntu 14.04, 15.10, 16.04
    * Centos 7
    * Fedora 23
  * Oneprovider:
    * any platform that supports Docker Engine (>1.11)
    * Ubuntu 15.10, 16.04
    * Fedora 23
  * Onezone:
    * any platform that supports Docker Engine (>1.11)
    * Ubuntu 15.10, 16.04
    * Fedora 23
* Artefacts available from IDNIGO-DataCloud repositories:
  * CentOS 7:
    * [oneclient-3.0.0.rc11.71.g4e1189e-1.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/oneclient-3.0.0.rc11.71.g4e1189e-1.el7.centos.x86_64.rpm])
  * Ubuntu 14.04:
    * [oneclient_3.0.0.rc11.71.g4e1189e-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/	oneclient_3.0.0.rc11.71.g4e1189e-1_amd64.deb)   
  * Docker images:
    * indigodatacloud/onezone:3.0.0.11
    * indigodatacloud/oneprovider:3.0.0.11
    * indigodatacloud/oneclient:3.0.0.11
* A repository supporting **optional** Operating Systems is available at http://onedata-dev-packages.cloud.plgrid.pl providing packages for Fedora 23, Ubuntu  15.10 and 16.10

## <a name="orchestrator"></a>Orchestrator v. 1.2.1-FINAL

#### What's new
* The current update provides improved TOSCA templates parsing and IAM access token handling.

#### List of RfCs
* Fixes:
  * [Issue #157](https://project.indigo-datacloud.eu/work_packages/157) - Check access token expiration date and signature
* Improvements:
  * [Issue #158](https://project.indigo-datacloud.eu/work_packages/158) - Update default monitoring endpoint 
  * [Issue #161](https://project.indigo-datacloud.eu/work_packages/161) - Update custom INDIGO TOSCA types 
  * [Issue #163](https://project.indigo-datacloud.eu/work_packages/163) - Improve DB connection handling during shutdown


#### Installation & Configuration
This release require a parameter change regarding the zabbix wrapper endpoint - the environment variable provided during startup must be changed from: </br>
  ``` http://${host}:${port}/monitoring/adapters/zabbix/zones/indigo/types/*service*/groups/Cloud_Providers/hosts/ ```</br>
  to </br>
  ``` http://${host}:${port}/monitoring/adapters/zabbix/zones/indigo/types/*infrastructure*/groups/Cloud_Providers/hosts/ ```</br>

Thus, the upgrade operations are:
* Stop the old container:</br>
  ```sudo docker stop orchestrator```</br>
* Remove the old container:</br>
  ```sudo docker rm orchestrator```</br>
* Pull the new image version:<br>
  ```sudo docker pull indigodatacloud/orchestrator:1.2.1-FINAL```</br>
* Start the new version:</br>
  ```docker run ...*updated parameters*... indigodatacloud/orchestrator:1.2.1-FINAL```</br>

#### Artefacts
* Docker Container:
  * [indigodatacloud/orchestrator:indigo_1](https://hub.docker.com/r/indigodatacloud/orchestrator/)

## <a name="synergy"></a>Synergy Service, v. 1.3.0  and Scheduler Manager, v. 2.2.2

#### What's new
This update brings many new features and bug fixes like
* new **Synergy Service** features:
  * added support for OpenStack DOMAIN to shell.py
  * use pbr fully for easier package building
* new **Synergy Schedule Manager** features:
  * OpenStack projects can now access to two distinct quota kinds: private and shared quota (see documentation)
  * Synergy CLI command enhanced in order to be compliant with the OpenStack style
  * KeystoneManager enhanced with the support of trust tokens; added the new "clock skew" feature needed for renewing the tokens a delta time before their expiration (new 'clock_skew' parameter)
  * SchedulerManager enhanced with the implementation of the BACKFILL scheduling algorithm (new 'backfill_depth' parameter)
  * NovaManager enhanced with the support to METADATA (new 'metadata_proxy_shared_secret' parameter)
  * use pbr fully for easier package building
* breaking changes
  * Synergy doesn't rely anymore on nova.conf
  * Synergy CLI changed (see documentation)
  * now by default, the VMs are instantiated into the private quota. To select the shared quota, is needed to place special keys in the local user data file and pass it through the--user-data <user-data-file> parameter at instance creation (see user guide https://indigo-dc.gitbooks.io/synergy/content/user-guide.html)

#### List of RfCs

Changes for **synergy-service** since v1.0.1
* Features
  * Added support for OpenStack DOMAIN to shell.py
  * use pbr fully for easier package building
* Bug fixes
  * Replaces uuid.uuid4 with uuidutils.generate_uuid
  * [packaging] make docker aware of PKG_VERSION
  * Update changelogs and system package versions
  * Clean up oslo imports
  * Update the Sphinx documentation
  * fix packaging with docker and its documentation
  * Distribute tabulate as part of Synergy
  * Remove versions for required packages
  * fix missing "requests" from the requirements
  * Updated coverage configuration file
  * fix docker packaging for CentOS
  * fix wrong version of eventlet
  * fix docs for packaging with Ubuntu
  * fix to get the synergy version when packaging
  * fix required packages when packaging
  * RPM: don't output errors on uninstallation
  * Fix conf for AMQP virtual host
  * Added unit tests
  * Fixed destroy() method
  * Fixed serializer
  * Fixed logging for managers
  * fix eventlet and dateutil required versions
  * Fix requirement version pinning
  * setup.cfg mod
  * setup.cfg updated
  * Use dependency pinning
  * Streamline packaging with docker
  * Cleanup tox.ini: Remove obsolete constraints
  * improved serialization
  * Managers are now serializable
  * improved command shell by using the 'tabulate' module
  * listManagers, startManager, stopManager and getManagerStatus methods now use the Managers serialization
  * 'tabulate' module dependence added
  * updated unit tests
  * changed entry points

Changes for **synergy-scheduler-manager** since v1.0.1
* Breaking changes
  * Synergy doesn't rely anymore on nova.conf
* Features
  * Add the new clock_skew parameter for KeystoneManager
  * Add a backfill_depth parameter
  * CLI command "synergy usage show" enhanced
  * Scheduler managers enhanced
  * use pbr fully for easier package building
* Bug fixes
  * Make SchedulerManager handle ERROR notifications
  * fix: update required version of synergy-service
  * [packaging] make docker aware of PKG_VERSION
  * Synergy releases in advance the VMs that are going to be destroyed
  * Queue.updatePriority() takes much time if the queue is large
  * Invalid input for field/attribute quota_class_set
  * KeystoneManager.authenticate() uses a wrong domain attribute
  * Item readjustment fixed in PriorityQueue
  * The FairshareManager should not use the Manager.condition var
  * Fix scheduling when shared quota is disabled
  * Update changelogs and system package versions
  * Clean up oslo imports
  * Method deserialize() fixed
  * The QuotaCommand shows a wrong value (%) for the field 'share'
  * Remove versions for required packages
  * fix git and pbr when packaging with docker
  * fix synergy-service version in spec file (rpm)
  * fix required packages when packaging
  * fix to get the synergy version when packaging
  * fix connection URL to RabbitMQ
  * Added Queue class to synergy_scheduler_manager/common/queue.py
  * Common objects and relative test units added
  * Destroy() method fixed
  * Fix requirement version pinning
  * Use dependency pinning
  * fix OpenStack CentOS repo for docker packaging
  * Cleanup tox.ini: Remove obsolete constraints
  * Add python-nova as a dependency

* Complete list of issues is available at: https://review.openstack.org/#/q/projects:openstack/synergy

#### Installation & Configuration
* Service Reference Card: https://indigo-dc.gitbooks.io/synergy/content/doc/service_reference_card.html
* Instructions on how to Update an already existing service are avalable [here]()

#### Artefacts
Packages:
* CentOS7
  * [python-synergy-service-1.3.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/python-synergy-service-1.3.0-1.el7.centos.noarch.rpm)
  * [python-synergy-scheduler-manager-2.2.2-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/python-synergy-scheduler-manager-2.2.2-1.el7.centos.noarch.rpm)
* Ubuntu 14.04
  * [python-synergy-service_1.3.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-synergy-service_1.3.0_all.deb)
  * [python-synergy-scheduler-manager_2.2.2_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-synergy-scheduler-manager_2.2.2_all.deb)
