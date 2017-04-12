# RepoSync

The **java-SyncRepos** component can be used to synchronize Docker images in DockerHub to instances of either OpenStack or OpenNebula with Docker support already configured. To do so, it relies on the WebHooks mechanisms offered by DockerHub infrastructure and it provides a REST interface to list the available images already synchronized and some operations to force the synchronization of individual ones.

## Summary:
<!--
* Updates:<br>
  * [RepoSync v1.2.0-1](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/fifth_update_of_indigo-1.html#rs)<br>
-->

* [Release Notes v. 1.2.0-1](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
  
  
* [Documentation](#id6)
* [Support](#id8)

<a id="id2"></a>
#### What's new
* Added service support to Ubuntu 14.04, 16.04 and CentOS 7. Packages are now dependent on jsvc
* Added support for HTTPS

<a id="id3"></a>
#### List of RfCs

* [Issue #42](https://github.com/indigo-dc/java-reposync/issues/42) - Create init services
* [Issue #449](https://github.com/indigo-dc/java-reposync/issues/449) - Support HTTPS

<a id="id4"></a>
#### Installation & Configuration
In order to update the packages please use:
* Just install the new packages over the old ones. It should ask if you want to replace the existing configuration so don't do it. It should work just 
fine with the old one. In case SSL support is needed, please configure the properties described at [https://github.com/indigo-dc/java-reposync/blob/master/docs/configuration.md](https://github.com/indigo-dc/java-reposync/blob/master/docs/configuration.md)


#### Artefacts
* CentOS7
  * [indigo-dc-reposync-1.2.0-1.noarch.rpm	](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/indigo-dc-reposync-1.2.0-1.noarch.rpm	)
* Ubuntu16.04
  * [reposync_1.2.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/reposync_1.2.0_all.deb)
  
  Docker Container:
* [indigodatacloud/reposync:indigo_2](https://hub.docker.com/r/indigodatacloud/reposync/)

<a id="id6"></a>
## Documentation

* [RepoSync on GitBook](https://indigo-dc.gitbooks.io/java-syncrepos/content/)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
