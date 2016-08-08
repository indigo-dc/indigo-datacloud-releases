# INDIGO IAM v0.3.0

Summary:
* [Release Notes](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [Documentation](#id6)
  * [List of Artifacts](#id7)
  * [Support](#id8)


<a id="id1"></a>
## Release Notes

The **Identity and Access Management Service** provides a layer where identities, enrollment, group membership and other attributes and authorization policies on distributed resources can be managed in an homogeneous way, supporting the federated authentication mechanisms supported by the INDIGO AAI. The IAM service provides user identity and policy information to services so that consistent authorization decisions can be enforced across distributed services.

<a id="id2"></a>
### What's new

This is the first public release of the INDIGO Identity and Access Management
Service.

The IAM is an OpenID-connect identity provider which provides:
* OpenID-connect and OAuth client registration and management (leveraging and extending the MitreID connect server functionality
* SCIM user and group provisioning and management
* A partial implementation of the OAuth Token Exchange draft standard for OAuth token delegation and impersonation

Supported Platforms:
* The **IAM** service is currently distributed as a docker image from Dockerhub, so in order to run the service, you will need Docker v. 1.11.1 or greater. If you want to use docker-compose to deploy the service, you will also need docker-compose v.1.7.0 or greater.

<a id="id3"></a>
#### List of RfCs 

* [GitHub Issues](https://github.com/indigo-iam/iam/issues)

<a id="id4"></a>
### Deployment Notes

* Please read the [Deployment and Administration guide](https://indigo-dc.gitbooks.io/iam/content/doc/admin.html)
* Documentation on how to build and run the service can be found in the [IAM GitBook manual](https://www.gitbook.com/book/andreaceccanti/iam/details) or on [Github](https://github.com/indigo-iam/iam/blob/master/SUMMARY.md).

<a id="id5"></a>
### Known Issues

* N/A

<a id="id6"></a>
### Documentation

* [INDIGO IAM GitBook](https://indigo-dc.gitbooks.io/iam/content/)

<a id="id7"></a>
### List of Artifacts

Docker Container:
* i[ndigodatacloud/iam-login-service:indigo_1](https://hub.docker.com/r/indigodatacloud/iam-login-service/)

<a id="id8"></a>
### Support

* [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
* [INDIGO AAI Task Force mailing list](https://lists.indigo-datacloud.eu/sympa/sigrequest/indigo-aai-tf)
* [INDIGO AAI on Slack](https://indigo-aai.slack.com/)