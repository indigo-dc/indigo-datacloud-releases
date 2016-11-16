# INDIGO Kepler v. 1.0.1

**Summary**:

* Updates
  * [INDIGO Kepler v 1.0.2](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/fourth_update_of_indigo-1.html#ik)<br>

* [Release Notes v. 1.0.1](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)<br>

* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes

<a id="id2"></a>
### What's new

* This is the first release of INDIGO Kepler & Client
  * Component consists of two parts which are both released under 1.0.1 tag:
    * [indigoclient](https://github.com/indigo-dc/indigoclient/releases/tag/1.0.1)
    * [indigokepler](https://github.com/indigo-dc/indigokepler/releases/tag/1.0.1) 

Supported Platforms:
* The components are in Java, so in principle any modern OS can be used.

<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

* During development, a Docker image was created which prepackages everything and creates a user-friendly Kepler instance with INDIGO-Kepler modules installed.
* Both parts can be installed via Maven:
  * indigoclient: ```mvn install```
  * indigokepler: ```mvn initialize install dependency:copy-dependencies -DoutputDirectory=target/indigo/lib/jar -DexcludeArtifactIds=ptolemy```

* Ready to compile version are available here:
  * [indigoclient-1.0.1.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/indigoclient-1.0.1.tar.gz)
  * [indigokepler-1.0.1.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/indigokepler-1.0.1.tar.gz)
* After Maven compilation, two artifacts are created: *indigo-fg-api-1.0.1.jar* and *indigo-fg-actors-1.0.1.jar*
* Additionally, in *indigokepler/target/* a directory named indigo is created which fulfills Kepler's requirements for a module. It is sufficient to add it to an existing Kepler installation to use INDIGO-Kepler actors.

* Ansible playbook is available in [GitHub](https://github.com/indigo-dc/ansible-role-kepler) and [Ansible Galaxy](https://galaxy.ansible.com/indigo-dc/kepler/)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Docker Container:
* [indigodatacloudapps/kepler:indigo_1](https://hub.docker.com/r/indigodatacloudapps/kepler/tags/)

<a id="id6"></a>
## Documentation

* [indigoclient GitBook](https://www.gitbook.com/book/indigo-dc/indigoclient)
* [indigokepler GitBook](https://www.gitbook.com/book/indigo-dc/indigokepler)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
or
  * [indigoclient GitHub Issues](https://github.com/indigo-dc/indigoclient/issues)
  * [indigokepler GitHub Issues](https://github.com/indigo-dc/indigokepler/issues)
