# OpenStack Identity Authentication Library

There is no need anymore for a different python-keystoneauth package. The needed changes were introduced upstream, 
except for one grant type.

However, this package is now a separate plugin that can be distributed without patching the whole python-keystoneauth.

Therefore, the old python-keystoneauth* packages included in the INDIGO-1 release can be dropped, as they will be substituted 
with the following one.

**Summary**:
* [Release Notes v. 0.1.0](#id1)
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
* A plugin for the keystoneauth library, implementing the authorization code OpenID Connect grant type.
c
* Please see also the details included in [UPSTREAM CHANGELOG](http://docs.openstack.org/developer/keystoneauth/history.html#id1)
<a id="id3"></a>

#### List of RfCs 

* [https://bugs.launchpad.net/keystoneauth](https://bugs.launchpad.net/keystoneauth)

<a id="id4"></a>
### Deployment Notes
After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_2.md):
* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-newton/rdo-release-newton-4.noarch.rpm```<br>
  ```$ yum clean all```<br>
  ```$ yum install  python-keystone-oidc-authz-code```<br>
* On Ubuntu 14.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:liberty```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install  python-keystone-oidc-authz-code```<br>
or <br>
  ```$ apt-get install  python3-keystone-oidc-authz-code```<br>

<a id="id5"></a>
### Known Issues

* see list of unsolved bugs at [https://bugs.launchpad.net/keystoneauth](https://bugs.launchpad.net/keystoneauth)

<a id="id7"></a>
### List of Artifacts
The supported platforms:
* Any OpenStack client version with keystoneauth >=2.10.0 
 
Packages:
* CentOS 7
  * [python2-keystoneauth-oidc-authz-code-0.1.2-0.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/python2-keystoneauth-oidc-authz-code-0.1.2-0.el7.centos.noarch.rpm)
* Ubuntu 14.04
  * [python-keystone-oidc-authz-code_0.1.2-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python-keystone-oidc-authz-code_0.1.2-1_all.deb) 
  * [python3-keystone-oidc-authz-code_0.1.2-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python3-keystone-oidc-authz-code_0.1.2-1_all.deb)
  
<a id="id6"></a>
### Documentation
* https://indigo-dc.gitbooks.io/keystone-with-oidc-documentation/content/user-cli.html 
* [GitHub README](https://github.com/indigo-dc/keystoneauth/blob/master/README.rst)
* [Official OpenStack Identity Authentication Library Documentation](http://docs.openstack.org/developer/keystoneauth/)

<a id="id8"></a>
### Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)












