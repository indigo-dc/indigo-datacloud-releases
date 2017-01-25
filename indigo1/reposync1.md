# RepoSync

The **java-SyncRepos** component can be used to synchronize Docker images in DockerHub to instances of either OpenStack or OpenNebula with Docker support already configured. To do so, it relies on the WebHooks mechanisms offered by DockerHub infrastructure and it provides a REST interface to list the available images already synchronized and some operations to force the synchronization of individual ones.

**Summary**:

* Updates:<br>
  * [RepoSync v1.2.0-1](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/fifth_update_of_indigo-1.html#rs)<br>


* [Release Notes v. 1.0-1](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
  
  
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 1.0-1

<a id="id2"></a>
### What's new

This is the first release of the Java-RepoSync service

Supported Platforms:
* OSs:
  *  Ubuntu 14.04 is supported by adding the [JRE 1.8 PPA](https://launchpad.net/~openjdk-r/+archive/ubuntu/ppa), required by java-syncrepos dependencysince 
  * CentOS 7 is supported by default
  * Any other distribution that support Docker is supported through the Docker image

* Operating System and Cloud Management Frameworks
  * It supports both OpenNebula and OpenStack backends

<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7 <br>
```$ yum clean all```<br>
```$ yum install indigo-dc-reposync```

* On Ubuntu 14.04 - after setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md) add also the JRE 1.8 PPA following the documentation present [here](https://launchpad.net/~openjdk-r/+archive/ubuntu/ppa):<br>
  ```$ apt-get update```<br>
  ```$ apt-get install reposync```

Other methods:
* an Ansible playbook is available from the [INDIGO-DC github](https://github.com/indigo-dc/java-syncrepos/tree/master/ansible/tasks)
* a Docker container is available in the [INDIGO-DC Organization on DockerHub](https://hub.docker.com/r/indigodatacloud/reposync/):<br>
  ```docker pull indigodatacloud/reposync:indigo_1```

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* [reposync_1.0~jenkins_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty/main/binary-amd64/reposync_1.0~jenkins_all.deb)
* [indigo-dc-reposync-1.0-1.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/base/indigo-dc-reposync-1.0-1.noarch.rpm)

Docker Container:
* [indigodatacloud/reposync:indigo_1](https://hub.docker.com/r/indigodatacloud/reposync/)

<a id="id6"></a>
## Documentation

* [RepoSync on GitBook](https://indigo-dc.gitbooks.io/java-syncrepos/content/)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
