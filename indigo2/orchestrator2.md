# Orchestrator v. 1.3.0


This is the **Orchestrator of the PaaS layer**, a core component of the INDIGO - DataCloud project. It receives high-level deployment requests and coordinates the deployment process over the CMFs and Mesos.

## Summary:

<!--
* Updates
  * [Orchestrator v. 1.1.0-FINAL](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/second_update_of_indigo-1.html#orchestrator)
  * [Orchestrator v. 1.2.0-FINAL](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/third_update_of_indigo-1.html#orchestrator)
  * [Orchestrator v. 1.2.1-FINAL](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/sixth_update_of_indigo-1.html#orchestrator)
-->

* [Release Notes v. 1.3.0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 1.3.0

<a id="id2"></a>
### What's new

* Deploy on AWS and on Marathon, IAM token exchange and refresh, plus various enhancements and bugfixes

* More details can be found in the [CHANGELOG](New product. The changelog can be found at https://github.com/indigo-dc/orchestrator/blob/v1.3.0-FINAL/CHANGELOG.md)

Supported Platforms:

* The orchestrator can run on all the platforms that support the execution of Docker containers. It requires java >= 8


<a id="id3"></a>
#### List of RfCs 

* IAM token exchange and refresh (#96)
* SLAM REST endpoint authentication (#189)
* Selection of deployment sites through TOSCA SLA policies (#174)
* Support the deployment on AWS (#196)
* Fix the deploy never timing out (#186)
* Send the Clues client credentials through TOSCA templates (#172)
* Fix TOSCA interfaces not sent to IaaS deployers (#181)

<a id="id4"></a>
### Deployment Notes

* For clean and upgrade installations, from INDIGO-1 version, if it's the case
  * Installation guide: https://indigo-dc.gitbooks.io/indigo-paas-orchestrator/content/how_to_deploy.html
  * Upgrade guide: https://indigo-dc.gitbooks.io/indigo-paas-orchestrator/content/how_to_upgrade.html

<a id="id5"></a>
### Known Issues

* The issues are tracked at [https://github.com/indigo-dc/orchestrator/issues](https://github.com/indigo-dc/orchestrator/issues)

<a id="id7"></a>
### List of Artifacts

Docker Container:
* [indigodatacloud/orchestrator:indigo_2](https://hub.docker.com/r/indigodatacloud/orchestrator/)

<a id="id6"></a>
## Documentation

* [Orchestrator on GitBook](https://www.gitbook.com/book/indigo-dc/orchestrator/details)

* Other documentation:
  * [REST API doc](http://indigo-dc.github.io/orchestrator/restdocs/)
  * [JAVA API doc](http://indigo-dc.github.io/orchestrator/apidocs/)


<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
