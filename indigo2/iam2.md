# INDIGO IAM v. 0.6.0

The **Identity and Access Management Service** provides a layer where identities, enrollment, group membership and other attributes and authorization policies on distributed resources can be managed in an homogeneous way, supporting the federated authentication mechanisms supported by the INDIGO AAI. The IAM service provides user identity and policy information to services so that consistent authorization decisions can be enforced across distributed services.

## Summary:

* Updates
  * [INDIGO IAM v. 1.0.0](https://indigo-dc.gitbooks.io/indigo-datacloud-releases/content/indigo2/fourth_update_of_indigo-2.html#iam)<br>

* [Release Notes v0.6.0](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v0.6.0

<a id="id2"></a>
### What's new

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

<a id="id3"></a>
#### List of RfCs 

* Milestone v0.6.0 on github:
  * https://github.com/indigo-iam/iam/issues?utf8=?&q=milestone%3Av0.6.0%20
  * https://github.com/indigo-iam/iam/milestone/2

<a id="id4"></a>
### Deployment Notes

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

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

Docker Container:
* [indigodatacloud/iam-login-service:indigo_2](https://hub.docker.com/r/indigodatacloud/iam-login-service/)

<a id="id6"></a>
## Documentation

* [INDIGO IAM GitBook](https://indigo-dc.gitbooks.io/iam/content/)


<a id="id8"></a>
## Support

* [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
* [INDIGO AAI Task Force mailing list](https://lists.indigo-datacloud.eu/sympa/sigrequest/indigo-aai-tf)
* [INDIGO AAI on Slack](https://indigo-aai.slack.com/)
