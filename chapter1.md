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


## Installation Notes 

All INDIGO - DataCloud products are distributed from a single repository having the following structure:

    INDIGO-DC production (stable): dist/EMI/1/sl5/<basearch>/{base|updates}
        stable and signed, well tested software components, recommended to be installed on production-sites
    INDIGO-DC testing: INDIGO/testing/{1|2|3}/<platform>/<basearch>
        packages that will become part of the next stable distribution; in the certification and validation phase and available for technical-previews
    Third-party: INDIGO/1/<platform>/<basearch>/third-party
        packages that are not part of INDIGO, but are currently not part of the base OS or EPEL

<basearch> is currently: x86_64, SRPMS, tgz 

All EMI packages are signed with the INDIGO - DataCloud gpg key. The public key can be downloaded from [here](http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc), and the fingerprint from [here](http://ADD_LINK).

It is strongly recommended the use of the lastest version of the indigodc-release package containing the public key and the yum and apt repository files.

To understand how to install and configure INDIGO-1 products either refer to the "Generic Installation & Configuration Guide" chapter or to each individual product documentation.


## Software

INDIGO-1 software can be downloaded from [INDIGO DataCloud repositories](http://repo.indigo-datacloud.eu/).


## Documentation

Please find INDIGO-1 documentation [here](https://www.gitbook.com/@indigo-dc/dashboard)


## Support

Most complex software contains bugs, we are not an exception. One of the features of free and open source software is the ability to report bugs, helping to fix or improve the software you use.

INDIGO - DataCloud project uses the [GGUS (Global Grid User Support)](https://ggus.eu/) tool as its user support system. It provides sophisticated search functionality, report generation, interfaces to bug tracking systems used by different middleware components, and automatic ticket reminder including escalation indication.

Developers, researchers and IT enthusiasts: feel free to write to [info@indigo-datacloud.eu](info@indigo-datacloud.eu) to ask for more information on how to deploy your PaaS based solution for your work. For automatic notifications you can register to the [INDIGO-DataCloud RSS release feed](http://ADD_LINK) or subscribe to the [INDIGO-DataCloud Announce Mailing list](https://lists.indigo-datacloud.eu/sympa/info/indigo-announce). You can also socialize with us via [Twitter](https://twitter.com/indigodatacloud), [Facebook](https://www.facebook.com/indigodatacloud/?ref=bookmarks) and join our [LinkedIn group](https://www.linkedin.com/groups/8416266). 
