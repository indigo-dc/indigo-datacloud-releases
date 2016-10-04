# Second Update of INDIGO-1

The Second Update of INDIGO-1 release contains:
* [INDIGO IAM v. 0.4.0](#iam)
* [Infrastructure Manager v1.4.7](#im)
* [ONEdock v. 1.0-2](#onedock)
* [TOSCA-parser v. 0.6.1](#tp)
* [TOSCA-in-HEAT/Heat-Translator v. indigo-1.1](#ht)
* [OOI v. 0.3.2](#ooi)
* [Zabbix-probes v. 0.4.0](#zp)
* [Orchestrator v. 0.4.0](#orchestrator)
* [Nova-Docker v. 0.4.0](#nd)
* [FutureGateway](#fg):
  * [fgAPIServer v0.0.4](#fgapis)
  * [APIServerDaemon v0.0.4](#fgapisd)
  * [PortalSetup v0.0.3](#fgps)
* [LiferayIAM v. 1.1](#li)


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

## <a name="im"></a>Infrastructure manager v1.4.7

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
  ```sudo docker run -d -p 8899:8899 -p 8800:8800 -e IM_DATA_DB=mysql://username:password@server/db_name --name im indigodatacloud/im  ``` <br> ``` 

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
  ```apt-get update && apt-get install onedock-node``` and <br>```
  
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

#### List of RfCs
* text

* More information about bug fixes and other developments can be found on our [ADD](https://link) 

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
  ```apt-get update && apt-get install python-heat-translator```<br>```


#### Artefacts
* CentOS7
  * [heat-translator-0.5.1.dev38-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/centos7/x86_64/updates/heat-translator-0.5.1.dev38-1.noarch.rpm)
* Ubuntu14.04
  * [python-heat-translator_0.5.1.dev38-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-heat-translator_0.5.1.dev38-1_all.deb)

## <a name="ooi"></a>OOI v. 0.3.2

#### What's new
* The updated version provides only bug fixes, no new feature

#### List of RfCs
* #1624233:
  * ooi fails with 500 when deleting a volume
  * ooi fails with error 500 when deleting a volume that is attached

* More info at [Milestone-0.3.2](https://launchpad.net/ooi/+milestone/0.3.2)

#### Installation & Configuration
In order to update the packages please use:
* For CentOS 7:<br>
  ```yum clean all && yum update python-ooi```<br>
* For Ubuntu 14:04:<br>
  ```apt-get update && apt-get install python-ooi```<br>```


#### Artefacts
* CentOS7
  * [python-ooi-0.3.2-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/centos7/x86_64/updates/python-ooi-0.3.2-1.el7.centos.noarch.rpm)
* Ubuntu14.04
  * [python-ooi_0.3.2-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-ooi_0.3.2-1_all.deb)
  * [ooi-doc_0.3.2-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/ooi-doc_0.3.2-1_all.deb)
  
## <a name="zp"></a>Zabbix-probes v.

#### What's new
* text

#### List of RfCs
* text

* More information about bug fixes and other developments can be found on our [ADD](https://link) 

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the [INDIGO-IAM Deployment and Administration Guide](https://andreaceccanti.gitbooks.io/iam/content/doc/admin.html)

#### Artefacts
* Docker Container:
  * [text](https://text)


## <a name="orchestrator"></a>Orchestrator v.

#### What's new
* text

#### List of RfCs
* text

* More information about bug fixes and other developments can be found on our [ADD](https://link) 

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the [INDIGO-IAM Deployment and Administration Guide](https://andreaceccanti.gitbooks.io/iam/content/doc/admin.html)

#### Artefacts
* Docker Container:
  * [text](https://text)


## <a name="nd"></a>Nova-Docker v.

#### What's new
* text

#### List of RfCs
* text

* More information about bug fixes and other developments can be found on our [ADD](https://link) 

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the [INDIGO-IAM Deployment and Administration Guide](https://andreaceccanti.gitbooks.io/iam/content/doc/admin.html)

#### Artefacts
* Docker Container:
  * [text](https://text)



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

## <a name="li"></a>LiferayIAM v. 1.1

#### What's new
* This release improve the token validation. With this release the validation is not limited to the token obtained during the login and/or the refresh but also to token obtained by different applications. The change simplify the integration with mobile applications which can get the token from IAM.

#### List of RfCs
* [Issue-5](https://github.com/indigo-dc/LiferayIAM/issues/5) - token validation

#### Installation & Configuration
* To upgrade a Liferay the package has to be installed as the first time. The only difference is that custom values will not be overwritten.
* More information can be found in the [Administration Guide](https://indigo-dc.gitbooks.io/liferay-iam-connector/content/doc/admin.html)

#### Artefacts
* CentOS 7
  * [LiferayIAM-binary-v1.1.tgz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/tgz/LiferayIAM-binary-v1.1.tgz)
* Ubuntu14.04
  * [LiferayIAM-binary-v1.1.tgz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/LiferayIAM-binary-v1.1.tgz)

