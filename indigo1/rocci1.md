# rOCCI Server v. 1.1.9 & Client v. 4.3.4

**rOCCI** is a framework that allows management of resources in arbitrary cloud management frameworks through the OCCI standard. 

rOCCI is a third-party product, which is already documented in the EGI Wiki: [https://wiki.egi.eu/wiki/rOCCI:ROCCI](https://wiki.egi.eu/wiki/rOCCI:ROCCI)

INDIGO contributions have so far dealt mainly with streamlining the functionality in the AWS backend, documented at [https://wiki.egi.eu/wiki/ROCCI-server_Admin_Guide#EC2_Backend](https://wiki.egi.eu/wiki/ROCCI-server_Admin_Guide#EC2_Backend)

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

* rOCCI-server 1.1.9
* rOCCI-cli 4.3.4

Supported Platforms:
* from INDiDO-DC repositories - Ubuntu 14 & CentOS7
* Other: Ubuntu 16, SL 5, SL 6, Debian 6, 7, 8

<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7 

```$ yum clean all```<br>
```$ yum install occi-server```<br>
or
```$ yum install occi-cli```<br>

* On Ubuntu 14.04 - after setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):

```$ apt-get update```<br>
```$ apt-get install occi-server```<br>
or
```$ apt-get install occi-cli```<br>

Some more details regarding the installation can be found in th [Installing_rOCCI-server Guide]( https://wiki.egi.eu/wiki/rOCCI:ROCCI-server_Admin_Guide#Installing_rOCCI-server)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts
Packages:
* CentOS 7 :
  * occi-cli-4.3.4+20160624183454-1.el7.x86_64.rpm
  * occi-server-1.1.9+20160622124300-1.el7.x86_64.rpm
* Ubuntu 14.04:
  * occi-server_1.1.9+20160622115755-1_amd64.deb
  * occi-cli_4.3.4+20160624175848-1_amd64.deb

<a id="id6"></a>
## Documentation

* [rOCCI on GitBOOK](https://www.gitbook.com/book/indigo-dc/rocci/details)
 
<a id="id8"></a>
## Support

* Please use the [rOCCI GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:ROCCI_FAQ)
