# Fifth Update of INDIGO-1

The Fifth Update of INDIGO-1 release contains:
* [FutureGateway](#fg):
  * [fgAPIServer v0.0.6](#fg)
  * [APIServerDaemon v0.0.6](#fg)
  * [PortalSetup v0.0.5](#fg)
* [RepoSync v.1.2.0-1](#rs)

<!--
* [INDIGO IAM v. 0.4.0](#iam)
-->

## <a name="fg"></a>FutureGateway
### <a name="fgas"></a>fgAPIServer & APIServerDaemon v0.0.6, PortalSetup v. 0.0.5
#### What's new
* This release introduces several fixes improving FG stability in relation with the ToscaIDC EI usage. The most important features are related to:
  * The fresh token extraction with PTV during task status check (long runnning tasks foreseeing the expiration of the token used at the creation time)
  * The possibility to download input files with accessible API' urls. 
  * The possibility to delete TOSCA resources by API calls using the PATCH request on tasks endpoint.

#### List of RfCs
* fgAPIServer v0.0.6
  * [Issue#15](https://github.com/indigo-dc/fgAPIServer/issues/15) Downloadable input files: Once a task receives input files, next GET calls to the task will provide the "url" string to access the file
  * [Issue#16](https://github.com/indigo-dc/fgAPIServer/issues/16) PTV tester service has been updated to the last PTV specs in accordance with latest changes of LiferayIAM
  * [Issue#17](https://github.com/indigo-dc/fgAPIServer/issues/17) PATCH call on status change; used to instruct the ToscaIDC EI to delete the TOSCA resource
  * [Issue#18](https://github.com/indigo-dc/fgAPIServer/issues/18) Tester application toscaIDC configured to use the PTV tester; this makes consistent the baseline FG installation
  * [Issue#19](https://github.com/indigo-dc/fgAPIServer/issues/19) Including the incoming subject field when managing PTV: This involved a new field in database table fg_token (subject)
  * [Issue#20](https://github.com/indigo-dc/fgAPIServer/issues/20) New db patch script and new baseline database setup script, aligned to schema v0.0.9
  * [Issue#21](https://github.com/indigo-dc/fgAPIServer/issues/21) Aligning db schema check to v0.0.9
  * [Issue#22](https://github.com/indigo-dc/fgAPIServer/issues/22) GET task call does not show tasks in PURGED status (see APIServerDaemon)

* APIServerDaemon v0.0.6
  * [Issue#13](https://github.com/indigo-dc/APIServerDaemon/issues/13) New db schema check to v0.0.9
  * [Issue#14](https://github.com/indigo-dc/APIServerDaemon/issues/14) Including in build.xml the 'test' target using junit and mokito
  * [Issue#15](https://github.com/indigo-dc/APIServerDaemon/issues/15) PTV fresh token extraction in ToscaIDC EI while checking task status
  * [Issue#16](https://github.com/indigo-dc/APIServerDaemon/issues/16) Managing PATCH call on status change in ToscaIDC EI
  * [Issue#17](https://github.com/indigo-dc/APIServerDaemon/issues/17) Deleted tasks will not include record deletion in task table; a special PURGED status will be applied to task: This caused a 'dangerous' internal task_id recycling when deleting a task that is the last record in task table.
  * [Issue#18](https://github.com/indigo-dc/APIServerDaemon/issues/18) ToscaIDC loads its own .properties file includng PTV configuration (address, port, user and password)
  * [Issue#19](https://github.com/indigo-dc/APIServerDaemon/issues/19) ToscaIDC adds UUID info in runtime_data
  * [Issue#20](https://github.com/indigo-dc/APIServerDaemon/issues/20) ToscaIDC adds PTV subject field in runtime data if subject exists: This is important for GUIs to filter out tasks not belongin to the portal user. The FG user field currently stores the PTV mapped user.

* PortalSetup
  * [Issue#3](https://github.com/indigo-dc/PortalSetup/issues/3) Wrong warning message while installing related to SYSCTL
  * [Issue#4](https://github.com/indigo-dc/PortalSetup/issues/4) Maven and ant installed by packages
  * [Issue#5](https://github.com/indigo-dc/PortalSetup/issues/5) Improving package installation procedure (for loop change)
  * [Issue#6](https://github.com/indigo-dc/PortalSetup/issues/6) Suggested wsgi configuration

#### Installation & Configuration
* [FutureGateway documentation on GitBook](https://indigo-dc.gitbooks.io/futuregateway/content/) has been updated accordingly to the introduced changes.

* To update an existing system; it is requested to update the database with the patching mechanism as described below:
  * go to the directory $FGLOCATION/fgAPIServer/db_patches
    * execute script patch_apply.sh
    * Download from git fgAPIServer and APIServerDaemon files. The first does not need to be compiled, while the second requires the following actions:
      a1) execute "ant all"
      a2) copy the generated war file in directory $CATALINA_HOME/webapps and wait for the APIServerDaemon application replacement watching file $CATALNA_HOME/logs/catalina.out
  * During the update process it is important to do not overwrite existing configuration files or application directories
  * The update is now ready.

#### Artefacts
* CentOS7
  * [fgAPIServer-v0.0.6.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/fgAPIServer-v0.0.6.tar.gz)
  * [APIServerDaemon-v0.0.6.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/APIServerDaemon-v0.0.6.tar.gz)
  * [PortalSetup-v0.0.5.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/SRPMS/tgz/PortalSetup-v0.0.5.tar.gz)
* Ubuntu14.04
  * [fgAPIServer-v0.0.6.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/source/fgAPIServer-v0.0.6.tar.gz)
  * [APIServerDaemon-v0.0.6.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/source/APIServerDaemon-v0.0.6.tar.gz)
  * [PortalSetup-v0.0.5.tar.gz](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/source/PortalSetup-v0.0.5.tar.gz)


<!--
## <a name="iam"></a>INDIGO IAM v.0.5.0

#### What's new
* This release provides new functionality and some bug fixes

#### List of RfCs
* Groups are now encoded in the JSON returned by the IAM /userinfo endpoint as an array of group names.
* Group information is also exposed by the token introspection endpoint
* External authentication information (i.e. when a user authenticates with Google or SAML instead of username/password) is now provided in the JSON returned by the /userinfo endpoint
* The first incarnation of the administrative dashboard is now included in the service
* The first incarnation of the registration service is now included. The registration service implements a "self-register with admin approval" registration flow
* User passwords are now encoded in the database using the Bcrypt encoder
* A password forgotten service is now provided

* More information about bug fixes and other developments can be found on our [JIRA release board](https://issues.infn.it/jira/browse/INDIAM/fixforversion/13811) 

#### Installation & Configuration
* If the installation was done following the the instructions available in the [INDIGO-IAM Deployment and Administration Guide](https://indigo-dc.gitbooks.io/iam/content/doc/admin.html), please follow the following steps to upgrade:<br>
     ``` docker pull indigodatacloud/iam-login-service ``` <br>
     ``` docker stop iam-login-service ``` <br>
     ``` docker rm iam-login-service ``` <br>
     ``` docker run \  ``` <br>
     ```   --name iam-login-service --net=iam -p 8080:8080 \  ``` <br>
     ```   --env-file=/path/to//iam-login-service/env \  ``` <br>
     ```   -v /path/to//keystore.jks:/keystore.jks:ro \  ``` <br>
     ```   indigodatacloud/iam-login-service:indigo_1   ``` <br>

#### Artefacts
* Docker Container:
  * [indigodatacloud/iam-login-service:indigo_1](https://hub.docker.com/r/indigodatacloud/iam-login-service/tags/)

-->
## <a name="im"></a>RepoSync v1.2.0-1

#### What's new
* Added service support to Ubuntu 14.04 and CentOS 7. Packages are now dependent on jsvc
* Added support for HTTPS

#### List of RfCs

* [Issue #42](https://github.com/indigo-dc/java-reposync/issues/42) - Create init services
* [Issue #449](https://github.com/indigo-dc/java-reposync/issues/449) - Support HTTPS

#### Installation & Configuration
In order to update the packages please use:
* Just install the new packages over the old ones. It should ask if you want to replace the existing configuration so don't do it. It should work just 
fine with the old one. In case SSL support is needed, please configure the properties described at [https://github.com/indigo-dc/java-reposync/blob/master/docs/configuration.md](https://github.com/indigo-dc/java-reposync/blob/master/docs/configuration.md)


#### Artefacts
* CentOS7
  * [indigo-dc-reposync-1.2.0-1.noarch.rpm	](http://repo.indigo-datacloud.eu/repository/indigo/1/centos7/x86_64/updates/indigo-dc-reposync-1.2.0-1.noarch.rpm	)
* Ubuntu14.04
  * [reposync_1.2.0_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/1/ubuntu/dists/trusty-updates/main/binary-amd64/reposync_1.2.0_all.deb)

<!--
* Container
  * [indigodatacloud/im:indigo_1](https://hub.docker.com/r/indigodatacloud/im/tags/)
-->  
