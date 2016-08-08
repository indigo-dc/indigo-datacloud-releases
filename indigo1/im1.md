# Infrastructure Manager v1.4.6

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

<a id="id4"></a>
### Deployment Notes

```$ docker run -d -p 8899:8899 -p 8800:8800 --name im indigodatacloud/im:indigo_1```

* Other installation procedures are described in: [https://www.gitbook.com/book/indigo-dc/im/details](https://www.gitbook.com/book/indigo-dc/im/details)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id6"></a>
### Documentation

* [Infrastructure Manager GitBook](https://www.gitbook.com/book/indigo-dc/im/details)

<a id="id7"></a>
### List of Artifacts

Packages:
* IM-1.4.6-1.el7.noarch.rpm
* python-im_1.4.6-1_all.deb

Docker Container:
* [indigodatacloud/im:indigo_1](indigodatacloud/im)

<a id="id8"></a>
### Support

* GitHub issues: [https://github.com/indigo-dc/im/issues](https://github.com/indigo-dc/im/issues)
