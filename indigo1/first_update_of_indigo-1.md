# First Update of INDIGO-1

The First Update of INDIGO-1 release contains:
* [CDMI v. 0.2](#cdmi)
* [CloudInfoProvider v. 0.9.3](#cip)
* [FutureGateway](#fg):
  * [fgAPIServer v0.0.4](#fgapis)
  * [APIServerDaemon v0.0.4](#fgapisd)
  * [PortalSetup v0.0.3](#fgps)
* [LiferayIAM v. 1.1](#li)
* [TTS v. 0.4.0](#tts)


## <a name="cdmi"></a>CDMI v. 0.2

#### What's new
* Improving the CDMI specification compliance, fixing authentication and file-system issues

#### List of RfCs
* [Issue 63](https://github.com/indigo-dc/CDMI/issues/63): Querying for capability of a file with invalid Bearer token work - incorrect behavior
* [Issue 62](https://github.com/indigo-dc/CDMI/issues/62): Querying for capability with an invalid token works - incorrect behaviour
* [Issue 56](https://github.com/indigo-dc/CDMI/issues/56): NPE on querying capabilities of a file, when file not in the root directory
* [Issue 55](https://github.com/indigo-dc/CDMI/issues/55): NPE on querying the capability of a dataobject when it has been uploaded through an out of band mechanism
* [Issue 54](https://github.com/indigo-dc/CDMI/issues/54): Changing capability on a data object without querying for its capabilities first returns some JSON (possibly incorrect behavior)
* [Issue 53](https://github.com/indigo-dc/CDMI/issues/53): Changing Capability of an Object returns 409 Conflict
* [Issue 52]((https://github.com/indigo-dc/CDMI/issues/52)): Incorrect JSON returned on querying capability
* [Issue 51](https://github.com/indigo-dc/CDMI/issues/51): AccessDeniedExceptions on clean startup of CDMI server
* [Issue 50](https://github.com/indigo-dc/CDMI/issues/50): Children not found on querying capabilities with dCacheStorageBackend
* [Issue 49](https://github.com/indigo-dc/CDMI/issues/49): Null Pointer Exception on getting the current capability of a file or directory
* [Issue 38](https://github.com/indigo-dc/CDMI/issues/38): Reopened: Incorrect response when Unauthorised expected
* [Issue 33](https://github.com/indigo-dc/CDMI/issues/33): Incorrect response when Unauthorised expected

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the [CDMI-QoS Deployment and Administration Guide](https://indigo-dc.gitbooks.io/cdmi-qos/content/doc/administrator.html)

#### Artefacts
* CentOS 7
  * [cdmi-server-0.2-1.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/cdmi-server-0.2-1.x86_64.rpm)
* Ubuntu 14.04
  * [cdmi-server-0.2_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/cdmi-server-0.2_all.deb)
* Docker Container:
  * [indigodatacloud/cdmi:indigo_1](https://hub.docker.com/r/indigodatacloud/cdmi/tags/)

## <a name="cip"></a>CloudInfoProvider v. 0.9.3

#### What's new
* Implement cleaning of obsolete images from CMDB, fix OpenStack provider deprecation warnings and vebose output, fix and improve LDIF output, python3 support, testing and documentation.

#### List of RfCs
* send-to-cmdb can now delete obsolete images from the CMDB
* Re-enable and fix support of LDIF output using Mako templates
* Fix OpenStack deprecation warning
* Improve python 3 support and testing
* Improved and Updated documentation

#### Installation & Configuration
* A complete update of the node hosting the service can to be done using the system package manager, no manual intervention needed:<br>
  * For CentOS 7:<br>
  ``` yum clean all && yum update```<br>
  * For Ubuntu 14:04:<br>
  ```apt-get update && apt-get upgrade```<br>
* In order to update just the cloud-info-provider:<br>
  * For CentOS 7:<br>
  ``` yum clean all && yum update cloud-info-provider-indigo```<br>
  * For Ubuntu 14:04:<br>
  ```apt-get update && apt-get install -V python-cloud-info-provider-indigo```<br>
* For more info please read the [Deployment & Administration Guide](https://indigo-dc.gitbooks.io/cloud-info-provider/content/doc/admin.html)

#### Artefacts
* CentOS7
  * [cloud-info-provider-indigo-0.9.3-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/cloud-info-provider-indigo-0.9.3-1.el7.centos.noarch.rpm)
* Ubuntu14.04
  * [python-cloud-info-provider-indigo_0.9.3_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-cloud-info-provider-indigo_0.9.3_all.deb)


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

## <a name="tts"></a>TTS v. 0.4.0

#### What's new
* Several new features like new plugins (basic x509 & info), configurable OpenID Connect scopes per provider, updated documentation, several minor improvements and bug fixes 

#### List of RfCs
* New Features:
  * Basic X.509 CA: a new plugin that sets up a self-signed basic CA
  * [Issue-150](https://github.com/indigo-dc/tts/issues/150) - Info Plugin, showing the information provided by the OpenId Connect Provider, this is mostly useful for developers of plugins, but might also interesting for users to see which informations the TTS receives about them.
  * [Issue - 132](https://github.com/indigo-dc/tts/issues/132) - Configurable OpenID Connect scopes per provider: to be able to request as little information as possible per provider, yet more when needed
  * [Issue-105](https://github.com/indigo-dc/tts/issues/105) - Updated to the latest OpenId Connect library OIDCC: the library now handles the complete login process, the TTS just gets a success or failed message
  * [Issue-156](https://github.com/indigo-dc/tts/issues/156) - Updated/Enhanced Documentation
  * [Issue-106](https://github.com/indigo-dc/tts/issues/106)Internal Refactor to increase test coverage and code reusability
* Minor Improvements:
  * [Issue-128](https://github.com/indigo-dc/tts/issues/128) - creation time now in RFC1132 format
  * [Issue-160](https://github.com/indigo-dc/tts/issues/160) - enforce content type on REST interface
  * [Issue-161](https://github.com/indigo-dc/tts/issues/161) - store credentials for the REST interface only a certain amount of time and then automatically delete them
* Bugs Fixed:
  * [Issue-130](https://github.com/indigo-dc/tts/issues/130),[Issue-138](https://github.com/indigo-dc/tts/issues/138) - basic-idh had an issue in the default configuration
  * [Issue-135](https://github.com/indigo-dc/tts/issues/135), [Issue-140](https://github.com/indigo-dc/tts/issues/140) - idh-single-user had issues with different providers, caused by local user cache

#### Installation & Configuration
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
