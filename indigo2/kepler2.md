# INDIGO Kepler

## Summary:

* Updates
  * [INDIGO Kepler v 1.2.0](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo2/fourth_update_of_indigo-2.html#kepler)<br>
  * [INDIGO Kepler v 1.1.1](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo2/first_update_of_indigo-2.html#ik)<br>


* [Release Notes v. 1.1 ](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)<br>

* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 1.1.1

<a id="id2"></a>
### What's new

* Highlights of INDIGO Kepler & Client version in INDIGO-2 release
  * In indigo-dc/indigoclient project the main update concerns support for another FutureGateway remote function i.e. to set Runtime Data of a task. This functionality is useful in general (allows to interact with a running task) and especially it is used for live-monitoring in the ENES use case. However this new functionality required that we change the dependencies used in the project. Our Java HTTP client, which was Jersey, did not support HTTP PATCH method. We had to replace it with Apache HttpComponents. This also required that we change the testing framework into WireMock. The good thing is that only the low-level things changed (the HTTP connectivity part), but all high-level API provided for INDIGO are exactly the same and all tests prove that the high-level API works as expected.
  * As for indigo-dc/indigokepler, we have added a new Kepler actor which sets Runtime Data and therefore we also updated ENES workflows to make use of it. We have also developed a new workflow which can be run in batch mode (without user interface). And we have created a set of scripts which install a new application on the FutureGateway - for Ophidia terminal type of task and for running Kepler in batch mode. We have also fixed a bug which appeared during code refactoring - Kepler installation through Ansible role was not having the properties files in correct locations.
  * We have also worked on indigo-dc/ansible-role-kepler and indigo-dc/ansible-role-kepler-batch to be able to make Docker images for either Kepler with GUI or Kepler in batch mode. The latter is a new addition in INDIGO Release 2.
  * We are finishing the work of packaging but finally and soon all the previously mentioned components will be tagged and released as v1.1


Supported Platforms:
* We provide the pre-packaged versions as Docker images which all inherit from Ubuntu 14.04 image.


<a id="id3"></a>
#### List of RfCs 

* https://github.com/indigo-dc/indigoclient/issues/8
* https://github.com/indigo-dc/indigoclient/issues/9
* https://github.com/indigo-dc/indigoclient/issues/10
* https://github.com/indigo-dc/indigokepler/issues/8
* https://github.com/indigo-dc/indigokepler/issues/10


<a id="id4"></a>
### Deployment Notes
* Installation methods
  * Docker images:
    * indigodatacloudapps/kepler:</br>
```docker run -it -p 15900:5900 indigodatacloudapps/kepler```</br> (now you can connect via VNC at @localhost:15900@)
    * indigodatacloudapps/kepler-batch:</br>
```docker run indigodatacloudapps/kepler-batch```</br>
    * Java projects:
      * indigo-dc/indigoclient: </br>
```mvn install```</br></br>
      * indigo-dc/indigokepler: </br>
```mvn initialize```</br>
```mvn install```</br>
```mvn dependency:copy-dependencies -DoutputDirectory=target/indigo/lib/jar -DexcludeArtifactIds=ptolemy```</br>



* During development, a Docker image was created which prepackages everything and creates a user-friendly Kepler instance with INDIGO-Kepler modules installed.
* Both parts can be installed via Maven:
  * indigoclient: ```mvn install```
  * indigokepler: ```mvn initialize install dependency:copy-dependencies -DoutputDirectory=target/indigo/lib/jar -DexcludeArtifactIds=ptolemy```

* Ansible playbook is available in [GitHub](https://github.com/indigo-dc/ansible-role-kepler) and [Ansible Galaxy](https://galaxy.ansible.com/indigo-dc/kepler/)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

* Docker images: [indigodatacloudapps/kepler:indigo_2](https://hub.docker.com/r/indigodatacloudapps/kepler/tags/) and [indigodatacloudapps/kepler-batch:indigo_2](https://hub.docker.com/r/indigodatacloudapps/kepler-batch/tags/)
* Ansible roles: indigo-dc.kepler and indigo-dc.kepler-batch
* Java projects: https://github.com/indigo-dc/indigoclient and https://github.com/indigo-dc/indigokepler
* Source Tarballs:
  * [indigoclient-v1.1.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/indigoclient-v1.1.tar.gz)
  * [indigokepler-v1.1.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/indigokepler-v1.1.tar.gz)

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
