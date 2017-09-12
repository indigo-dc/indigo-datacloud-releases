# Accounting

The APEL project provides accounting for the Indigo DataCloud project. It is written in Python and uses MySQL.

## Overview
APEL Cloud Accounting can account for the usage of OpenNebula and OpenStack instances. Accounting "collectors" need to be 
installed on machines with access to the underlying Cloud infrastructure. The collectors can be found [here](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/accounting1.html).

The collectors produce "Usage Records" in the APEL-Cloud v0.2 or v0.4 message formats. Information about these format can 
be found [here](https://wiki.egi.eu/wiki/Federated_Cloud_Accounting#Documentation).

These records need to be sent as POST requests to the REST endpoint `.../api/v1/cloud/record`, where `...` is the machine 
hosting the docker image. A POST request requires an X.509 certificate to authenticate the request. The hostname, which 
should be the same as the common name (CN) contained in the X.509 certificate, must be listed as a provider 
[here](http://indigo.cloud.plgrid.pl/cmdb/service/list) for the request to be authorized.

Accepted records are summarised twice daily. These summaries can be accessed with a GET request 
to `.../api/v1/cloud/record/summary`. Summaries can be filtered using `key=value` pairs. See 
[Supported key=value pairs](doc/user.md#supported-keyvalue-pairs) for a list of valid supported `key=value` 
pairs. A GET request requires an IAM access token be included in the request. This token is then sent to the IAM to authenticate 
the ID of the service requesting access to the summary. This ID needs to be in `ALLOWED_FOR_GET` in `apel_rest/settings.py` for access 
to be authorized. See [Authorize new WP5 components to view Summaries](doc/admin.md#authorize-new-wp5-components-to-view-summaries) for 
instructions on adding service to `ALLOWED_FOR_GET`

It is currently expected that only the QoS/SLA tool will interact with these summaries.


## Summary:
* Updates
  * [Accounting v. 1.4.0](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo2/fourth_update_of_indigo-2.md#accounting)

* [Release Notes v 1.3.2](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)

<a id="id1"></a>
## Release Notes v. 1.3.2-1

<a id="id2"></a>
### What's new

* Dockerhub Image Tag: 1.3.2-1, containing:
  + APEL REST Interface version 1.3.2-1
  + APEL Server version 1.6.0-1


* New Features:

  * Allow for the Identity and Access Management (IAM) URL to be set in settings.py: https://github.com/apel/rest/pull/23
  * Add the ability to locally ban/allow POST requests: https://github.com/apel/rest/pull/26
  * Add a simple script to sender to the APEL REST interface: https://github.com/apel/rest/pull/29
  * Add ability to query summaries by GlobalUserName: https://github.com/apel/rest/pull/30
  * Upgrade to APEL 1.6.0: https://github.com/apel/rest/pull/32

* Patches, Bug Fixes and Documentation updates:

  * Reduction of duplicate log entries: https://github.com/apel/rest/pull/18
  * Clearer exception handling: https://github.com/apel/rest/pull/19
  * Example summary output to documentation: https://github.com/apel/rest/pull/21
  * Improve the install documentation: https://github.com/apel/rest/pull/24
  * Add Fetching of Certificate Revokation Lists to Docker build: https://github.com/apel/rest/pull/25
  * Explicitly set UpdateTime to update to current time on a change to the row: https://github.com/apel/rest/pull/28

<a id="id3"></a>
#### List of RfCs 

* Refactor the external call to get the list of providers to single method https://github.com/apel/rest/pull/16
* Added a link to the Service Reference Card to Summary.md: https://github.com/apel/rest/pull/17
* Removal of the method level getLogger() calls: https://github.com/apel/rest/pull/18
* Improve exception handling should provider JSON not be retrieved: https://github.com/apel/rest/pull/19
* Remove hardcoded urls from test suite: https://github.com/apel/rest/pull/20
* Add example summary output to documentation: https://github.com/apel/rest/pull/21
* Remove allowed failure of Python 2.7 tests as this version should be checked: https://github.com/apel/rest/pull/22
* Allow for the Identity and Access Management (IAM) URL to be set in settings.py: https://github.com/apel/rest/pull/23
* Improve the install documentation: https://github.com/apel/rest/pull/24
* Add Fetching of Certificate Revokation Lists to Docker build: https://github.com/apel/rest/pull/25
* Add the ability to locally ban/allow POST requests: https://github.com/apel/rest/pull/26
* Replace default cursor object with a DictCursor: https://github.com/apel/rest/pull/27
* Explicitly set UpdateTime to update to current time on a change to the row: https://github.com/apel/rest/pull/28
* Add a simple script to sender to the APEL REST interface: https://github.com/apel/rest/pull/29
* Add ability to query summaries by GlobalUserName: https://github.com/apel/rest/pull/30
* Upgrade to APEL 1.6.0: https://github.com/apel/rest/pull/32


<a id="id4"></a>
### Deployment Notes

* Installation methods
  * Running the docker image on Centos 7 and Ubuntu 16.04: https://github.com/indigo-dc/Accounting#running-the-docker-image-on-centos-7-and-ubuntu-1604
  + Kubernetes YAML files also provided.
* Upgrade methods
  * How to update an already deployed service to 1.3.2 (from 1.2.1): https://github.com/indigo-dc/Accounting/blob/dev/doc/admin.md#how-to-update-an-already-deployed-service-to-130-from-121


* For more details please see detailed [Instalation & Configuration Guide](https://indigo-dc.gitbooks.io/accounting/content/)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

* The supported platforms
  * CentOS7 and Ubuntu 16. As the software is deployed as a docker container, any OS with docker 
  should be able to deploy the Accounting Service

* Docker Container:
  * [indigodatacloud/accounting:indigo_2](https://hub.docker.com/r/indigodatacloud/accounting/)

<!--
Third-Party dependencies:
* Accounting Collectors - OpenNebula:<br>
  * [oneacct-export-0.2.6-1.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/third-party/oneacct-export-0.2.6-1.x86_64.rpm)
  * [oneacct-export_0.2.6-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/third-party/binary-amd64/oneacct-export_0.2.6-1_amd64.deb)
* Accounting Collectors - OpenStack
  * [caso_0.3.2.orig.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/caso_0.3.2.orig.tar.gz)
  * [caso_0.3.2-1ubuntu2_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/third-party/binary-amd64/caso_0.3.2-1ubuntu2_all.deb)
-->

<a id="id6"></a>
## Documentation

* [Developer guide](https://indigo-dc.gitbooks.io/accounting/content/doc/developer.html)
* [Deployment and Administration guide](https://indigo-dc.gitbooks.io/accounting/content/doc/admin.html)
* [Service Reference Card](https://indigo-dc.gitbooks.io/accounting/content/doc/admin.html)
* [User guide](https://indigo-dc.gitbooks.io/accounting/content/doc/user.html)


<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
