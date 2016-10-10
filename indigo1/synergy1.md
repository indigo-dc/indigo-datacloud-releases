# Synergy 1.0.1

**Synergy** is as a new extensible general purpose management OpenStack service. Its capabilities are implemented by a collection of managers which are specific and independent pluggable tasks, executed periodically or interactively. The managers can interact with each other in a loosely coupled way.
* The **Scheduler Manager** provides advanced scheduling (fairshare) capability for OpenStack. In particular it aims to address the resource utilization issues coming from the static allocation model inherent in the Cloud paradigm, by adopting the dynamic partitioning strategy implemented by the advanced batch schedulers.

Synergy is made of two packages:
* *synergy-service*: the main package
* *synergy-scheduler-manager*: plugin for synergy-service that adds the scheduler functionality. This package depends on synergy-service.

**Summary**:
* [Release Notes](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes

<a id="id2"></a>
### What's new

This is the first release of the **Synergy** service.

Highlights of the features provided in this version:
* With Synergy the OpenStack administrator can allocate a subset of resources, called dynamic resources, to be shared among different projects. Such dynamic resources are not statically allocated with fixed quotas, but are instead shared among multiple projects according to a fair share policy defined by the Cloud administrator.
* Synergy provides also a queuing mechanism for the requests that can't be immediately fullfilled: these requests will be served when the relevant resources are available.
* Synergy can manage the instantation of both Virtual Machines and containers managed via the nova-docker service.

Supported Platforms:
* the supported platforms: Ubuntu 14.04, CentOS 7
 
<a id="id3"></a>
#### List of RfCs 
*   OpenProject tasks internal links): [#2996](https://project.indigo-datacloud.eu/work_packages/2996) and [#3788](https://project.indigo-datacloud.eu/work_packages/3788)
*   OpenStack CI: [https://review.openstack.org/#/q/projects:openstack/synergy](https://review.openstack.org/#/q/projects:openstack/synergy)
*   Bug tracker on launchpad: [synergy-service](https://bugs.launchpad.net/synergy-service) and [synergy-scheduler-manager](https://bugs.launchpad.net/synergy-scheduler-manager)


<a id="id4"></a>
### Deployment Notes
* APT or YUM or [Puppet](https://github.com/indigo-dc/puppet-synergy), and some tweaks to follow in [Installation Docs](https://indigo-dc.gitbooks.io/synergy/content/doc/admin.html)
* 
<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* CentOS7
  * python-synergy-service-1.0.1-1.el7.centos.noarch.r
  * python-synergy-scheduler-manager-1.0.1-1.el7.centos.noarch.rpm
* Ubuntu 14.04
  * python-synergy-service_1.0.1_all.deb
  * python-synergy-scheduler-manager_1.0.1_all.deb

<a id="id6"></a>
## Documentation

* [Synergy on GitBook](https://indigo-dc.gitbooks.io/synergy/content/)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)<br>
or 
  * [http://bugs.launchpad.net/synergy-scheduler-manager](http://bugs.launchpad.net/synergy-scheduler-manager)
  * [http://bugs.launchpad.net/synergy-service](http://bugs.launchpad.net/synergy-service)
