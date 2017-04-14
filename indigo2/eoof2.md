# Extended OpenStack and OpenNebula Functionalities

*	Improved scheduling for allocation of resources by popular open source Cloud platforms, i.e. OpenStack and OpenNebula.
  * Enhancements will address both better scheduling algorithms and support for spot-instances. 
  *	We will also support dynamic partitioning of resources among “traditional batch systems” and Cloud infrastructures (for some LRMS).
*	Support for standards in IaaS resource orchestration engines through the use of the TOSCA standard.
  *	This overcomes the portability and usability problem that ways of orchestrating resources in Cloud computing frameworks widely differ among each other.
*	Improved IaaS orchestration capabilities for popular open source Cloud platforms, i.e. OpenStack and OpenNebula.
  *	Enhancements will include the development of custom TOSCA templates to facilitate resource orchestration for end users, increased scalability of deployed resources and support of orchestration capabilities for OpenNebula.


<br>

Components:
* OpenStack support for INDIGO developments (AAI, preemptible instances, etc.)
  * [OpenStack preemptible instances support (OpenStack Preemptible Instances Extensions)](opie2.md)
  * OpenStack support for INDIGO AAI
    * [OpenStack Identity Authentication Library support for INDIGO AAI developments](keystone_library2.md)
    * [Keystone AAI support](keystone_aai_support2.md)
* [Docker driver for OpenStack Nova](nova-docker2.md)
* [Heat-Translator tool is aimed to translate non-heat templates to OpenStack Heat Orchestration Template (HOT)](heat-translator2.md)
* [Docker support for OpenNebula](onedock2.md)
* [Sync between INDIGO Docker-hub, ONEDock and nova-docker](reposync2.md)
* [OpenStack Client](python-osclient1.md) & [Nova Client](python-nova2.md)

<a id="install"></a>
## Installation and Configuration

After setting the INDIGO-DC repositories as explained in the
[Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_2.md):

* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-liberty/rdo-release-liberty-5.noarch.rpm```<br>
  ```$ yum clean all```<br>
  ```$ yum install opie```<br>
  or<br>
  ```$ yum install python2-keystoneauth1``` <br>
  or <br>
  ```$ yum install python-nova-docker```<br>
or<br>
  ```$ yum install python2-novaclient``` or ```$ yum install python-openstackclient```<br>
or <br>
  ```$ yum install indigo-dc-reposync```<br>
  
* On Ubuntu 16.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:liberty```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install opie```<br>
  or<br>
  ```$ apt-get install python3-keystoneauth1``` or ```$ apt-get install python-keystoneauth1```<br>
  or<br>
  ```$ apt-get install python-nova-docker``` <br>
  or <br>
  ```$ apt-get install python-novaclient``` or ```$ apt-get install python-openstackclient```<br>
  or <br>
  ```$ apt-get install reposync```

* For more details regarding individual services configuration please follow the links above for the respective components
