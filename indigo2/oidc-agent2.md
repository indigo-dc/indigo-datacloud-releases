# OpenIDConnect Agent - OIDC-Agent

**oidc-agent** is a new system service ensuring that always a valid access token is available for
the command line.

<!--
## Summary:
* Updates
  * [TTS v. 1.2.0](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo2/fifth_update_of_indigo-2.html#tts)
  -->
</br>

* [Release Notes v. v 1.1.1](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v.1.1.1

<a id="id2"></a>
### What's new

* *oidc-agent* oidc-agent is a tool to manage OpenID Connect tokens and make them easily usable 
from the command line. We followed the ssh-agent design, so users can handle OIDC tokens in a similiar
way as they do with ssh keys.

*oidc-agent* is usually started in the beginning of an X-session or a login session. Through use of 
environment variables the agent can be located and used to handle oidc tokens.

The agent initially does not have any account configurations loaded. You can load a account configuration 
by using *oidc-add*. Multiple accounts configurations may be loaded in oidc-agent concurrently. *oidc-add* is also 
used to remove a loaded configuration from oidc-agent.

Supported Platforms:
* Centos 7
* Ubuntu 14.04, 16.04

<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

* Please see the documentation available at : https://indigo-dc.gitbooks.io/oidc-agent/content/admin.html


<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* Centos 7: 
  * [oidc-agent-1.1.0-1.x86_64.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/updates/oidc-agent-1.1.0-1.x86_64.rpm)
* Ubuntu 16.04: 
  * [oidc-agent_1.1.1-2_amd64.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial-updates/main/binary-amd64/oidc-agent_1.1.1-2_amd64.deb)

<a id="id6"></a>
## Documentation

* [OIDC-Agent on GitBook](https://indigo-dc.gitbooks.io/oidc-agent/content/)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
