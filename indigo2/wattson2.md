# Token Translation Client - WaTTSon v. 1.1.0

The WaTTS (INDIGO Token Translation Service) command line client

## Summary:

<!--
* Updates
  * [TTS v. 0.4.0](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/first_update_of_indigo-1.html#tts) <br>
-->

* [Release Notes v. v 1.1.0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v.1.1.0

<a id="id2"></a>
### What's new

* ready for WaTTS 1.0.0
* dedicated Docker Container to run on e.g. MacOS X

Supported Platforms:
* Centos 7
* Ubuntu 14.04, 16.04

<a id="id3"></a>
#### List of RfCs 

* have a docker build script: https://github.com/indigo-dc/wattson/issues/16 

<a id="id4"></a>
### Deployment Notes

* Installation methods - apt/yum install
* Update: Just a command line client, a single binary, not needed

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7 

  ```$ yum clean all```

  ```$ yum install wattson```

* On Ubuntu 14.04 - after setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):

  ```$ apt-get update```
  
  ```$ apt-get install wattson```

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* Centos 7: [wattson-1.1.0.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/wattson-1.1.0.el7.centos.x86_64.rpm)
* Ubuntu14.04: [wattson-1.1.0-amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/wattson-1.1.0-amd64.deb)
* Docker container: [indigodatacloud/wattson:indigo_2](https://hub.docker.com/r/indigodatacloud/wattson/tags/)

<a id="id6"></a>
## Documentation

* [WaTTSon on GitBook](https://indigo-dc.gitbooks.io/wattson/content/)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
