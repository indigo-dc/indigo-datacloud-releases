# pOCCI v. 1.0.3


**pOCCI** is OCCI standard compliance testing tool. Tests are described [here](http://www.etsi.org/deliver/etsi_ts/103100_103199/103142/01.01.01_60/ts_103142v010101p.pdf).

## Summary:
* [Release Notes v. 1.0.3](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 1.0.3

<a id="id2"></a>
### What's new

* This is a revision of pOCCI with documentation updates and very minor output fixes.


Supported Platforms:
* OpenNebula, OpenStack, AWS, Synnefo (anything OCCI-enabled)
* CentOS7, Ubuntu 14, Ubuntu 16

* OS Systems
  *  From INDIGO-DC repositories: - CentOS 7, Ubuntu 14/trusty
  *  [others](http://scientific.zcu.cz/cesnet/pOCCI/html/devel.html#packages), also native python egg (pypi.python.org)
* clouds: 
  * Amazon EC2, OpenNebula, OpenStack, rOCCI-server dummy backend for testing
  
<a id="id3"></a>
#### List of RfCs 

List of bugfixes and extensions:
* https://github.com/CESNET/pOCCI/pull/1
* https://github.com/CESNET/pOCCI/pull/9
* https://github.com/CESNET/pOCCI/pull/10
* https://github.com/CESNET/pOCCI/pull/11
* https://github.com/CESNET/pOCCI/pull/12
* https://github.com/CESNET/pOCCI/pull/16
* https://github.com/CESNET/pOCCI/issues/2
* https://github.com/CESNET/pOCCI/issues/3
* https://github.com/CESNET/pOCCI/issues/4
* https://github.com/CESNET/pOCCI/issues/6
* https://github.com/CESNET/pOCCI/issues/8
* https://github.com/CESNET/pOCCI/issues/17

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_2.md):
* On CentOS 7 

```$ yum clean all```</br>
```$ yum install python-pocci```</br>
or
```$ yum install python3-pOCCI```

* On Ubuntu 16.04 - after setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):

```$ apt-get update```</br>
```$ apt-get install python-pocci```</br>
or
```$ apt-get install python3-pocci```

Other instalaltion methods:
* installation from egg: [http://scientific.zcu.cz/cesnet/pOCCI/html/usage.html#installation](http://scientific.zcu.cz/cesnet/pOCCI/html/usage.html#installation)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* CentOS7:
  * [python2-pOCCI-1.0.3-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/python2-pOCCI-1.0.3-1.el7.centos.noarch.rpm)
  * [python-pOCCI-1.0.3-1.el7.centos.src.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/base/python-pOCCI-1.0.3-1.el7.centos.src.rpm)
  * [python-pOCCI-doc-1.0.3-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/python-pOCCI-doc-1.0.3-1.el7.centos.noarch.rpm)
* Ubuntu 16.04:
  * [python3-pocci_1.0.3-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python3-pocci_1.0.3-1_all.deb)
  * [python-pocci_1.0.3-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python-pocci_1.0.3-1_all.deb)
  * [python-pocci_1.0.3-1_amd64.changes](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python-pocci_1.0.3-1_amd64.changes)
  * [python-pocci_1.0.3-1.debian.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/source/python-pocci_1.0.3-1.debian.tar.gz)
  * [python-pocci_1.0.3-1.dsc](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/source/python-pocci_1.0.3-1.dsc)
  * [python-pocci_1.0.3.orig.tar.gz]
  * [python-pocci-doc_1.0.3-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/python-pocci-doc_1.0.3-1_all.deb)
  
<a id="id6"></a>
## Documentation

* [pOCCI on GitBook](https://www.gitbook.com/download/pdf/book/indigo-dc/pocci)
* User documentation is in the form of manpages (links are in the gitbook).

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
* For Technical stuff: please use github - [https://github.com/CESNET/pOCCI/issues](https://github.com/CESNET/pOCCI/issues)
