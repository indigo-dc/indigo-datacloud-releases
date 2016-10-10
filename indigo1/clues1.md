# CLUES v. 0.5.1

**CLUES (CLUster Energy Saving) INDIGO Extensions**

[CLUES](https://github.com/grycap/clues) is an elasticity manager system for HPC clusters and Cloud infrastructures that features the ability to power on/deploy working nodes as needed (depending on the job workload of the cluster) and to power off/terminate them when they are no longer needed.

CLUES has been extended in the INDIGO-DataCloud project with new plugins to support the [PaaS Orchestrator](https://github.com/indigo-dc/orchestrator) and to introduce elasticity capabilities to both HTCondor and Apache Mesos (including its frameworks Chronos and Marathon). These are the plugins:

* indigo_orchestrator.py: CLUES plugin to connect with the INDIGO orchestrator.
* condor.py: CLUES plugin to connect with HTCondor.
* mesos.py: CLUES plugin to connect with Mesos, Chronos, and Marathon.

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

Highlights:
* Support for the INDIGO-DataCloud PaaS Orchestrator
* Support for HTCondor
* Support for Apache Mesos

Supported on:
* Ubuntu 14.04 / CentOS 7

<a id="id3"></a>
#### List of RfCs

* High-level development tasks coordinated via [INDIGO-DC OpenProject tasks](http://bit.ly/clues_rfc_indigo1) (internal link)

<a id="id4"></a>
### Deployment Notes

* Ansible Role: [https://github.com/indigo-dc/ansible-role-clues](https://github.com/indigo-dc/ansible-role-clues)

<a id="id5"></a>
### Known Issues
* N/A

<a id="id7"></a>
### List of Artifacts

Tarballs:
* clues-indigo-v0.5.1.tar.gz

<a id="id6"></a>
## Documentation

* [CLUES GitBook](https://indigo-dc.gitbooks.io/clues-indigo/content/)

<a id="id8"></a>
## Support

* Support via GitHub issues: [https://github.com/indigo-dc/clues-indigo/issues](https://github.com/indigo-dc/clues-indigo/issues)
* or through the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
