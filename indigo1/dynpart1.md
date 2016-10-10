# Partition Director v. 0.08-1

**Partition Director** ease management of a hybrid data center, where both Batch System based and cloud based services are provided. Physical computing resources can play both roles in a mutual exclusive fashion.

The **Partition Director** takes care of commuting the role of one or more physical machines from "Worker Node" (member of the batch system cluster) to "Compute Node" (member of a cloud instance) and vice versa.

**Summary**:
* [Release Notes](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes

<a id="id2"></a>
### What's new

Highlights of first release:
* Current release only works with the IBM/Platform LSF Batch system (version 7.0x or higher) and Openstack Cloud manager instances (Kilo or newer).

Supported Platforms:
* Operating System = CentOS 7
* Cloud Management Frameworks = Openstack v. >= KILO

<a id="id3"></a>
#### List of RfCs 

* High-level development tasks coordinated via [INDIGO-DC OpenProject tasks](https://project.indigo-datacloud.eu/work_packages/697?layout=false) (internal link)
 
<a id="id4"></a>
### Deployment Notes

* Installation is done through the RPMs provided and configuration files
* See also [Deployment Details](https://indigo-dc.gitbooks.io/dynpart/content/chapter1.html)

<a id="id5"></a>
### Known Issues
* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* python-dynpart-partition-director-0.08-1.el7.centos.noarch.rpm
* python-lsf-dynpart-partition-director-0.08-1.el7.centos.noarch.rpm

<a id="id6"></a>
## Documentation

* [Partition Director GitBook](https://www.gitbook.com/book/indigo-dc/dynpart/details)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
