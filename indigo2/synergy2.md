# Synergy 1.0.1

**Synergy** is as a new extensible general purpose management OpenStack service. Its capabilities are implemented by a collection of managers which are specific and independent pluggable tasks, executed periodically or interactively. The managers can interact with each other in a loosely coupled way.
* The **Scheduler Manager** provides advanced scheduling (fairshare) capability for OpenStack. In particular it aims to address the resource utilization issues coming from the static allocation model inherent in the Cloud paradigm, by adopting the dynamic partitioning strategy implemented by the advanced batch schedulers.

Synergy is made of two packages:
* *synergy-service*: the main package
* *synergy-scheduler-manager*: plugin for synergy-service that adds the scheduler functionality. This package depends on synergy-service.

## Summary:
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

Highlights of the features provided in this version:
* New synergy service features:
  * Service configuration enhanced. Configuration parameters of service are specified on a dedicated configuration file.
* New synergy scheduler manager features:
  * Improved integration of synergy manager with Openstack. It is not nedeed to change Nova code.
  * Scheduler configuration enhanced. Configuration parameters of scheduler are specified on a dedicated configuration file.

Supported Platforms:
* Supported Operating Systems platforms:
  * CentOS 7
  * Ubuntu 16.04
* Supported CMF (Cloud Management Framework) versions:
  * OpenStack v. Newton
  * OpenStack v. Mitaka (only CentOS 7)
  * OpenStack v. Liberty (only CentOS 7)


<a id="id3"></a>
#### List of RfCs 
* https://launchpad.net/synergy-service/+milestone/1.5.1
* https://launchpad.net/synergy-scheduler-manager/+milestone/2.4.0


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
  * [python-synergy-scheduler-manager-2.4.0-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/python-synergy-scheduler-manager-2.4.0-1.el7.centos.noarch.rpm)
  * [python-synergy-service-1.5.1-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/python-synergy-service-1.5.1-1.el7.centos.noarch.rpm)
* Ubuntu 16.04
  * [python-synergy-service_1.5.1_all.deb]()
  * [python-synergy-scheduler-manager_2.4.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python-synergy-scheduler-manager_2.4.0_all.deb)

<a id="id6"></a>
## Documentation

* https://indigo-dc.gitbooks.io/synergy-doc/content/
* Service Reference Card: https://indigo-dc.gitbooks.io/synergy-doc/content/doc/service_reference_card.html
* Update/Upgrade Synergy packages: https://indigo-dc.gitbooks.io/synergy-doc/content/doc/admin.html

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)<br>
or 
  * [http://bugs.launchpad.net/synergy-scheduler-manager](http://bugs.launchpad.net/synergy-scheduler-manager)
  * [http://bugs.launchpad.net/synergy-service](http://bugs.launchpad.net/synergy-service)
