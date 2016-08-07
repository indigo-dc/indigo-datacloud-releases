# Generic Installation and Configuration Guide

This chapter provides information on how to enable and use the INDIGO DataCloud software repositories.


## Installing the Operating Systems and Cloud  Management Frameworks 


### Operating Systems


#### CentOS 7 


For more information on CentOS please check: [https://www.centos.org/](https://www.centos.org/)

All the information to install this operating system can be found at https://wwwhttps://www.centos.org/download/[](https://www.centos.org/download/)

You will find there information on CentOS [packages](http://mirror.centos.org/centos/7/) and [Docker Containers](https://hub.docker.com/_/centos/).

##### The EPEL repository
If not present by default on your nodes, you should enable the EPEL repository (https://fedoraproject.org/wiki/EPEL)

EPEL has an 'epel-release' package that includes gpg keys for package signing and repository information. Installing the latest version of epel-release package available on EPEL7 repositories like:
* [http://download.fedoraproject.org/pub/epel/7/x86_64/e/](http://download.fedoraproject.org/pub/epel/7/x86_64/e/) 

allows you to use normal tools, such as **yum**, to install packages and their dependencies. By default the stable EPEL repo should be enabled.


#### Ubuntu 14.04






## Enable the INDIGO - DataCloud repositories


## Important note on automatic updates 

The CentOS and Ubuntu Operating Systems both offer auto-updates mechanisms. Sometimes middleware updates require non-trivial configuration changes or a reconfiguration of the service. This could involve service restarts, new configuration files, etc, which makes it difficult to ensure that automatic updates will not break a service. Thus

**WE STRONGLY RECOMMEND NOT TO USE AUTOMATIC UPDATE PROCEDURE OF ANY KIND**

on the INDIGO - DataCloud  repositories (you can keep it turned on for the OS). You should read the update information provides by each service and do the upgrade manually when an update has been released! 






