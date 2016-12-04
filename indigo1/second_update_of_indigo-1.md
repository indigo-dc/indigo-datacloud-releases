# Second Update of INDIGO-1 - 11/10/2016

The Second Update of INDIGO-1 release contains:
* [CDMI v. 1.1](#cdmi)
* [INDIGO IAM v. 0.4.0](#iam)
* [Infrastructure Manager v1.4.7](#im)
* [FutureGateway](#fg):
  * [fgAPIServer v0.0.5](#fg)
  * [APIServerDaemon v0.0.5](#fg)
  * [PortalSetup v0.0.4](#fg)
* [HEAT-Translator v. indigo-1.1](#ht)
* [LiferayIAM v. 1.1.1](#li)
* [Nova-Docker v. 12.0.0](#nd)
* [ONEdock v. 1.0-2](#onedock)
* [OOI v. 0.3.2](#ooi)
* [Orchestrator v. 1.1.0-FINAL](#orchestrator)
* [TOSCA-parser v. 0.6.1](#tp)


## <a name="cdmi"></a>CDMI v. 1.1

#### What's new
* Redis-Db replaces the filesystem-backed storage of metadata

#### List of RfCs
* Redis-DB as new metadata storage
* Focus on QoS-management via CDMI
* refactoring

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the [Updating CDMI-QoS Guide](hhttps://indigo-dc.gitbooks.io/cdmi-qos/content/doc/updating_cdmi-qos.html)

#### Artefacts
* CentOS 7
  * [cdmi-server-1.1-1.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/cdmi-server-1.1-1.x86_64.rpm)
* Ubuntu 14.04
  * [cdmi-server-1.1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/cdmi-server-1.1_all.deb)
* Docker Container:
  * [indigodatacloud/cdmi:indigo_1](https://hub.docker.com/r/indigodatacloud/cdmi/tags/)


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
* If the installation was done following the the instructions available in the [INDIGO-IAM Deployment and Administration Guide](https://indigo-dc.gitbooks.io/iam/content/doc/admin.html), please follow the following steps to upgrade:<br>
     ``` docker pull indigodatacloud/iam-login-service ``` <br>
     ``` docker stop iam-login-service ``` <br>
     ``` docker rm iam-login-service ``` <br>
     ``` docker run \  ``` <br>
     ```   --name iam-login-service --net=iam -p 8080:8080 \  ``` <br>
     ```   --env-file=/path/to//iam-login-service/env \  ``` <br>
     ```   -v /path/to//keystore.jks:/keystore.jks:ro \  ``` <br>
     ```   indigodatacloud/iam-login-service:indigo_1   ``` <br>

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

## <a name="fg"></a>FutureGateway
### <a name="fgas"></a>fgAPIServer & APIServerDaemon v0.0.5, PortalSetup v. 0.0.4
#### What's new
* This update contains only bug fixes

#### List of RfCs
* Portal token validator: LiferayIAM does not uses error: field to invalidate tokens; this time valid tokens are the ones providing the subject
* An internal 'state' has been exposes as an official state foreseen by API specifications
* During installation on machines having jdk8 the checkstyle caused a failure due to an unsupported jar file
* PortalSetup contains static references to the newest versions of fgAPIServer and APIServerDaemon for the installation script fgSetup.sh
  
#### Installation & Configuration
1. Extract from Git, paying attention to do not overwrite the apps/ directory and existing .conf files
2. Restart the service
  2. a) If fgAPIServer runs as an application (command line execution); just restart the service. In case the service has been started by the /etc/init.d/futuregateway script execute a restart
  2. b) The fgAPIServer runs as wsgi. Restart the service that provides the configured wsgi execution (In case of apache restart it).
3. APIServerDaemon; this is a Java web application and its code must be extracted from Git and compiled executing 'ant all', once obtained the war file copy the file under $CATALINA_HOME/webapps, then control the file $CATALINA_HOME/logs/catalina.out file checking for its successful installation. The service is now ready and polling activity can be monitored by the log file $CATALINA_HOME/webapps/APIServerDaemon/WEB-INF/logs/APIServerDaemon.log

#### Artefacts
* CentOS7
  * [fgAPIServer-v0.0.5.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/fgAPIServer-v0.0.5.tar.gz)
  * [APIServerDaemon-v0.0.5.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/APIServerDaemon-v0.0.5.tar.gz)
  * [PortalSetup-v0.0.4.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/PortalSetup-v0.0.4.tar.gz)
* Ubuntu14.04
  * [fgAPIServer-v0.0.5.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/source/fgAPIServer-v0.0.5.tar.gz)
  * [APIServerDaemon-v0.0.5.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/source/APIServerDaemon-v0.0.5.tar.gz)
  * [PortalSetup-v0.0.4.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/source/PortalSetup-v0.0.4.tar.gz)

## <a name="ht"></a>HEAT-Translator v. indigo-1.1

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


## <a name="li"></a>LiferayIAM v. 1.1.1

#### What's new
* This release improve updates groups management following the new IAM groups specification: From IAM >= v0.4.0.rc0 groups are provided as a simple list of name and not as maps with name and other properties. The new version can manage the group list. Additionally, documentation has been improved with instructions to upgrade from the previous version.

#### List of RfCs
* [Issue-10](https://github.com/indigo-dc/LiferayIAM/issues/10) - Groups generate exceptions

#### Installation \& Configuration
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


## <a name="nd"></a>Nova-Docker v. 12.0.0

#### What's new
* The new version provides better packaging, configuration files are now provided in a separate package from the library, and also [improved documentation is provided](https://indigo-dc.gitbooks.io/openstack-nova-docker/content/)

#### Installation & Configuration
* In order to perform an update please follow the following instructions:
* For CentOS 7:<br>
  ``` yum -y remove python-nova-docker && yum clean all && yum -y update python-nova-docker```<br>
* For Ubuntu 14:04:<br>
  ```apt-get remove --purge python-nova-docker```<br>
  ```apt-get update && apt-get -y install python-nova-docker nova-compute-docker```<br>
  
#### Artefacts
* CentOS7
  * [python-nova-docker-12.0.4_indigo-1.el7.local.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/centos7/x86_64/updates/python-nova-docker-12.0.4_indigo-1.el7.local.noarch.rpm)
* Ubuntu14.04
  * [nova-compute-docker_12.0.0_indigo-1_all.deb ](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/nova-compute-docker_12.0.0_indigo-1_all.deb )
  * [python-nova-docker_12.0.0_indigo-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-nova-docker_12.0.0_indigo-1_all.deb)

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

* More details can be found in the [CHANGELOG](https://github.com/indigo-dc/orchestrator/blob/master/CHANGELOG.md#v110---2016-09-30)

#### Installation & Configuration
* Before the upgrade it needs to be checked on IAM if the openid scope is selected for the Orchestrator protected resource server, otherwise the clients will not be able to make requests to it.
* In order to update the container, please do:
  * Stop the old container:<br>
  ```sudo docker stop orchestrator ```<br>
  * Remove the old container:<br>
  ```sudo docker rm orchestrator ```<br>
  * Pull the new image version:<br>
  ```sudo docker pull indigodatacloud/orchestrator:indigo_1``` <br> 
  * Start the new version, with the same command that you used before, just pay attention to use the right tag of the container, like:
  ```sudo docker run --name orchestrator --link databaseWorkflow:databaseWorkflow --link databaseOrchestrator:databaseOrchestrator \
-p 80:8080 -e ORCHESTRATOR_URL="<public_orchestrator_url, like http://localhost:80>" -d indigodatacloud/orchestrator:indigo_1```


#### Artefacts
* Docker Container:
  * [docker pull indigodatacloud/orchestrator:indigo_1](https://hub.docker.com/r/indigodatacloud/orchestrator/tags/)
  


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


<!--
## <a name="zp"></a>Zabbix-probes v. 1.01

#### What's new
* The current update is mainly focused on solving several bugs detected and on adding a feature to the OCCI probe for improving its adoption rate, since the former user/password authentication was not adequate enough for automating the whoel monitoring process.  The documentation includes also a new section about updating the Zabbix probes

#### List of RfCs
* [Issue #6](ttps://github.com/indigo-dc/Monitoring/issues/6)Bug fix related to retrieving the config file info when the file is not available
* Add IAM support for authentication in the OCCI probe


#### Installation & Configuration
 * deb and rpm files will be provided for updating the current packages

#### Artefacts
* 
-->


