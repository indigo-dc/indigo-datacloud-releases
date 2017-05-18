# Nineth Update of INDIGO-1 - 03.05.2017

The Nineth Update of INDIGO-1 release contains:
* [INDIGO IAM v. 0.6.0](#iam)
* [Orchestrator v. 1.2.2-FINAL](#orchestrator)

## <a name="iam"></a>INDIGO IAM v.0.6.0

#### What's new
Highlights of the 0.6.0 release:
* Support audience enforcement on access tokens
* Nested groups
* Configurable token and approval cleanup period
* Improved performance for some inefficient queries
* Improved audit log
* Bug fixing

More details:
https://github.com/indigo-iam/iam/issues?utf8=?&q=milestone%3Av0.6.0%20
or
https://github.com/indigo-iam/iam/milestone/2

Supported Platforms:
* The **IAM** service is currently distributed as a docker image from Dockerhub, so in order to run the service, you will need Docker v. 1.11.1 or greater. If you want to use docker-compose to deploy the service, you will also need docker-compose v.1.7.0 or greater.


#### List of RfCs

* Milestone v0.6.0 on github:
  * https://github.com/indigo-iam/iam/issues?utf8=?&q=milestone%3Av0.6.0%20
  * https://github.com/indigo-iam/iam/milestone/2
  
* More information about bug fixes and other developments can be found on our [HitHub IAM issue tracker](https://github.com/indigo-iam/iam/releases/tag/v0.5.0) 

#### Installation & Configuration
* *How to upgrade already deployed service*:
  * If you've followed the gitbook guide (https://indigo-dc.gitbooks.io/iam/content/doc/admin.html), you could do as follows:</br>
```docker pull indigodatacloud/iam-login-service```</br>
```docker stop iam-login-service```</br>
```docker rm iam-login-service```</br>
```docker run \```</br>
```  --name iam-login-service --net=iam -p 8080:8080 \```</br>
```  --env-file=/path/to/iam-login-service/env \```</br>
```   -v /path/to/keystore.jks:/keystore.jks:ro \```</br>
```  indigodatacloud/iam-login-service```</br>

* *Service Reference*
  * IAM gitbook: https://indigo-dc.gitbooks.io/iam/content/doc/admin.html


* Please read the [Deployment and Administration guide](https://indigo-dc.gitbooks.io/iam/content/doc/admin.html)

<a id="id7"></a>
#### Artefacts

* Docker Container:
  * [indigodatacloud/iam-login-service:indigo_1](https://hub.docker.com/r/indigodatacloud/iam-login-service/)

## <a name="orchestrator"></a>Orchestrator v. 1.2.2-FINAL

#### What's new
* The current update enabled authentication with SLAM service.

#### List of RfCs
* Improvements:
  * [Issue #189](https://project.indigo-datacloud.eu/work_packages/189) - Enabled authentication with SLAM service

#### Installation & Configuration
No special operations will be required for the upgrade. Thus, the upgrade operations are:
* Stop the old container:</br>
  ```sudo docker stop orchestrator```</br>
* Remove the old container:</br>
  ```sudo docker rm orchestrator```</br>
* Pull the new image version:<br>
  ```sudo docker pull indigodatacloud/orchestrator:1.2.1-FINAL```</br>
* Start the new version:</br>
  ```docker run ...*updated parameters*... indigodatacloud/orchestrator:1.2.1-FINAL```</br>

#### Artefacts
* Docker Container:
  * [indigodatacloud/orchestrator:indigo_1](https://hub.docker.com/r/indigodatacloud/orchestrator/)

