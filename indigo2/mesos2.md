# Mesos Cluster

The **INDIGO-DataCloud PaaS** relies on [Apache Mesos](http://mesos.apache.org/) for:
- managed service deployment 
- user applications execution

The instantiation of the high-available Mesos cluster is managed by 
the INDIGO *[Orchestrator](https://www.gitbook.com/book/indigo-dc/orchestrator/details)* in a fully automated 
way as soon as a user request described by a TOSCA template is submitted. Once the cluster is up and running, it can 
be re-used for successive requests.

**Mesos** is able to manage cluster resources (cpu, mem) providing isolation and sharing across distributed applications (frameworks)

**[Marathon](https://mesosphere.github.io/marathon/)** and **[Chronos](https://mesos.github.io/chronos/)** are two powerful 
frameworks that can be deployed on top of a Mesos Cluster.

Sophisticated two-level scheduling and efficient resource isolation are the key-features of the Mesos middleware that are 
exploited in the INDIGO PaaS, in order to run different workloads (long-running services, batch jobs, etc) on the same 
resources while preserving isolation and prioritizing their execution.

**INDIGO** *PaaS* uses:
- Marathon to deploy, monitor and scale *Long-Running services*, ensuring that they are always up and running.
- Chronos to run *user applications* (jobs), taking care of fetching input data, handling dependencies among jobs, rescheduling 
failed jobs.



## Summary:

* [Release Notes](#id1)
  * [What's new](#id2)
  * [Supported platforms](#id3)
  * [Deployment Notes](id4)
  * [Artifacts](id5)
  * [Documentation](id6)
  * [Support](#id8)


<a id="id1"></a>
## Release Notes

<a id="id2"></a>
## What's New
* Support for Ubuntu 16.04
* Mesos upgraded to 1.1.0
* Marathon upgraded to 1.4.1
* Chronos upgraded to 3.0.2
* marathon-consul, mesos-consul, haproxy-consul replaced with marathon-lb
* Support for persistent storage (using rex-ray driver)
* New TOSCA templates for Mesos Cluster:
  * added cluster elasticity
  * deployment on AWS 

<a id="id3"></a>
## The supported platforms*
Operating System: Ubuntu 14.04, CentOS 7, Ubuntu 16.04
Cloud Management Frameworks - any

<a id="id4"></a>
## Deployment Notes 
* Mesos Clusters can be automatically deployed using the available TOSCA templates. The deployment is performed through ansible recipes

<a id="id5"></a>
## Artifacts
* List of the affected packages and/or containers:*

* Updated ansible roles:
  * [indigo-dc.zookeeper](https://github.com/indigo-dc/ansible-role-zookeeper)
  * [indigo-dc.consul](https://github.com/indigo-dc/ansible-role-consul)
  * [indigo-dc.mesos](https://github.com/indigo-dc/ansible-role-mesos)
  * [indigo-dc.chronos](https://github.com/indigo-dc/ansible-role-chronos)
  * [indigo-dc.marathon](https://github.com/indigo-dc/ansible-role-marathon)
  * [indigo-dc.keepalived](https://github.com/indigo-dc/ansible-role-keepalived)

* New ansible roles:
  * #indigo-dc.marathon-lb](https://github.com/indigo-dc/ansible-role-marathon-lb)

* Deprecated ansible roles:
  * indigo-dc.haproxy-consul

* Updated docker images:
  * [indigodatacloud/mesos-master:1.1.0](https://hub.docker.com/r/indigodatacloud/mesos-master/tags/)
  * [indigodatacloud/marathon:1.4.1](https://hub.docker.com/r/indigodatacloud/marathon/tags/)
  * [indigodatacloud/chronos:3.0.2](https://hub.docker.com/r/indigodatacloud/chronos/tags/)


<a id="id6"></a>
## Documentation
* Link to the GitBook documentation: https://www.gitbook.com/book/indigo-dc/mesos-cluster/details


<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
