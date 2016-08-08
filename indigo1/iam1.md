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

Highlights of the first release in INDIGO-1:
* **Authentication**: The IAM supports the authentication mechanisms defined by the INDIGO AAI architecture (SAML, X.509, OpenID connect)
* **Session management**: the IAM provides session management functionality. Sessions are used to provide single sign-on and logout functionality to client applications and services.
* **Enrollment**: The IAM provides enrollment and registration functionalities, so that users can join groups/collaborations according to user-defined flows.
* **Attribute and identity management**: The IAM provides services to manage group membership, attributes assignment, to group/collaboration administrators and the ability, for users, to consolidate multiple identities in a single INDIGO identity.
* **User provisioning**: the IAM provides endpoints to provision information about users identities to other services, so that consistent local account provisioning, for example, can be implemented
* **Policy definition, distribution and evaluation**: the IAM provides tools and APIs to
  * define authorization policies on distributed resources
  * define policy distribution flows so that policies can be imported from other IAM instances
  * evaluate policies against a request context and issue an authorization decision

Supported Platforms:
* The **IAM** service is currently distributed as a docker image from Dockerhub, so in order to run the service, you will need Docker v. 1.11.1 or greater. If you want to use docker-compose to deploy the service, you will also need docker-compose v.1.7.0 or greater.

<a id="id3"></a>
#### List of RfCs 

* [GitHub Issues](https://github.com/indigo-iam/iam/issues)

<a id="id4"></a>
### Deployment Notes

* Please read the [Deployment and Administration guide](https://indigo-dc.gitbooks.io/iam/content/doc/admin.html)

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