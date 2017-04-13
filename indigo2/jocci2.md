# jOCCI v. 0.2.6

**jOCCI** is a suite of Java libraries to facilitate use of the [OCCI (Open Cloud Computing Interface)](http://occi-wg.org/) protocol as 
standardized by OGF (the Open Grid Forum). Its main purpose is to simplify development of OCCI clients in Java.

The jOCCI suite consists of the following components:

* **jOCCI-core** is an implementation of the OCCI class structure in Java. It allows developers to work with OCCI concepts hands-on, treating OCCI classes as actual classes in their program.
* **jOCCI-api** is a library for OCCI transport over HTTPs.


## Summary:
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

This is the initial release of jOCCI, a Java library implementing the OCCI protocol for use mainly in client-side products. 


Supported Platforms:
* CentOS7, Ubuntu 14, Ubuntu 16

<a id="id4"></a>
### Deployment Notes 
* There is no installation, the packages will be brought in by a 
depending application. Similarly, upgrades will be brought in with updates of the depending application where applicable.

<a id="id3"></a>
#### List of RfCs 
* https://github.com/Misenko/jOCCI-api/wiki/jOCCI-Release-Page

<a id="id5"></a>
### Known Issues
* Only OCCI version 1.1 is supported.

<a id="id7"></a>
### List of Artifacts

* [libjocci-api-java_0.2.6-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/libjocci-api-java_0.2.6-1_all.deb)
* [libjocci-api-java-doc_0.2.6-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/libjocci-api-java-doc_0.2.6-1_all.deb)
* [jOCCI-api-0.2.6-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/jOCCI-api-0.2.6-1.el7.centos.noarch.rpm)
* [jOCCI-api-0.2.6-1.el7.centos.src.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/base/jOCCI-api-0.2.6-1.el7.centos.src.rpm)
* [jOCCI-api-javadoc-0.2.6-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/jOCCI-api-javadoc-0.2.6-1.el7.centos.noarch.rpm)

* [libjocci-core-java_0.2.4-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/libjocci-core-java_0.2.4-1_all.deb)
* [libjocci-core-java-doc_0.2.4-1_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/libjocci-core-java-doc_0.2.4-1_all.deb)
* [jOCCI-core-0.2.4-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/jOCCI-core-0.2.4-1.el7.centos.noarch.rpm)
* [jOCCI-core-0.2.4-1.el7.centos.src.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/base/jOCCI-core-0.2.4-1.el7.centos.src.rpm)
* [jOCCI-core-javadoc-0.2.4-1.el7.centos.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/jOCCI-core-javadoc-0.2.4-1.el7.centos.noarch.rpm) 

jOCCI libraries are available also from the following sources:
* Maven
    * https://mvnrepository.com/artifact/cz.cesnet.cloud/jocci-core
    * https://mvnrepository.com/artifact/cz.cesnet.cloud/jocci-api
* GitHub sources
    * https://github.com/indigo-dc/jOCCI-core
    * https://github.com/indigo-dc/jOCCI-api
* INDIGO DataCloud repository
    * http://repo.indigo-datacloud.eu/#one

## Documentation
* https://github.com/Misenko/jOCCI-api/wiki

