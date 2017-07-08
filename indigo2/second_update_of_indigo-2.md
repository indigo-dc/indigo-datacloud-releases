# Second Update of INDIGO-2 - 17/07/2017

The Second Update of INDIGO-2 release contains:
* [IM v. 1.5.5](#im)
* [FutureGateway](#fg):
  * [fgAPIServer v0.0.8](#fg)
  * [APIServerDaemon v0.0.8](#fg)
  * [PortalSetup v0.0.8](#fg)
  * [fgSetup v0.0.8](#fg)
* [LiferayPlugins v. 2.0.3](#li)
* [ONEdock v. 1.2](#onedock)
* [TOSCA-parser v. 0.8.2](#tp)


## <a name="cdmi"></a>Infrastructure Manager v. 1.5.5

#### What's new
* Add Support OTC.
* Support "DependsOn" TOSCA relationship.
* Enable to specify a port range in endpoint ports.
* Fix error loading an infrastructure from DB in case of invalid TOSCA.
* Fix error getting IP info in OCCI conn.
* Fix error in Azure conn creating a VM with only a public net attached.
* Fix error in contextualization nodes with private leys.
* More bugfixes and improvements...

#### List of RfCs
* Add support for instance_type in host properties: https://github.com/indigo-dc/im/issues/182.
* Support dependson relationship getting level: https://github.com/indigo-dc/im/issues/179.
* Enable to open different set of ports per VM: https://github.com/indigo-dc/im/issues/176.
* Fix error loading an infrastructure from DB in case of invalid TOSCA: https://github.com/indigo-dc/im/issues/174.
* Enable to specify a port range in endpoint ports: https://github.com/indigo-dc/im/issues/172.
* Fix error: source_range in ports property of endpoint capability is not correctly processed: https://github.com/indigo-dc/im/issues/170.
* Improve IAM token local validation enhancement: https://github.com/indigo-dc/im/issues/148.
* Fix error getting IP info in OCCI conn: https://github.com/grycap/im/issues/331.
* Enable to reset the add_public_ip_count in the OCCI/OST conns: https://github.com/grycap/im/issues/334.
* Improve Azure instance_type selection: https://github.com/grycap/im/issues/335.
* Improve GCE instance type selection: https://github.com/grycap/im/issues/336.
* Manage DNS records in EC2, Azure and GCE connectors: https://github.com/grycap/im/issues/340.
* Fix error in Azure conn creating a VM with only a public net attached: https://github.com/grycap/im/issues/342.
* Fix error in contextualization nodes with private keys: https://github.com/grycap/im/issues/313.
* Improve OpenNebula conn with new ver. 5 functions as SGs: https://github.com/grycap/im/issues/319.
* Improve error mesage in case of invalid proxy in OCCI conn: https://github.com/grycap/im/issues/317.
* Fix errors in Azure connector : https://github.com/grycap/im/issues/323, https://github.com/grycap/im/issues/324.
* Fix errors with python3 https://github.com/grycap/im/issues/278, https://github.com/grycap/im/issues/284
* Fix error in some SFTP functions in SSH class. https://github.com/grycap/im/issues/280
* Change default value of REMOTE_CONF_DIR to /var/tmp. https://github.com/grycap/im/issues/283
* Enable to specify a port range in outports. https://github.com/grycap/im/issues/285
* Add functions to create VM snapshots. https://github.com/grycap/im/issues/152
* Fix error in OCCI conn setting public key. https://github.com/grycap/im/issues/292
* Improve SG management in connectors EC2 and OpenStack. https://github.com/grycap/im/issues/296
* Add support to OTC. https://github.com/grycap/im/issues/302
* In case of hybrid infrastructures some connector will not remove all resources. https://github.com/grycap/im/issues/288
* Select a random pool in case of OpenStack site in OCCI conn. https://github.com/grycap/im/issues/306
* Detach volumes before removing it in OCCI conn. https://github.com/grycap/im/issues/305
* Support OpenStack calls with VOMS proxies. https://github.com/grycap/im/issues/310

#### Installation & Configuration
*The supported platforms
  * CentOS 7
  * Ubuntu 14.04
  * Ubuntu 16.04

* To upgrade to the last version first you have to install the new version using yum or apt tool:</br>
  ``` yum update IM RADL ``` <7br>
  ``` apt install python-im python-radl ``` </br>

* To update a container the user has to:
  * Stop the old container:</br>
    ``` sudo docker stop im ``` </br>
  * Remove the old container:</br>
    ``` sudo docker rm im ``` </br>
  * Pull the new image version:</br>
    ``` sudo docker pull indigodatacloud/im ``` </br>
  * Start the new version:</br>
    ``` sudo docker run -d -p 8899:8899 -p 8800:8800 -e IM_DATA_DB=mysql://username:password@server/ ``` </br>
        
#### Artefacts
* CentOS 7
  * [IM-1.5.5-1.el7.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/IM-1.5.5-1.el7.noarch.rpm)
* Ubuntu 14.04
  * [python-im_1.5.5-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/binary-amd64/python-im_1.5.5-1_all.deb)
* Ubuntu 16.04
  * [python-im_1.5.5-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/python-im_1.5.5-1_all.deb)
* Docker Container:
  * [indigodatacloud/cdmi:indigo_2](https://hub.docker.com/r/indigodatacloud/im/tags/)

## <a name="fg"></a>FutureGateway
### <a name="fgas"></a>fgAPIServer, APIServerDaemon, PortalSetup &fgSetup v. 0.0.8
#### What's new
* This update provides mainly fixes of several bugs discovered after the electric indigo release. Few changes have been added to the installation especially taking in mind newcomers allowing them to improve the user experience while installing and testing the environment.

  * *fgAPIServer* - The front-end is the most impacted component in this release. It provides the implementation of new API specs concerning Applications and Infrastructure changes. Other minor code refinements have been included as well.
  * *APIServerDaemon* - It only contains a fix related to LiferayPTV service handling. ToscaIDC logging has been modified during resource creation.
  * *PortalSetup* - Contain modified fgSetup.sh files to point the v0.0.8 release
  + *fgSetup* - Contain a revised ansible role which supports both Ubuntu 14.04 and 16.0x and fgcommons.yml file fixed to point the v0.0.8 release

#### List of RfCs

*fgAPIServer
  * Empty authorization token causes error 500 instead of 401 https://github.com/indigo-dc/fgAPIServer/issues/51
  * Wrong parameter in Applications https://github.com/indigo-dc/fgAPIServer/issues/50
  * Missed links https://github.com/indigo-dc/fgAPIServer/issues/31
  * Not displaying properly tasks/<task_id> when specifying user=? filter https://github.com/indigo-dc/fgAPIServer/issues/49
  
#### Installation & Configuration
* Updating existing components:

  * *APIServerDaemon* - Stop the APIServerDaemon stopping Tomcat or the APIServerDaemon webapp. Rename the current APIServerDaemon directory to keep a safe copy of the old version (you will also need some files from it). Extract from GitHub the new APIServerDaemon with a clone command. From the older folder, copy the whole lib/ directory. Compile the code executing 'ant all'. At the end of the compilation, copy the generated war file under dist directory into the tomcat webapps folder and wait until the new APIServerDaemon web application is successfully deployed.
* *fgAPIServer* - Stop apache or any WSGI engine supporting the fgAPIServer execution; stop any other stand-alone execution instance (if any). Rename the fgAPIServer folder to keep safe the older version (you may need from it the fgapiserver.conf file as well as the apps folder). Extract from GitHub the new version cloning the fgAPIServer sources. Recover from the older version the fgapiserver.conf file and the apps folder. Restart the WSGI engine (apache for instance) and any other stand-alone instance if necessary.
* *PortalSetup* - It just contain the new revised contextualization script to install FG on top of an EGI FedCloud node. The script generated by the contextualization file can be used as reference for stand-alone installations as well.

#### Artefacts
* CentOS7
  * [fgAPIServer-v0.0.8.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/fgAPIServer-v0.0.8.tar.gz)
  * [APIServerDaemon-v0.0.8.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/APIServerDaemon-v0.0.8tar.gz)
  * [PortalSetup-v0.0.8.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/PortalSetup-v0.0.8.tar.gz)
* Ubuntu16.04
  * [fgAPIServer-v0.0.8.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/fgAPIServer-v0.0.8tar.gz)
  * [APIServerDaemon-v0.0.8.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/APIServerDaemon-v0.0.8.tar.gz)
  * [PortalSetup-v0.0.8.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/trusty-updates/main/source/PortalSetup-v0.0.8.tar.gz)
