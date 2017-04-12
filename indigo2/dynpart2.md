# Partition Director

**Partition Director** ease management of a hybrid data center, where both Batch System based and cloud based services are provided. Physical computing resources can play both roles in a mutual exclusive fashion.

The **Partition Director** takes care of commuting the role of one or more physical machines from "Worker Node" (member of the batch system cluster) to "Compute Node" (member of a cloud instance) and vice versa.

**Summary**:
* [Release Notes v. 0.9](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 0.9

<a id="id2"></a>
### What's new

Highlights of second release:
* Automated adjust share tool

Supported Platforms:
* CentOS 7
* Openstack v. Newton

<a id="id3"></a>
#### List of RfCs 

 ** Development of bjobs_r.py python script alternative to mcjobs.c which extracts the list of running jobs on each host. mcjobs.c had the licensing constraints
 ** Removed v2 while importing novaclient in all the scripts, explicitely added VERSION, to resolve compatibility issue 
 ** Added function isError() and count_N_jobs to handle correctly error situation while interacting with bjobs_r.py in p_driver.py
 ** Added function get_cn_list out of init function in p_switch.py 
 ** Development of adjust_lsf_shares.py to implement automated adjustment of shares on both partition
 
 <a id="id4"></a>
### Deployment Notes

* Puppet receipe available at https://github.com/indigo-dc/dynpart/tree/master/conf_mng/puppet/farm_dynpart
* RPM package available at 
https://jenkins.indigo-datacloud.eu:8080/job/dynpart-packaging/platform=bcentos7/lastSuccessfulBuild/artifact/RPMS/python-dynpart-partition-director-cc-0.9-2.el7.centos.noarch.rpm
https://jenkins.indigo-datacloud.eu:8080/job/dynpart-packaging/platform=bcentos7/lastSuccessfulBuild/artifact/RPMS/python-dynpart-partition-director-lsf-0.9-2.el7.centos.noarch.rpm
* for clean and upgrade installation
  * Related documentation at : 
    * https://indigo-dc.gitbooks.io/dynpart/content/batch.html
    * https://indigo-dc.gitbooks.io/dynpart/content/cloud.html

<a id="id5"></a>
### Known Issues
* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* [python-dynpart-partition-director-cc-0.9-2.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/python-dynpart-partition-director-cc-0.9-2.el7.centos.noarch.rpm)
* [python-dynpart-partition-director-lsf-0.9-2.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/python-dynpart-partition-director-lsf-0.9-2.el7.centos.noarch.rpm)

<a id="id6"></a>
## Documentation

* [Partition Director GitBook](https://www.gitbook.com/book/indigo-dc/dynpart/details)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
