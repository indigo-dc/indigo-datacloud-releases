# Orchestrator 


This is the **Orchestrator of the PaaS layer**, a core component of the INDIGO - DataCloud project. It receives high-level deployment requests and coordinates the deployment process over the CMFs and Mesos.

**Summary**:
* Updates
  * [Orchestrator v. 1.1.0-FINAL](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/second_update_of_indigo-1.html#orchestrator)
  * [Orchestrator v. 1.2.0-FINAL](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/third_update_of_indigo-1.html#orchestrator)
  * [Orchestrator v. 1.2.1-FINAL](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/sixth_update_of_indigo-1.html#orchestrator)
  
* [Release Notes v. 1.0.0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 1.0.0

<a id="id2"></a>
### What's new

This is the first release o the Orchestrator. 
* features:
  * Support for the Data Location Scheduling (OneData)
  * Support for Configuration Database for the IaaS Resources
  * Cloud Provider choice (SLAM, CMDB, Monitoring, CPR integration)
  * Ranking of the resources via Cloud Provider Ranker
  * Implement AAI support and IM authentication relay 
  * Use selected Cloud Provider for deploy/update/undeploy
  * Image ID substitution in TOSCA template (to support multiple CP
* changes:
  * Removed OneDock-specific authentication
* fixes:
  * TOSCA: required inputs with default value not handled correctly
  * Provider choice override for Chronos single provider 


* More details can be found in the [CHANGELOG](New product. The changelog can be found at https://github.com/indigo-dc/orchestrator/blob/v1.0.0-FINAL/CHANGELOG.md)

Supported Platforms:
* The orchestrator can run on all the platforms that support the execution of Docker containers or Wildfly 9


<a id="id3"></a>
#### List of RfCs 

* See [CHANGELOG](New product. The changelog can be found at https://github.com/indigo-dc/orchestrator/blob/v1.0.0-FINAL/CHANGELOG.md) for a complete list of solved issues

<a id="id4"></a>
### Deployment Notes

* The reference on how to build the code, the docker container and how to run it is available at [https://github.com/indigo-dc/orchestrator/blob/releases/1-0-stable/README.md](https://github.com/indigo-dc/orchestrator/blob/releases/1-0-stable/README.md)
* 
<a id="id5"></a>
### Known Issues

* The issues are tracked at [https://github.com/indigo-dc/orchestrator/issues](https://github.com/indigo-dc/orchestrator/issues)

<a id="id7"></a>
### List of Artifacts

Docker Container:
* [indigodatacloud/orchestrator:indigo_1](https://hub.docker.com/r/indigodatacloud/orchestrator/)

<a id="id6"></a>
## Documentation

* [Orchestrator on GitBook](https://www.gitbook.com/book/indigo-dc/orchestrator/details)

* Other documentation:
  * [REST API doc](http://indigo-dc.github.io/orchestrator/restdocs/)
  * [JAVA API doc](http://indigo-dc.github.io/orchestrator/apidocs/)


<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
