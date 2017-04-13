# Infrastructure Manager v. 1.5.2

The **Infrastructure Manager (IM)** is a tool that deploys complex and customized virtual infrastructures on IaaS Cloud deployments (such as AWS, OpenStack, etc.). 
* It eases the access and the usability of IaaS clouds by automating the VMI (Virtual Machine Image) selection, deployment, configuration, software installation, monitoring and update of the virtual infrastructure. 
* It supports APIs from a large number of virtual platforms, making user applications cloud-agnostic. 
* In addition it integrates a contextualization system to enable the installation and configuration of all the user required applications providing the user with a fully functional infrastructure.

This version evolved in the [INDIGO-Datacloud project](https://www.indigo-datacloud.eu/) by adding support to TOSCA documents as input for the infrastructure creation.

## Summary:

<!--
* Updates
  * [IM v1.5.1](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/eight_update_of_indigo-1.html#im)
  * [IM v1.5.0](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/seventh_update_of_indigo-1.html#im)
  * [IM v1.4.8](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/fourth_update_of_indigo-1.html#im)
  * [IM v1.4.7](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/second_update_of_indigo-1.html#im)
-->

* [Release Notes v1.5.2](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v1.5.2


<a id="id2"></a>
### What's new

Hihglihts of this release:
* IM is now python 3 compatible
* Improve and enrichment of error messages and logging
* Improve OCCI connector
* Fix ssh, ansible and vm errors


Supported Platforms:
* CentOS 6
* CentOS 7
* Ubuntu 14.04
* Ubuntu 16.04

<a id="id3"></a>
#### List of RfCs 

* Error detecting Ansible process timeout -> https://github.com/grycap/im/issues/273
* Error in return value of function execute_timeout in SSH class -> https://github.com/grycap/im/issues/271
* Add VMINFO_JSON conf var to enable the GetVMInfo function return JSON RADL -> https://github.com/grycap/im/issues/270
* Improve OCCI cloud_init data process -> https://github.com/grycap/im/issues/269
* Error getting VM info -> https://github.com/grycap/im/issues/266
* Improve error messages in case of internal connector errors -> https://github.com/grycap/im/issues/242
* Test IM with python 3 -> https://github.com/grycap/im/issues/144
* Enrich the logging entries + stack trace with the infra id -> https://github.com/grycap/im/issues/250

<a id="id4"></a>
### Deployment Notes

```$ docker run -d -p 8899:8899 -p 8800:8800 --name im indigodatacloud/im:indigo_2```

* Other installation procedures are described in: [https://www.gitbook.com/book/indigo-dc/im/details](https://www.gitbook.com/book/indigo-dc/im/details)

* An Ansible playbokk is also available in [GitHub](https://raw.githubusercontent.com/indigo-dc/im/master/ansible_install.yaml) for an easier instalaltion and configuration

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* [IM-1.5.2-1.el7.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/IM-1.5.2-1.el7.noarch.rpm)
* [python-im_1.5.2-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python-im_1.5.2-1_all.deb)

Docker Container:
* [indigodatacloud/im:indigo_2](https://hub.docker.com/r/indigodatacloud/im/)


<a id="id6"></a>
## Documentation

* [Infrastructure Manager GitBook](https://www.gitbook.com/book/indigo-dc/im/details)

* To upgrade to the last version first you have to install the new version using yum or apt tool:
```yum update IM```</br>
```apt install python-im```</br>

* As there is a change in the DB format. Old 1.5.0 data must be updated. Use the script: db_1_5_0_to_1_5_1.py to update the DB format (if you have installed 1.5.0 version) or db_1_4_to_1_5.py (if you have installed 1.4.X version):
  * Install new IM 1.5.2 version.
  * In case that you were using a DATA_FILE to store the IM data (in case of 1.4.X version), define the DATA_DB in the im.cfg file.
  * Execute the script .
    * In case that you were using a DATA_FILE you have to specify it as the first parameter of the script.
    * If you were using a DATA_DB to store your data this parameter is not needed.
    * The data will be moved to the new format and old data will be renamed as table inf_list_XXXXXX.

* To update a container the user has to:
  * Stop the old container:</br>
```sudo docker stop im```</br>
  * Remove the old container:</br>
```sudo docker rm im```</br>
  * Pull the new image version:</br>
```sudo docker pull indigodatacloud/im```</br>
  * Start the new version:</br>
```sudo docker run -d -p 8899:8899 -p 8800:8800 -e IM_DATA_DB=mysql://username:password@server/db_name --name im indigodatacloud/im```</br>

<a id="id8"></a>
## Support

* GitHub issues: [https://github.com/indigo-dc/im/issues](https://github.com/indigo-dc/im/issues)
