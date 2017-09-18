# CLUES 

**CLUES (CLUster Energy Saving) INDIGO Extensions**

[CLUES](https://github.com/grycap/clues) is an elasticity manager system for HPC clusters and Cloud infrastructures that features the ability to power on/deploy working nodes as needed (depending on the job workload of the cluster) and to power off/terminate them when they are no longer needed.

CLUES has been extended in the INDIGO-DataCloud project with new plugins to support the [PaaS Orchestrator](https://github.com/indigo-dc/orchestrator) and to introduce elasticity capabilities to both HTCondor and Apache Mesos (including its frameworks Chronos and Marathon). These are the plugins:

* indigo_orchestrator.py: CLUES plugin to connect with the INDIGO orchestrator.
* condor.py: CLUES plugin to connect with HTCondor.
* mesos.py: CLUES plugin to connect with Mesos, Chronos, and Marathon.

## Summary:
* [Release Notes v. 0.9.0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 0.9.0

<a id="id2"></a>
### What's new

Highlights of INDIGO-2 version:
* Add IAM token management

Supported on:
* Ubuntu 14.04, 16.04 / CentOS 7

<a id="id3"></a>
#### List of RfCs

* IAM token expiration -> https://github.com/indigo-dc/clues-indigo/issues/19
* Manage authentication for Mesos/Marathon/Chronos endpoints -> https://github.com/indigo-dc/clues-indigo/issues/20
* Orchestrator plugin does not correctly manage more than one master node -> https://github.com/indigo-dc/clues-indigo/issues/21
* Enable to detect mesos slaves by ip -> https://github.com/indigo-dc/clues-indigo/issues/23
* CPU and memory of mesos nodes are hardcoded when the nodes are off -> https://github.com/indigo-dc/clues-indigo/issues/25
* CPU and Memory used are not updated -> https://github.com/indigo-dc/clues-indigo/issues/26
* Orchestrator plugin does not correct manage SSL connections -> https://github.com/indigo-dc/clues-indigo/issues/29
* Problems updating infrastructure with queued requests-> https://github.com/indigo-dc/clues-indigo/issues/33
* Error in orchestrator plugin -> https://github.com/indigo-dc/clues-indigo/issues/35
* Error detecting unexisting jobs in mesos -> https://github.com/indigo-dc/clues-indigo/issues/45
+ Error getting correct uuid when powering on a new node -> https://github.com/indigo-dc/clues-indigo/issues/42

<a id="id4"></a>
### Deployment Notes

* Ansible Role: [https://github.com/indigo-dc/ansible-role-clues](https://github.com/indigo-dc/ansible-role-clues)

<a id="id5"></a>
### Known Issues
* N/A

<a id="id7"></a>
### List of Artifacts

Tarballs:
* [clues-indigo-v0.9.0.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/clues-indigo-v0.9.0.tar.gz)

<a id="id6"></a>
## Documentation

* [CLUES GitBook](https://indigo-dc.gitbooks.io/clues-indigo/content/)

<a id="id8"></a>
## Support

* Support via GitHub issues: [https://github.com/indigo-dc/clues-indigo/issues](https://github.com/indigo-dc/clues-indigo/issues)
* or through the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
