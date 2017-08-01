# Third Update of INDIGO-2 - XX/08/2017

The Third Update of INDIGO-2 release contains:
* [Ophidia v. 1.1.0](#ophidia)
* [Monitoring - Zabbix-probes v. 1.1](#zp)

## <a name="ophidia"></a>Ophidia v. 1.1.0

#### What's new
* This Ophidia minor release fixes several bugs and provides the following new main features: 
  * WPS-enabled oph_term; 
  * support for OpenID authZ/authN; 
  * support for FITS data format; 
  * operator for file system browsing; 
  * multi-user installation; 
  * and monitoring of workflow status.
  
#### List of RfCs
* Bugs in some operators and primitives
* Bug in strncpy calls in framework
* Bugs in primitives core library
* [Bug #15](https://github.com/OphidiaBigData/ophidia-analytics-framework/issues/15)
* [Bug #14](https://github.com/OphidiaBigData/ophidia-analytics-framework/issues/14)
* [Bug #8](https://github.com/OphidiaBigData/ophidia-server/issues/8)
* [Bug #7](https://github.com/OphidiaBigData/ophidia-server/issues/7)
* [Bug #2](https://github.com/OphidiaBigData/ophidia-primitives/issues/2)

  
* For more details please read the [Release Notes of Ophidia-1.1.0-0](https://indigo-dc.gitbooks.io/ophidia/content/release_notes.html)

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the Ophidia Upgrade Guide](https://indigo-dc.gitbooks.io/ophidia/content/upgrade.html)
* [Ophidia Service Reference Card](https://indigo-dc.gitbooks.io/ophidia/content/service_reference_card.html)

## Artefacts
Packages:
* Ubuntu 14.04
  * [ophidia-analytics-framework_1.1.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/senial-updates/main/binary-amd64/ophidia-analytics-framework_1.1.0-0_amd64.deb)
  * [ophidia-primitives_1.1.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/ophidia-primitives_1.1.0-0_amd64.deb)
  * [ophidia-server_1.1.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/ophidia-server_1.1.0-0_amd64.deb)
  * [ophidia-terminal_1.1.0-0_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/ophidia-terminal_1.1.0-0_amd64.deb)
* CentOS 7 
  * [ophidia-analytics-framework-1.1.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/ophidia-analytics-framework-1.1.0-0.el7.centos.x86_64.rpm)
  * [ophidia-primitives-1.1.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/ophidia-primitives-1.1.0-0.el7.centos.x86_64.rpm)
  * [ophidia-server-1.1.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/ophidia-server-1.1.0-0.el7.centos.x86_64.rpm)
  * [ophidia-terminal-1.1.0-0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/ophidia-terminal-1.1.0-0.el7.centos.x86_64.rpm)
  
## <a name="zp"></a>Monitoring  - Zabbix-probes v. 1.1

<!--
#### What's new
* The current update provides new probes - Mesos cluster probes which includes probes for Mesos, Marathon and Chronos

#### List of RfCs
* New feature:
  * Implemented Mesos, Chronos and Marathon probes

#### Installation & Configuration
* The Monitoring - Zabbix probes documentation has been updated and is available at https://www.gitbook.com/book/indigo-dc/monitoring/details
* New probe documentation is available at: https://indigo-dc.gitbooks.io/monitoring/content/doc/mesos.html

#### Artefacts
* CentOS7
  * [MesosZabbixProbe-1.01-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/MesosZabbixProbe-1.01-1.noarch.rpm)
* Ubuntu14.04
  * [mesos-zabbix-probe-1.01.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/mesos-zabbix-probe-1.01.deb)

-->





