# OCCI support for OpenStack and OpenNebula

OCCI is a framework that allows management of resources in arbitrary cloud management frameworks through the OCCI standard.
This allow the users to exploit same CLI and APIs to manage diverse Cloud Management Framework in a transparent way.  

INDIGO - DataCloud project offersaAn implementation of the Open Grid Forum's Open Cloud Computing Interface (OCCI) for OpenStack. 
extended AWS support for rOCCI. Python and Java libraries for OCCI support.

* [OpenStack OCCI Interface (OOI)](ooi1.md)
* [pOCCI](pocci1.md)
* [rOCCI](rocci1.md)

<a id="install"></a>
## Installation and Configuration

After setting the INDIGO-DC repositories as explained in the
[Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):

* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-liberty/rdo-release-liberty-5.noarch.rpm```<br>
  ```$ yum clean all```<br>
  ```$ yum install python-ooi```<br>
  or<br>
  ```$ yum install python-pocci``` or ```$ yum install python3-pOCCI```<br>
or<br>
  ```$ yum install occi-server``` or ```$ yum install occi-cli```<br>
  
* On Ubuntu 14.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:liberty```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install python-ooi```<br>
  or<br>
  ```$ apt-get install python-pocci``` or ```$ apt-get install python3-pocci```<br>
  or<br>
  ```$ apt-get install occi-server``` or ```$ apt-get install occi-cli```<br>

* For more details regarding individual services configuration please follow the links above for the respective components
