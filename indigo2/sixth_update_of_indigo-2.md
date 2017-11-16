# Sixth Update of INDIGO-2 - 20/11/2017

The Fifth Update of INDIGO-2 release contains:
* [Analytics Portlets v. 1.0.2](#ap)
* [CloudProviderRanker v X.Y.Z](#cpr)
* [IM v. 1.6.1](#im)
* [Orchestrator v. 1.6.X-FINAL](#orchestrator)
* [udocker v. 1.2.1](#ud)
* [WaTTs v. 1.1.0](#watts)


## <a name="ap"></a>Analytics Portlets v. 1.0.2

#### What's new
* Look&feel improvements for the submission form and adaptation of the monitoring portlet code to the new response of the Future Gateway returning the tasks list.

#### List of RfCs
* New features:
  * Multimodel submission portlet: 
    * Range slider for the selection of the percentile added;
    * "Select all models” checkbox added;
    * “Look&feel improvements to the submission form layout”.
  * Monitoring portlet:
    * after an update of the Future Gateway, it was requested to adapt the management logic of the JSON response containing the list of the tasks run by the registered user."

#### Installation & Configuration
* To upgrade the portlets to a newer version, the system administrator has to replace the old jar files with the new ones into the <liferay-installation-dir>/osgi/modules folder and refresh the web portal.

#### Documentation
* [Analytics Portlets Gitbook](https://indigo-dc.gitbooks.io/analytics-portlets/content/)
* [Service Reference Card](https://indigo-dc.gitbooks.io/analytics-portlets/content/doc/service_reference.html)

#### Artefacts
* CentOS 7
  * [analytics-portlets-1.0.2.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/analytics-portlets-1.0.2.tar.gz)
* Ubuntu 16.04
  * [analytics-portlets-1.0.2.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/source/analytics-portlets-1.0.2.tar.gz)
