# Token Translation Service (WaTTS) v. 1.0.0

The **Token Translation Service (TTS)** offers an easy way to self service credentials by the users. The TTS was necessary to develop for cases when OpenId Connect serves as the only source for authorization and identification. Therefore, the TTS bridges the gap between services that do not support OpenId Connect and the OpenId Connect provider. 

## Summary:

<!--
* Updates
  * [TTS v. 0.4.0](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/first_update_of_indigo-1.html#tts) <br>
-->

* [Release Notes v. v 1.0.0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 1.0.0

<a id="id2"></a>
### What's new

WaTTS has been changed to a pure REST server with a JavaScript SPA, so both, the web and the command line clients use the same interface.
WaTTS got many new features the most important to mention are:
* one single configuration file
* OpenID Connect certified relaying party library
* authorization based on OpenID Connect information

Supported Platforms:
* Centos 7
* Ubuntu14.04

<a id="id3"></a>
#### List of RfCs 

* Passing the Version of WaTTS to the plugins https://github.com/indigo-dc/tts/issues/183
* shorten session ids: https://github.com/indigo-dc/tts/issues/180
* change WaTTS into a pure REST server, no html rendering at server side (added a javascript SPA) https://github.com/indigo-dc/tts/issues/180
* switch so single configuration file that gets validated before starting WaTTS https://github.com/indigo-dc/tts/issues/107, https://github.com/indigo-dc/tts/issues/240, https://github.com/indigo-dc/tts/issues/244
* http - > https redirection https://github.com/indigo-dc/tts/issues/204
* display login error messages https://github.com/indigo-dc/tts/issues/208, https://github.com/indigo-dc/tts/issues/209, https://github.com/indigo-dc/tts/issues/226, https://github.com/indigo-dc/tts/issues/372
* show message is login is impossible https://github.com/indigo-dc/tts/issues/199
* internal renaming/cleaning https://github.com/indigo-dc/tts/issues/206, https://github.com/indigo-dc/tts/issues/224
* extract plugins from WaTTS core https://github.com/indigo-dc/tts/issues/185
* fix REST inconsitency https://github.com/indigo-dc/tts/issues/127
* fetch versions of plugins https://github.com/indigo-dc/tts/issues/218
* use jobs framework for queues https://github.com/indigo-dc/tts/issues/115, https://github.com/indigo-dc/tts/issues/241
* add the possiblity to pass parameter to plugins https://github.com/indigo-dc/tts/issues/177, https://github.com/indigo-dc/tts/issues/375
* add interface for error messages from plugin to user https://github.com/indigo-dc/tts/issues/184
* block the WebInterface while a request is running https://github.com/indigo-dc/tts/issues/230
* add flag to allow removing of deprecated credentials https://github.com/indigo-dc/tts/issues/229
* add the possiblity to forward the access token to a plugin https://github.com/indigo-dc/tts/issues/233
* validate plugin parameter and give better errors: https://github.com/indigo-dc/tts/issues/228
* add debug output https://github.com/indigo-dc/tts/issues/246
* upgrade to elm 18 https://github.com/indigo-dc/tts/issues/247
* error at REST interface should result in 4xx code https://github.com/indigo-dc/tts/issues/239, https://github.com/indigo-dc/tts/issues/232
* timeout for plugins https://github.com/indigo-dc/tts/issues/232
* disable a service on plugin error or config error https://github.com/indigo-dc/tts/issues/258, https://github.com/indigo-dc/tts/issues/361
* support for downloading as a file in UI https://github.com/indigo-dc/tts/issues/189
* carousel for multiple parameter sets https://github.com/indigo-dc/tts/issues/222
* tooltip for unauthorizes/disable services https://github.com/indigo-dc/tts/issues/266
* change credential IDs to uuids https://github.com/indigo-dc/tts/issues/181
* ensure backwards compatibilty with protocol https://github.com/indigo-dc/tts/issues/263
* rename tts to wattson https://github.com/indigo-dc/tts/issues/294, https://github.com/indigo-dc/tts/issues/300
* update to newest, certified oidcc, https://github.com/indigo-dc/tts/issues/297, https://github.com/indigo-dc/tts/issues/310, https://github.com/indigo-dc/tts/issues/309
* rename to WaTTS https://github.com/indigo-dc/tts/issues/299, https://github.com/indigo-dc/tts/issues/314
* documentation https://github.com/indigo-dc/tts/issues/216, https://github.com/indigo-dc/tts/issues/322,
* enforce https https://github.com/indigo-dc/tts/issues/333
* enhance userinfo for plugins https://github.com/indigo-dc/tts/issues/331, https://github.com/indigo-dc/tts/issues/347, https://github.com/indigo-dc/tts/issues/356
* change REST v2 to have issuer in url https://github.com/indigo-dc/tts/issues/336
* enhance startup https://github.com/indigo-dc/tts/issues/340, https://github.com/indigo-dc/tts/issues/341, https://github.com/indigo-dc/tts/issues/342, https://github.com/indigo-dc/tts/issues/339, https://github.com/indigo-dc/tts/issues/339
* add possibility to show documenation at WaTTS server https://github.com/indigo-dc/tts/issues/351,
* ui polish https://github.com/indigo-dc/tts/issues/363, https://github.com/indigo-dc/tts/issues/370, https://github.com/indigo-dc/tts/issues/381, https://github.com/indigo-dc/tts/issues/386
<a id="id4"></a>

### Deployment Notes

* Upgrade is hard to handle automatically a manual how to do it is here: https://indigo-dc.gitbooks.io/token-translation-service/content/admin.html (Upgrade WaTTS)
* Basic installation ist at the same document above, configuration at: https://indigo-dc.gitbooks.io/token-translation-service/content/config.html

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7 

  ```$ yum clean all```</br>
  ```$ yum install tts```

* On Ubuntu 14.04 - after setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):

  ```$ apt-get update```</br>
  ```$ apt-get install tts```

* Ansible plugin:
  * https://github.com/indigo-dc/ansible-role-tts
  * https://github.com/indigo-dc/ansible-role-tts/releases/tag/v1.0.0

* More details regarding the installation and **configuration** can be found in the [TTS Deployment And Administration Guide](https://indigo-dc.gitbooks.io/token-translation-service/content/admin.html)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* Centos 7: [tts-1.0.0-1.el7.centos.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/tts-1.0.0-1.el7.centos.x86_64.rpm)
* Ubuntu14.04: [tts_1.0.0-1_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/tts_1.0.0-1_amd64.deb)

<a id="id6"></a>
## Documentation

* [TTS on GitBook](https://indigo-dc.gitbooks.io/token-translation-service/content/)
  * [User Guide](https://indigo-dc.gitbooks.io/token-translation-service/content/user.html)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
