The First Update of INDIGO-1 release contains:
* [CDMI v. 0.2](#cdmi)
* CloudInfoProvider v. 0.9.3
* FutureGateway components:
  * fgAPIServer v0.0.4
  * APIServerDaemon v0.0.4
  * PortalSetup v0.0.3
* LiferayIAM v. 1.1
* TTS v. 0.4.0


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
CentOS 7
* [cdmi-server-0.2-1.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/cdmi-server-0.2-1.x86_64.rpm)
Ubuntu 14.04
* [cdmi-server-0.2_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/cdmi-server-0.2_all.deb)
Docker Container:
* [indigodatacloud/cdmi:indigo_1](https://hub.docker.com/r/indigodatacloud/cdmi/tags/)

## CloudInfoProvider v. 0.9.3
#### What's new

#### List of RfCs

* send-to-cmdb can now delete obsolete images from the CMDB
* Re-enable and fix support of LDIF output using Mako templates
* Fix OpenStack deprecation warning
* Improve python 3 support and testing
* Improved and Updated documentation

#### Installation & Configuration
* Update has to be done using the system package manager, no manual intervention needed:<br>
``` yum clean all && yum upgrade cloud-info-provider-indigo```<br>
```apt-get update && apt-get upgrade python-cloud-info-provider-indigo```<br>
* you can find more info in the [Deployment & Administration Guide](https://indigo-dc.gitbooks.io/cloud-info-provider/content/doc/admin.html)
#### Artefacts
* CentOS7
  * [cloud-info-provider-indigo-0.9.3-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/centos7/x86_64/updates/cloud-info-provider-indigo-0.9.3-1.el7.centos.noarch.rpm)
* Ubuntu14.04
  * [python-cloud-info-provider-indigo_0.9.3_all.deb](http://repo.indigo-datacloud.eu/repository/indigo-preview/1/ubuntu/dists/trusty-updates/main/binary-amd64/python-cloud-info-provider-indigo_0.9.3_all.deb)


## FutureGateway
### fgAPIServer v0.0.4
#### What's new
#### List of RfCs
#### Installation & Configuration
#### Artefacts

### APIServerDaemon v0.0.4
#### What's new
#### List of RfCs
#### Installation & Configuration
#### Artefacts

### PortalSetup v0.0.3
#### What's new
#### List of RfCs
#### Installation & Configuration
#### Artefacts

## LiferayIAM v. 1.1
#### What's new
#### List of RfCs
#### Installation & Configuration
#### Artefacts

## TTS v. 0.4.0
#### What's new
#### List of RfCs
#### Installation & Configuration
#### Artefacts
