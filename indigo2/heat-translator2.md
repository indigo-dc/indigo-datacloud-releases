# HEAT-translator

**Heat-Translator** is an Openstack project, with contributions through the INDIGO - DataCloud project, licensed under Apache 2. 
* It is a command line tool which takes non-Heat templates as an input and produces a Heat Orchestration Template (HOT) which can be deployed by Heat. Currently the development and testing is done with an aim to translate OASIS Topology and Orchestration Specification for Cloud Applications (**TOSCA)** templates to HOT. However, the tool is designed to be easily extended to use with any format other than TOSCA.

## Summary:

<!--
* Updates
  * [HEAT-translator v. indigo-1.1](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/second_update_of_indigo-1.html#ht)
-->

* [Release Notes v. 0.5.4-](#id1)
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

Highlights of the [Heat-Translator INDIGO-2 Release](https://github.com/MatMaul/heat-translator/releases):
* Mainly bugfixes, most of the changes needed for the examples to work on OpenStack are in the ansible recipes and the templates.

Supported Platforms:
* Tested with centos7+rdo and ubuntu14.04+ppa:mitaka-testing.

<a id="id3"></a>
#### List of RfCs 

* Bugs: https://bugs.launchpad.net/heat-translator


<a id="id4"></a>
### Deployment Notes

* Details on how to use the Heat Translator can be found at [doc/source/usage.rst]( https://github.com/openstack/heat-translator/blob/master/doc/source/usage.rst)

<a id="id5"></a>
### Known Issues
* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* [heat-translator-0.5.1.dev43-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/heat-translator-0.5.1.dev43-1.noarch.rpm)
* [python-heat-translator_0.5.1.dev43-1_all-xenial.deb)](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python-heat-translator_0.5.1.dev43-1_all-xenial.deb)

<a id="id6"></a>
## Documentation

* Documentation: http://docs.openstack.org/developer/heat-translator/
* Launchpad: https://launchpad.net/heat-translator
* Blueprints: https://blueprints.launchpad.net/heat-translator


<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
* IRC Channel: #openstack-heat-translator
