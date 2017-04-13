# Liferay Plugins 2.0.0


LiferayPlugins is a set of Liferay modules for the interaction with INDIGO-DataCloud services.
It consist of a set of modules for the authentication using the INDIGO-DATACLOUD IAM service,
formerly known as [LiferayIAM][1], module implementing the administration panel for the FutureGateway,
formerly known as [Admin-portlet][2], and Customisable application portlet.

In the INDIGO-DATACLOUD infrastructure model, IAM is the central authentication and authorisation
service and it has been developed inside the project to support the requirements of the supported communities.
It uses OpenID connect protocol for the authentication and OAuth for the authorisation.
More details are available in the [official documentation][3]. Therefore, all the software tools deployed for
the project must accept the IAM token directly or after a translation performed using the
[Token Translation Service][4] developed in the project.

The [FutureGateway][5] is a set of software components managing the application life-cycle on remote
infrastructure in Science Gateways. These components are responsible to interact with the remote e-Infrastructures
on behalf of the user to execute applications or deploy services.

Liferay is a web application framework and it is the main technology selected inside the
Work Package 6 to build the community portals. The functionalities provided by Liferay
make easier to build complex portals integrating different applications. These
allow users to exploit the services provided by INDIGO-DATACLOUD for their activities.
Since the portal will be the access point toward the developed services, users have to get the IAM authorisation
tokens on the portal and use it to communicate with other services.

The modules described in this guide add in Liferay the authentication, using OpenID Connect protocol,
and the management of the additional information provided by IAM such as
the user groups and others. Additionally, the modules made available the access
token for application running in the portal, or external to the portal, using the
Liferay remote APIs.


The code of the modules is based on some of the modules provided with Liferay 7.0
for the authentication with Facebook and Google and their configuration and management
is very similar.

[1]: https://github.com/FutureGateway/LiferayIAM
[2]: https://github.com/FutureGateway/Admin-portlet
[3]: https://www.gitbook.com/book/indigo-dc/iam/details
[4]: https://www.gitbook.com/book/indigo-dc/token-translation-service/details
[5]: https://www.gitbook.com/book/indigo-dc/futuregateway/details

## Summary:

<!--
* Updates
  * [LiferayIAM v. 1.1.1](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo1/second_update_of_indigo-1.md#li)
  * [LiferayIAM v. 1.1](https://github.com/indigo-dc/indigo-datacloud-releases/blob/master/indigo1/first_update_of_indigo-1.md#li)<br>
-->

* [Release Notes v. 2.0.0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)<br>

* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 2.0.0

<a id="id2"></a>
### What's new

LiferayPlugins repository include all the Liferay modules already present in LiferayIAM (now deprecated) and two new modules:
an administrative panel for the FutureGateway and a customisable application portlet to speedup the integration of new applications
in the ScienceGateway.

Supported Platforms
* Modules are supported by Liferay 7.0.x and this can run in any operating system supporting java 7.


<a id="id3"></a>
#### List of RfCs 

Bugs/Issue:
* https://github.com/indigo-dc/LiferayPlugIns/issues/1

New Development:
* Module for the admin panel named _future-gateway-admin-portlet_
* Module for the customisable application portlet named _future-gateway-customisable-application-portlet_


<a id="id4"></a>
### Deployment Notes
Installation Methods:
* Plug-in can be installed uploading the compiled module into the Liferay interface using the steps described in the documentation


* using ansible role: [https://github.com/indigo-dc/ansible-role-liferay-iam](https://github.com/indigo-dc/ansible-role-liferay-iam)
* manually using instructions on the documentation: [https://indigo-dc.gitbooks.io/liferay-iam-connector/content/doc/admin.html](https://indigo-dc.gitbooks.io/liferay-iam-connector/content/doc/admin.html)


<a id="id5"></a>
### Known Issues

* N/A
 
<a id="id7"></a>
### List of Artifacts
* com.liferay.portal.security.sso.iam.api-2.0.0.jar
* com.liferay.login.authentication.iam.web-2.0.0.jar
* com.liferay.portal.security.sso.iam.service-2.0.0.jar
* com.liferay.portal.security.sso.iam-2.0.0.jar
* com.liferay.portal.settings.authentication.iam.web-2.0.0.jar
* future.gateway.admin.portlet-2.0.0.jar
* customisable.application.portlet-2.0.0.jar


Tarballs:
* [LiferayIAM-binary-2.0.0.tgz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/LiferayPlugins-binary-2.0.0.tgz)

<a id="id6"></a>
## Documentation

* [Liferay Plugins GitBook](https://indigo-dc.gitbooks.io/liferay-plugins/content/doc/admin.html)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
