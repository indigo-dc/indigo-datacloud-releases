# QoS/SLA Management Service v. 1.1.1

This service allows the handshake between a userand a site on a given SLA and gives the Orchestrator/Ranker useful information to make decisions on tasks scheduling according to valid SLAs.
Moreover, it describes the QoS that a specific user/group has, both over a given site  or  generally  in  the  PaaS  as  a  whole; this includes a priority of a given user, the capability to access to different QoS at each site (Gold, Silver, Bronze services). 
Finally, it provides information on the configuration of the features / configuration / endpoints / closeness of the available resources


The **SLA (Service Level Agreement) Manager** is the service for QoS negotiations developed through the INDIGO - Data Cloud project. It is:
* providing a web-interface that allows customers to manage SLAs with service providers and describe its preferences
* enabling REST API for access both preferences and SLAs

## Summary:

* [Release Notes v. 1.1.1](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 1.1.1

<a id="id2"></a>
### What's new

New Features:
* SLA for storage
* Groups support in SLA scope
* Improved GUI
* QoS improvements

Depends on other components features:
* CMDB
* ONEDATA
* IAM

Other componets dependent on new features:
* Orchestrator

<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

* Please carefully read the [Installation Documentation](https://indigo-dc.gitbooks.io/slam/content/installation.html)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Docker Container:
* [indigodatacloud/slam:indigo_2](https://hub.docker.com/r/indigodatacloud/slam/tags/)
* [indigodatacloudapps/slam-webapp:indigo_1](https://hub.docker.com/r/indigodatacloudapps/slam-webapp/)

<a id="id6"></a>
## Documentation

* [SLA Manager in GitBook](https://indigo-dc.gitbooks.io/slam/content/)


<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
