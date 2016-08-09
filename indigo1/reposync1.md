# RepoSync v. 1.0-1


Summary:
* [Release Notes](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [Documentation](#id6)
  * [List of Artifacts](#id7)
  * [Support](#id8)


<a id="id1"></a>
## Release Notes

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

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](generic_installation_and_configuration_guide_1.md):
* On CentOS 7 

```$ yum clean all
$ yum install indigo-dc-reposync```

* On Ubuntu 14.04 - after setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](generic_installation_and_configuration_guide_1.md) add also the JRE 1.8 PPA following the documentation present [here](https://launchpad.net/~openjdk-r/+archive/ubuntu/ppa):

  ```$ apt-get update```

  ```$ apt-get install reposync```

Other methods:
* an Ansible playbook is available from the [INDIGO-DC github](https://github.com/indigo-dc/java-syncrepos/tree/master/ansible/tasks)
* a Docker container is available in the [INDIGO-DC Organization on DockerHub](https://hub.docker.com/r/indigodatacloud/reposync/):
  ```docker pull indigodatacloud/reposync:indigo_1```

<a id="id5"></a>
### Known Issues

* N/A

<a id="id6"></a>
### Documentation

* [RepoSync on GitBook](https://www.gitbook.com/book/jose-sanchezm/java-syncrepos/details)

<a id="id7"></a>
### List of Artifacts

Packages:
* reposync_1.0~jenkins_all.deb
* indigo-dc-reposync-1.0-1.noarch.rpm

Docker Container:
* [indigodatacloud/reposync:indigo_1](https://hub.docker.com/r/indigodatacloud/reposync/)

<a id="id8"></a>
### Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](
https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)