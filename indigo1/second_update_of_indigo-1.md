# Second Update of INDIGO-1

The Second Update of INDIGO-1 release contains:
* [INDIGO IAM v. 0.4.0](#iam)
* [Infrastructure Manager v1.4.7](#im)
* [ONEdock v. 1.0-2](#onedock)
* [TOSCA-parser v. 0.6.1](#tp)
* [TOSCA-in-HEAT/Heat-Translator v. indigo-1.1](#ht)
* [OOI v. 0.3.2](#ooi)
* [Zabbix-probes v. 0.4.0](#zp)
* [Orchestrator v. 1.1.0-FINAL](#orchestrator)
* [Nova-Docker v. 12.0.0](#nd)
* [FutureGateway](#fg):
  * [fgAPIServer v0.0.4](#fgapis)
  * [APIServerDaemon v0.0.4](#fgapisd)
  * [PortalSetup v0.0.3](#fgps)
* [LiferayIAM v. 1.1.1](#li)


## <a name="iam"></a>INDIGO IAM v.0.4.0

#### What's new
* This release provides new functionality and some bug fixes

#### List of RfCs
* Groups are now encoded in the JSON returned by the IAM /userinfo endpoint as an array of group names.
* Group information is also exposed by the token introspection endpoint
* External authentication information (i.e. when a user authenticates with Google or SAML instead of username/password) is now provided in the JSON returned by the /userinfo endpoint
* The first incarnation of the administrative dashboard is now included in the service
* The first incarnation of the registration service is now included. The registration service implements a "self-register with admin approval" registration flow
* User passwords are now encoded in the database using the Bcrypt encoder
* A password forgotten service is now provided

* More information about bug fixes and other developments can be found on our [JIRA release board](https://issues.infn.it/jira/browse/INDIAM/fixforversion/13811) 

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the [INDIGO-IAM Deployment and Administration Guide](https://andreaceccanti.gitbooks.io/iam/content/doc/admin.html)

#### Artefacts
* Docker Container:
  * [indigodatacloud/iam-login-service:indigo_1](https://hub.docker.com/r/indigodatacloud/iam-login-service/tags/)

## <a name="im"></a>Infrastructure Manager v1.4.7

#### What's new
* The updated version of the IM adddresses a number of issues like return 403 error when the user cannot access the infrastructure and add features like single site support 

#### List of RfCs
* Add single site support
* Return 403 error in REST API when the user cannot access the infrastructure
* Assure to kill ansible processes is case of ctxt timeout
* Bugfix in some configuration cases
* Bugfix not installing ansible roles defined in not master vm
* Add im.service file add support to systemd
* Enable to add a Storage to a running VM in the OCCI and OpenNebula connectors
* Bugfix in OCCI not waiting the volumes on creation

#### Installation & Configuration
In order to update the packages please use:
* For CentOS 7:<br>
  ``` yum clean all && yum update IM```<br>
* For Ubuntu 14:04:<br>
  ```apt-get update && apt-get install python-im```<br>
* For containers  
  * Stop the old container:<br>
  ```sudo docker stop im ```<br>
  * Remove the old container:<br>
  ```sudo docker rm im ```<br>
  * Pull the new image version:<br>
  ```sudo docker pull indigodatacloud/im``` <br> 
  * Start the new version:
  ```sudo docker run -d -p 8899:8899 -p 8800:8800 -e IM_DATA_DB=mysql://username:password@server/db_name --name im indigodatacloud/im  ``` <br>

#### Artefacts
* CentOS7
  * [IM-1.4.7-1.el7.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/centos7/x86_64/updates/IM-1.4.7-1.el7.noarch.rpm)
* Ubuntu14.04
  * [python-im_1.4.7-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-im_1.4.7-1_all.deb)
* Container
  * [indigodatacloud/im:indigo_1](https://hub.docker.com/r/indigodatacloud/im/tags/)

## <a name="onedock"></a>ONEdock v. 1.0-2

#### What's new
*  The updated version of OneDock addresses a problem due to the change in the -f parameter in the Docker CLI with the updated versions of Docker 

#### List of RfCs
* Add ansible installation for onedock
* Update config file installation
* Create package generating scripts for debian-based systems
* Create package generating scripts for rpm
* Remove the -f flag for docker tag
* Update scripts to comply with bashate style rules
* Add wiki documentation to gitbook

#### Installation & Configuration
In order to update the packages please use:
* For CentOS 7:<br>
  ```yum clean all && yum update onedock-master``` and <br>
  ```yum clean all && yum update onedock-node```<br>
* For Ubuntu 14:04:<br>
  ```apt-get update && apt-get install onedock-master```and<br>
  ```apt-get update && apt-get install onedock-node```<br>
  
#### Artefacts
* CentOS 7
  * [onedock-master-1.0-2.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/onedock-master-1.0-2.noarch.rpm)
  * [onedock-node-1.0-2.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/onedock-node-1.0-2.noarch.rpm)
* Ubuntu 14.04
  * [onedock_1.0-2_master_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/onedock_1.0-2_master_all.deb)
  * [onedock_1.0-2_node_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/onedock_1.0-2_node_all.deb)
  

## <a name="tp"></a>TOSCA-parser v. 0.6.1

#### What's new
* The updated version of TOSCA-parser addresses minor bug fixes and integrates the changes made upstream (in openstack/tosca-parser v.0.6).

#### Installation & Configuration
In order to update the packages please use:
* For CentOS 7:<br>
  ``` yum clean all && yum update tosca-parser```<br>
* For Ubuntu 14:04:<br>
  ```apt-get update && apt-get install python-tosca-parser```<br>
  
  
#### Artefacts
* CentOS7
  * [tosca-parser-0.6.1-1.el7.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/centos7/x86_64/updates/tosca-parser-0.6.1-1.el7.noarch.rpm)
* Ubuntu14.04
  * [python-tosca-parser_0.6.1-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-tosca-parser_0.6.1-1_all.deb)
  
  
## <a name="ht"></a>TOSCA-in-HEAT/HEAT-Translator v. indigo-1.1

#### What's new
* Fix network support : a map was wrongly used instead of a list which would create invalid hot templates. 

#### Installation & Configuration
In order to update the packages please use:
* For CentOS 7 + Mitaka:<br>
  ``` yum clean all && yum update heat-translator```<br>
* For Ubuntu 14:04:<br>
  ```apt-get update && apt-get install python-heat-translator```<br>


#### Artefacts
* CentOS7
  * [heat-translator-0.5.1.dev38-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/centos7/x86_64/updates/heat-translator-0.5.1.dev38-1.noarch.rpm)
* Ubuntu14.04
  * [python-heat-translator_0.5.1.dev38-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-heat-translator_0.5.1.dev38-1_all.deb)

## <a name="ooi"></a>OOI v. 0.3.2

#### What's new
* The updated version provides only bug fixes, no new feature

#### List of RfCs
* ooi fails with 500 when deleting a volume
* ooi fails with error 500 when deleting a volume that is attached

* More info at [Milestone-0.3.2](https://launchpad.net/ooi/+milestone/0.3.2)

#### Installation & Configuration
In order to update the packages please use:
* For CentOS 7:<br>
  ```yum clean all && yum update python-ooi```<br>
* For Ubuntu 14:04:<br>
  ```apt-get update && apt-get install python-ooi```<br>

#### Artefacts
* CentOS7
  * [python-ooi-0.3.2-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/centos7/x86_64/updates/python-ooi-0.3.2-1.el7.centos.noarch.rpm)
* Ubuntu14.04
  * [python-ooi_0.3.2-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-ooi_0.3.2-1_all.deb)
  * [ooi-doc_0.3.2-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/ooi-doc_0.3.2-1_all.deb)
  
## <a name="zp"></a>Zabbix-probes v. 1.01

#### What's new
* The current update is mainly focused on solving several bugs detected and on adding a feature to the OCCI probe for improving its adoption rate, since the former user/password authentication was not adequate enough for automating the whoel monitoring process.  The documentation includes also a new section about updating the Zabbix probes

#### List of RfCs
* [Issue #6](ttps://github.com/indigo-dc/Monitoring/issues/6)Bug fix related to retrieving the config file info when the file is not available
* Add IAM support for authentication in the OCCI probe


* More information about bug fixes and other developments can be found on our [ADD](https://link) 

#### Installation & Configuration
* deb and rpm files will be provided for updating the current packages

#### Artefacts
* 


## <a name="orchestrator"></a>Orchestrator v. 1.1.0-FINAL

#### What's new
* The compatibility with IAM has been improved
* Now the resources obtained from the REST APIs are sorted by date
* CLUES installed on board of the elastic clusters can receive the IAM token


#### List of RfCs
* [Issue #109](https://github.com/indigo-dc/orchestrator/issues/109) - Support iam_access_token property in tosca.nodes.indigo.ElasticCluster nodes
* [Issue #110](https://github.com/indigo-dc/orchestrator/issues/110) - Support multiple SLAs for the same cloud provider
* [Issue #101](https://github.com/indigo-dc/orchestrator/issues/101) - Deployments and resources must be sorted by date when retrieved from REST APIs
* [Issue #104](https://github.com/indigo-dc/orchestrator/issues/104) - Adapt user info data to the new IAM format

#### Installation & Configuration
In order to update the container, please do:
* Stop the old container:<br>
  ```sudo docker stop orchestrator ```<br>
* Remove the old container:<br>
  ```sudo docker rm orchestrator ```<br>
* Pull the new image version:<br>
  ```sudo docker pull indigodatacloud/orchestrator``` <br> 
* Start the new version:

#### Artefacts
* Docker Container:
  * [docker pull indigodatacloud/orchestrator:indigo_1](https://hub.docker.com/r/indigodatacloud/orchestrator/tags/)


## <a name="nd"></a>Nova-Docker v. 12.0.0

#### What's new
* The new version provides better packaging, configuration files are now provided in a separate package from the library, and also [improved documentation is provided](https://indigo-dc.gitbooks.io/openstack-nova-docker/content/)

#### Installation & Configuration
* In order to perform an update please follow the following instructions:


#### Artefacts
* CentOS7
  * [python-nova-docker-12.0.4_indigo-1.el7.local.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/centos7/x86_64/updates/python-nova-docker-12.0.4_indigo-1.el7.local.noarch.rpm)
* Ubuntu14.04
  * [nova-compute-docker_12.0.0_indigo-1_all.deb ](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/nova-compute-docker_12.0.0_indigo-1_all.deb )
  * [python-nova-docker_12.0.0_indigo-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-nova-docker_12.0.0_indigo-1_all.deb)
  

<!--
## <a name="fg"></a>FutureGateway
### <a name="fgas"></a>fgAPIServer v0.0.4
#### What's new
* Aligned LiferayIAM answers to the latest version
* Fixed little bug DELETE task
* Fix when using default user (No mapping in PTV)

#### Installation & Configuration
* To update fgAPIServer, just extract its code from the tarball placing it into $FGLOCATION, paying attention to do not overwrite any configuration file. Once new files are available, restart fgapiserver.py scipt in the screen section or restart the web server in case the front-end uses wsgi to execute.

#### Artefacts
* CentOS7
  * [fgAPIServer-v0.0.4.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/fgAPIServer-v0.0.4.tar.gz)
* Ubuntu14.04
  * [fgAPIServer-v0.0.4.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/source/fgAPIServer-v0.0.4.tar.gz)

### <a name="fgasd"></a>APIServerDaemon v0.0.4
#### What's new
* Fix on WAITING tasks
* Including runtime_data while deleting task
* Adding resource info in ToscaIDC executor interface (token)

#### Installation & Configuration
* To update APIServerDaemon, rename the existing $FGLOCATION/APIServerDaemon directory, extract its new code from the tarball make a full copy of the direcrtory web/WEB-INF/lib to the new APIServerDaemon dir. Execute and all and generate the new war file. Copy the war file into $CATALINA_HOME/webapps and check the log file $CATALINA_HOME/logs/catalina.log for successful deployment.

#### Artefacts
  * [APIServerDaemon-v0.0.4.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/APIServerDaemon-v0.0.4.tar.gz)
* Ubuntu14.04
  * [APIServerDaemon-v0.0.4.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/source/APIServerDaemon-v0.0.4.tar.gz)

### <a name="fgps"></a>PortalSetup v0.0.3
#### What's new
* fgSetup.sh can be configured to extract a fixed release
* Included fgSetup.sh script pointing to the latest available release

#### Installation & Configuration
* Just extract new files from the tarball

#### Artefacts
  * [PortalSetup-v0.0.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/PortalSetup-v0.0.3.tar.gz)
* Ubuntu14.04
  * [PortalSetup-v0.0.3.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/source/PortalSetup-v0.0.3.tar.gz)
-->

## <a name="li"></a>LiferayIAM v. 1.1.1

#### What's new
* This release improve updates groups management following the new IAM groups specification: From IAM >= v0.4.0.rc0 groups are provided as a simple list of name and not as maps with name and other properties. The new version can manage the group list. Additionally, documentation has been improved with instructions to upgrade from the previous version.

#### List of RfCs
* [Issue-10](https://github.com/indigo-dc/LiferayIAM/issues/10) - Groups generate exceptions

#### Installation & Configuration
* In order to use the latest version, 1.1.1, it is requested:
  * to remove the old version from the Liferay portal configuration panel and remove the old jar
  * restart Liferay and deploy the new one
  * No post-installation configuration is requested.

* More information can be found in the "Upgrade to a new release" section of the [Administration Guide](https://indigo-dc.gitbooks.io/liferay-iam-connector/content/doc/admin.html)

#### Artefacts
* CentOS 7
  * [LiferayIAM-binary-v1.1.1.tgz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/tgz/LiferayIAM-binary-v1.1.1.tgz)
* Ubuntu14.04
  * [LiferayIAM-binary-v1.1.1.tgz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/LiferayIAM-binary-v1.1.1.tgz)

