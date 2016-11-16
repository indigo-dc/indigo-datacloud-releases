# Infrastructure Manager 

The **Infrastructure Manager (IM)** is a tool that deploys complex and customized virtual infrastructures on IaaS Cloud deployments (such as AWS, OpenStack, etc.). 
* It eases the access and the usability of IaaS clouds by automating the VMI (Virtual Machine Image) selection, deployment, configuration, software installation, monitoring and update of the virtual infrastructure. 
* It supports APIs from a large number of virtual platforms, making user applications cloud-agnostic. 
* In addition it integrates a contextualization system to enable the installation and configuration of all the user required applications providing the user with a fully functional infrastructure.

This version evolved in the [INDIGO-Datacloud project](https://www.indigo-datacloud.eu/) by adding support to TOSCA documents as input for the infrastructure creation.

**Summary**:

* Updates
  * [IM v1.4.7](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/second_update_of_indigo-1.html#im)<br>
  * [IM v1.4.8](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/fourth_update_of_indigo-1.html#im)<br>

* [Release Notes v1.4.6](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v1.4.6


<a id="id2"></a>
### What's new

Hihglihts of this release:
* Support for TOSCA 1.0 YAML specification with the custom node types described in https://[github.com/indigo-dc/tosca-types/blob/master/custom_types.yaml](github.com/indigo-dc/tosca-types/blob/master/custom_types.yaml)
* Support for the Identity and Access Management Service (IAM).
* Support for deployment as a Docker container (available in [https://hub.docker.com/r/indigodatacloud/im/](https://hub.docker.com/r/indigodatacloud/im/))
* Support for the Token Translation Service (TTS) on OpenNebula Clouds.
* Improvements to access OpenStack Clouds that support IAM


Supported Platforms:
* Distributed as a Docker container
* Also distributed as DEB/RPMs packages supporting Ubuntu 14.04 / CentOS 7

<a id="id3"></a>
#### List of RfCs 

* Development followed via GitHub:  https://github.com/indigo-dc/im
  * High-level tasks coordinated via [WP5 OpenProject tasks](https://project.indigo-datacloud.eu/projects/wp5/work_packages?query_id=11) (internal link)

* Project WP5, tasks with subject including [TOSCA Templates] or [Orchestrator/IM]

* List og bugfixes addressed as a list of commits to the master branch: [https://github.com/indigo-dc/im/commits/master](https://github.com/indigo-dc/im/commits/master)

<a id="id4"></a>
### Deployment Notes

```$ docker run -d -p 8899:8899 -p 8800:8800 --name im indigodatacloud/im:indigo_1```

* Other installation procedures are described in: [https://www.gitbook.com/book/indigo-dc/im/details](https://www.gitbook.com/book/indigo-dc/im/details)

* An Ansible playbokk is also available in [GitHub](https://raw.githubusercontent.com/indigo-dc/im/master/ansible_install.yaml) for an easier instalaltion and configuration

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* IM-1.4.6-1.el7.noarch.rpm
* python-im_1.4.6-1_all.deb

Docker Container:
* [indigodatacloud/im:indigo_1](https://hub.docker.com/r/indigodatacloud/im/)


<a id="id6"></a>
## Documentation

* [Infrastructure Manager GitBook](https://www.gitbook.com/book/indigo-dc/im/details)

<a id="id8"></a>
## Support

* GitHub issues: [https://github.com/indigo-dc/im/issues](https://github.com/indigo-dc/im/issues)
