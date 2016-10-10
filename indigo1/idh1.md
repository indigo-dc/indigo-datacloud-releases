# Identity Harmonization Service (IDH) v. 1.0-2


The **INDIGO-DataCloud Identity Harmonization Service** provides a RESTful web service to link and unlink multiple local user accounts.
* Linking user accounts modifies the local user accounts so that all linked accounts represent the specified primary account with group memberships of all groups from all accounts.

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
Highlights of the [INDIGO-1 Release](https://github.com/indigo-dc/identity-harmonization/releases/tag/v1.0):
* [commits/indigo-1](https://github.com/indigo-dc/identity-harmonization/commits/v1.0)
  * This is the first release of the service
  * change oauth2 tokens to oidc tokens
  * saml delegation
  * oidc + scim user info update
  * work on harmonization algorithm
  * owrk on LDAP support
  * include local user mapping

Supported Platforms
* all with Java >= 1.8, tested on Ubuntu 14.04, Ubuntu 16.04, CentOS 7

<a id="id3"></a>
#### List of RfCs 

* [https://github.com/indigo-dc/identity-harmonization/issues](https://github.com/indigo-dc/identity-harmonization/issues)

<a id="id4"></a>
### Deployment Notes

* Build from source with maven
  * [https://indigo-dc.gitbooks.io/identity-harmonization/content/doc/building_from_sources.html](https://indigo-dc.gitbooks.io/identity-harmonization/content/doc/building_from_sources.html)
* Install via packages: identity-harmonization-0.0.1.deb, identity-harmonization-0.0.1-1.x86_64.rpm
  * [https://indigo-dc.gitbooks.io/identity-harmonization/content/doc/installing_idh.html](https://indigo-dc.gitbooks.io/identity-harmonization/content/doc/installing_idh.html)
* Run with Docker
  * [https://indigo-dc.gitbooks.io/identity-harmonization/content/doc/running_idh_as_a_docker_container.html](https://indigo-dc.gitbooks.io/identity-harmonization/content/doc/running_idh_as_a_docker_container.html)


<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts
Packages:
* identity-harmonization-0.0.1.deb
* identity-harmonization-0.0.1-1.x86_64.rpm

Docker Container:
* indigodatacloud/idh

<a id="id6"></a>
## Documentation

* [Identity Harmonisation Service GitBook](https://www.gitbook.com/book/indigo-dc/identity-harmonization/details)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
