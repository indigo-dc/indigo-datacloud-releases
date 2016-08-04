# INDIGO-1 MidnightBlue

The INDIGO - DataCloud project is pleased to announce the general availability of its first public software release, codenamed **MidnightBlue**.

The release comes after an initial phase of requirement gatherings which involved several European scientific collaborations in areas as diverse as structural biology, earth science, physics, bioinformatics, cultural heritage, astrophysics, life science, climatology. This resulted in the development of many software components addressing existing technical gaps linked to easy and optimal usage of distributed data and compute resources. These components are now released into a consistent and modular suite, offered as a contribution toward the definition and implementation of an efficient European Open Science Cloud.

The first INDIGO-DataCloud release provides **open source components** targeting:
* **Site-level solutions**, allowing data centers to increase efficiency and services for customers.
* **Data solutions**, offering advanced access to distributed data.
* **Automated solutions**, allowing users to easily specify and deploy complex data and compute resource requirements.
* **User-level solutions**, integrating scientific applications in programmable front-ends and in mobile applications.

*Key technical highlights → Giacinto/Cristina/Jorge - include a short description of high-level components as well as some numbers related e.g. to how many components in total, github repos, docker containers, etc.*

The INDIGO - DataCloud software is released under the Apache 2.0 software license and can be deployed on both public and private Cloud infrastructures. It can be downloaded from http://repo.indigo-datacloud.eu.

**INDIGO - DataCloud** is an Horizon 2020 project funded by the European Commission from April 2015 to September 2017. It involves 26 European partners, including research institutes, scientific collaborations, software developers, universities, e-infrastructures, private companies. Its main goal is to provide software solutions for science addressing several of the technology gaps in Cloud and Data technologies currently experienced by resource providers and scientists working in either small or big collaborations.

For more information on the project, see https://www.indigo-datacloud.eu. 


# Release Notes

The INDIGO-1 release consists in 32 Products divided in, mainly, Core Services, and Applications, that met the [INDIGO - DataCloud Acceptance Criteria:](http://ADD_LINK)
* X OS packages
  * XXX RPMS
  * YYY DEBS
  * ZZZ containers
* Y external/third-party dependencies:

INDIGO-1 is fully supported
* on the following **Operating Systems** platforms:
  * **CentOS 7**
  * **Ubuntu 14.04**
  * Optionally PTs support also other OS platforms. You can find information about this in the individual products documentation
* on the following **CMFs (Cloud Management Framework)** versions:
  * **OpenStack v. Liberty,** with the exception of the "TOSCA in HEAT (heat-translator) for which it one must used the Mitaka HEAT, and the rest of services on Liberty
  * **OpenNebula v. 4.14**

You can find in the later chapters the full list of products, with detailed release notes and instructions for their installation/configuration. 

