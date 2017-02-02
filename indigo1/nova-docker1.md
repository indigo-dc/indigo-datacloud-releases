# Nova-Docker 

**Nova-Docker** is the Docker driver for OpenStack Nova.

Summary:
* Updates
  * [Nova-Docker v. 12.0.0](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo1/second_update_of_indigo-1.html#nd)<br>

* [Release Notes v. 16.04-4](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 16.04-4

<a id="id2"></a>
### What's new

We provide [detailed documentation](https://indigo-dc.gitbooks.io/nova-docker-documentation/content/) on how to enable the use of **nova-docker** component in OpenStack based infrastructures:

With this release we provide also packaging ([rpm and debs]((#id7)) that facilitate the installation of the service.

Supported Platforms:
* CentOS7 & Ubuntu 14.04, OpenStack

<a id="id4"></a>
### Deployment Notes

After setting the INDIGO-DC repositories as explained in the [Generic Installation & Configuration Guide](../generic_installation_and_configuration_guide_1.md):
* On CentOS 7, as root or otherwise using sudo:<br>
  ```$ yum install -y https://repos.fedorapeople.org/openstack/openstack-liberty/rdo-release-liberty-5.noarch.rpm```<br>
  ```$ yum clean all```<br>
  ```$ yum install python-nova-docker```<br>
* On Ubuntu 14.04, as root or otherwise using sudo:<br>
  ```$ add-apt-repository cloud-archive:liberty```<br>
  ```$ apt-get update```<br>
  ```$ apt-get install python-nova-docker```<br>

For configuration details please follow the** [GitHub Documentation](https://indigo-dc.gitbooks.io/nova-docker-documentation/content/)**

<a id="id7"></a>
### List of Artifacts

Packages:
* python-nova-docker_16.04-1_all.deb
* python-nova-docker-16.04-4.el7.local.noarch.rpm

<a id="id6"></a>
## Documentation

* Deployment, configuration and usage of nova-docker on [GitBook](https://indigo-dc.gitbooks.io/openstack-nova-docker/content/) 

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
