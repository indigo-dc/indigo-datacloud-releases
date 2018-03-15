# Sixth Update of INDIGO-2 - 20/11/2017

The Fifth Update of INDIGO-2 release contains:
* [Analytics Portlets v. 1.0.2](#ap)
* [CloudProviderRanker v X.Y.Z](#cpr)
* [IM v. 1.6.1](#im)
* [Orchestrator v. 1.6.X-FINAL](#orchestrator)
* [udocker v. 1.1.1](#ud)
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


## <a name="ud"></a>udocker v. 1.1.1

#### What's new
* udocker 1.1.1 


#### List of RfCs

* Bug fixes and new features:
  * New execution engine using singularity
  * Updated documentation with OpenMPI information and examples
  * Additional unit tests
  * Redirect messages to stderr
  * Improved parsing of quotes in the command line
    * closes: #87
  * Allow override of the HOME environment variable
  * Allow override of libfakechroot.so at the container level
  * Automatic selection of libfakechroot.so from container info
  * Improve automatic install
  * Enable resetting prefix paths in Fn modes in remote hosts
  * Do not set AF_UNIX_PATH in Fn modes when the host /tmp is a volume
  * Export containers in both docker and udocker format
  * Import containers docker and udocker format
  * Load, import and export to/from stdin/stdout
  * Clone existing containers
  * Support for TCP/IP port remap in execution modes Pn
  * Fix run with basenames failing
    * closes: #89
  * Allow run as root flag
    * closes: #91

#### Installation & Configuration
* Information for installation and upgrade is available in the GitBook documentation at
https://indigo-dc.gitbooks.io/udocker/content/doc/installation_manual.html

#### Artefacts
* Binary Tarball
  * [udocker-1.1.1.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/udocker-1.1.1.tar.gz)
