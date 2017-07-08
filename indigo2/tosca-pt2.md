# TOSCA Parser v. 0.7.2 & Types v. 2.0.0

The **TOSCA Parser** is an OpenStack project and licensed under Apache 2. It is developed to parse TOSCA Simple Profile in YAML. It reads the TOSCA templates and creates an in-memory graph of TOSCA nodes and their relationship.
* more information on its Architecture can be found in the [README](https://github.com/openstack/tosca-parser/blob/master/README.rst)

The **[INDIGO TOSCA Types](https://github.com/indigo-dc/tosca-types/tree/v2.0.0)** repository  shows a YAML description of new types added in the INDIGO project to extend TOSCA Simple Profile in YAML Version 1.0 to add high level entities. In the examples directory there are a set of TOSCA documents using these types that will be supported by the INDIGO components.

* The **TOSCA Parser** now supports profile definition extensions that can be accessed via a custom tosca_definitions_version. Extensions can be added by creating a module in the "toscaparser/extensions" directory. See the ["nfv"](https://github.com/indigo-dc/tosca-parser/tree/0.7.2/toscaparser/extensions/nfv) module for an example.

## Summary:

* Updates
  * [TOSCA Parser v. 0.8.2](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo2/second_update_of_indigo-2.html#tp)


* [Release Notes TOSCA Parser v. 0.7.2 & Types v. 2.0.0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 0.7.2

<a id="id2"></a>
### What's new

Minor bugfixes:
* Fix error not considering inheritance in valid_target_types checking in functions. https://bugs.launchpad.net/tosca-parser/+bug/1672989

Supported Platforms:
* CentOS7 & Ubuntu 14:04, 16.04, OpenStack

<a id="id3"></a>
#### List of RfCs 

* https://bugs.launchpad.net/tosca-parser/+bug/1672989
* Comprehensive list of bug fixes is available [here](http://stackalytics.com/?release=mitaka&module=tosca-parser&metric=commits&company=upv)

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7 <br>
  ```$ yum clean all``` </br>
  ```$ yum install tosca-parser```

* On Ubuntu 14.04 - after setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):<br>
  ```$ apt-get update```</br>
  ```$ apt-get install python-tosca-parser```

* To upgrade to the last version you only have to install the new version using yum or apt tool:
  ```yum update tosca-parser```</br>
  ```apt install python-tosca-parser```
 
* Other installation methods are described [here](https://github.com/indigo-dc/tosca-parser/blob/master/doc/source/installation.rst)
* How To Use
  * Please refer to [doc/source/usage.rst](https://github.com/openstack/tosca-parser/blob/master/doc/source/usage.rst)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* [python-tosca-parser_0.7.2-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python-tosca-parser_0.7.2-1_all.deb)
* [tosca-parser-0.7.2-1.el7.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/tosca-parser-0.7.2-1.el7.noarch.rpm)

Tarballs:
* [tosca-types-v1.0.1.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/tosca-types-v2.0.0.tar.gz)

<a id="id6"></a>
## Documentation

* [TOSCA-parser Documentation](https://github.com/indigo-dc/tosca-parser/blob/master/README.rst)
  * [Installation](https://github.com/indigo-dc/tosca-parser/blob/0.7.2/doc/source/installation.rst)
  * [Usage](https://github.com/indigo-dc/tosca-parser/blob/0.7.2/doc/source/usage.rst)
* [TOSCA types Documentation](https://github.com/indigo-dc/tosca-types/blob/master/README.md)

<a id="id8"></a>
### Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
