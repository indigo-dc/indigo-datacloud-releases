# Liferay IAM


*[LiferayIAM](https://indigo-dc.gitbooks.io/liferay-iam-connector/content/)* is a set of modules for authentication using INDIGO-DATACLOUD IAM service.

These modules implement the authentication using OpenID Connect protocol and they are able to manage the additional information provided by IAM such as the user groups and others. Additionally, the modules made available the access token for application running in the portal, or external to the portal, using the remote APIs.

The code of the modules is based on some of the modules provided with Liferay 7.0 for the authentication with facebook and google and their configuration and management is very similar.

**Summary**:
* Updates
  * [LiferayIAM v. 1.1.1](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo1/second_update_of_indigo-1.md#li)
  * [LiferayIAM v. 1.1](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo1/first_update_of_indigo-1.md#li)<br>

* [Release Notes v. 1.0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)<br>

* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 1.0

<a id="id2"></a>
### What's new

Specific product release notes for the version included in INDIGO-1 release
* The package introduces OpenIdConnect authentication and basic authorisation using INDIGO-Datacloud IAM service on Liferay
* Provides APIs to portlet and other applications running with Liferay for managing the OAuth token. These allow to get the token and check the validity.

Supported Platforms
* Any Operating System with Java8 and Liferay 7.0.x


<a id="id3"></a>
#### List of RfCs 

* N/A


<a id="id4"></a>
### Deployment Notes
Installation Methods:
* using ansible role: [https://github.com/indigo-dc/ansible-role-liferay-iam](https://github.com/indigo-dc/ansible-role-liferay-iam)
* manually using instructions on the documentation: [https://indigo-dc.gitbooks.io/liferay-iam-connector/content/doc/admin.html](https://indigo-dc.gitbooks.io/liferay-iam-connector/content/doc/admin.html)


<a id="id5"></a>
### Known Issues

* N/A
 
<a id="id7"></a>
### List of Artifacts

Tarballs:
* LiferayIAM-binary-v1.0.tgz

<a id="id6"></a>
## Documentation

* [LiferayIAM GitBook](https://www.gitbook.com/book/indigo-dc/liferay-iam-connector/details)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
