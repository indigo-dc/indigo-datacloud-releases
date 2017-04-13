# FutureGateway API Server & API Server Daemon


The **FutureGateway** aids the creation of Science Gateways or enable existing community oriented interfaces to become a Science Gateway, thus accessing any distributed computing resource using a simple set of REST APIs.

The **FutureGateway API Server** project implements the interface of a RESTful API Server, compliant with [CSGF APIs](http://docs.csgfapis.apiary.io/#reference/v1.0/application/create-a-task) specifications. Any activity processed by this interface will be then processed and orchestrated by the [FutureGateway API Server Daemon](indigo1/fgapiserverdaemon1.md) component.
This service offers the same capabilities of the [API Server](https://github.com/FutureGateway/APIServer) project with the following differences:
* It exploits the [CSGF](https://www.catania-science-gateways.it/)' GridEngine system to target its supported distributed ifnrastructures
* It may support other executors services just developing the right interface classes into the [API Server Daemon][APIServerDaemon]

The **APIServerDaemon** is a polling daemon working as a java servlet operating under Tomcat8. This daemon polls on 
top of the REST queue table and process the requests accordingly

The Principal advantages of this solutions are:
* Backward compatibility with existing systems based on the CSGF
* Fast provisioning of ready to go solutions
* Fast prototyping when designing new features and components (including APIServer itself)
* Ideal solution for existing development environments already using CSGF.

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

The following FutureGateway components have been impacted by this release:

fgAPIServer - The API Server front-end has been enriched by several new features:
* fgapiserber_ptv, can be now configured to return real IAM settings. In the fgAPIServer main directory exists the directory .iam with the following three files: token (IAM token), subject (User identifier) and Groups.
* Automatic registration of token subjects; this guarantees user isolation when using Tokens
* Fix on application installation; users belonging to the installator' group will be allowed to use the app
* Makefile to create deb package (Ubuntu 14.04)
* Fixed pagination when listing tasks/apps/infrastructures
* Fixed boolean values in JSON answers from 0/1 to true/false
* Implemented APIs on infrastructure management and use of their ids installing applicaitons
* Official API support to application level files (does not deprecates input_files)

APIServerDaemon - This component has been updated only to support changes related to fgAPIServer

Supported Platforms:
* FutureGateway still supports both CentOS7, Ubuntu14.04 and MacOS X

<a id="id3"></a>
#### List of RfCs 

GitHub Issues:
#25 APIs differ from specification
#29 Unmapped users/group(s) causes error messages rather using unmapped user
#30 More fine grained user list
#32 Missing 'url' field for input files in FG API
#34 Cannot use any new application without manual intervention in the database
#36 Removing task gives wrong status code
#37 Add multiple tasks return 405 Method not allowed
#38 Delete the task list returns 405 Method not allowed
#39 When Access Token is expired API return 500 instead of 401
#41 Modify task gives error 500
#42 Create a task from Task API returns method not allowed

<a id="id4"></a>
### Deployment Notes

* Upgrade an already deployed service:
  * fgAPIServer: extract first new files from Git. Pay attention to configuration file and to restart the service related to wsgi in case the front end operates with that service.
  * fgdatabase: For this release it is necessary to apply the database patch going to fgAPIServer/db_patches directory and executing patch_apply.sh script
  * APIServerDaemon: extract from git; recompile with 'ant all', then place generated war file into $CATALINA_HOME/web's

* Installation methods:
  * Installation can be done using the old fashioned scipt based way or by using ansible roles.
  * Specific instructions are available in the documentatation - https://indigo-dc.gitbooks.io/futuregateway/content/installation.html

* **WARNING**: To allow baseline tests 'helloworld' and 'sayhello' automatically work, please execute as futuregateway user the following command after the installation procedure has completed: 'sed -i 's/Admin/Developers/' $FGLOCATION/fgAPIServer/.iam/groups'

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

* [fgAPIServer_v0.0.7.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/fgAPIServer_v0.0.7.tar.gz)
* Ubuntu 14.04/16.04: 
  * [APIServerDaemon_0.0.7_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/APIServerDaemon_0.0.7_all.deb)
  * [fgapiserver_0.0.7_all.deb
  * ](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/fgapiserver_0.0.7_all.deb)
  
<a id="id6"></a>
## Documentation

* Please refer to [FutureGateway documentation](https://indigo-dc.gitbooks.io/futuregateway/content/)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
