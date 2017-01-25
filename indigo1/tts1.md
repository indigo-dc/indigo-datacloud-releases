# Token Translation Service & Client

The **Token Translation Service (TTS)** offers an easy way to self service credentials by the users. The TTS was necessary to develop for cases when OpenId Connect serves as the only source for authorization and identification. Therefore, the TTS bridges the gap between services that do not support OpenId Connect and the OpenId Connect provider. 

**Summary**:
* Updates
  * [TTS v. 0.4.0](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/first_update_of_indigo-1.html#tts) <br>

* [Release Notes v. v0.2.2](#id1)
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

TTS is a complete new product, so all features are new.
Created in the course of the TTS was OIDCC, a new officially listed Erlang library for OpenId Connect:
* [https://github.com/indigo-dc/oidcc](https://github.com/indigo-dc/oidcc)
* [https://openid.net/developers/libraries/](https://openid.net/developers/libraries/)

OIDCC follows also the RFC 6749, 7519

Supported Platforms:
* Centos 7
* Ubuntu14.04

<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7 

  ```$ yum clean all```

  ```$ yum install tts```

* On Ubuntu 14.04 - after setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):

  ```$ apt-get update```
  
  ```$ apt-get install tts```

* More details regarding the installation and **configuration** can be found in the [TTS Deployment And Administration Guide](https://indigo-dc.gitbooks.io/token-translation-service/content/admin.html)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* Centos 7: tts-0.2.2-1.el7.centos.x86_64.rpm
* Ubuntu14.04: tts_0.2.2-1_amd64.deb

<a id="id6"></a>
## Documentation

* [TTS on GitBook](https://indigo-dc.gitbooks.io/token-translation-service/content/)
  * [User Guide](https://indigo-dc.gitbooks.io/token-translation-service/content/user.html)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
