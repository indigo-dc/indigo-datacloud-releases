The Third Update of INDIGO-1 release contains:
* [Acounting v. 1.2.1-1](#accounting)
* [CMDB v. 0.4.0](#cmdb)
* [FutureGateway](#fg):
  * [fgAPIServer v0.0.5](#fg)
  * [APIServerDaemon v0.0.5](#fg)
  * [PortalSetup v0.0.4](#fg)
* [LiferayIAM v. 1.1.1](#li)
* [Ophidia v. 0.6.1](#tp)
* [Orchent v. 12.0.0](#orchent)
* [Orchestrator v. 1.1.0-FINAL](#orchestrator)
* [Zabbix-probes v. 1.0-2](#orchestrator)


## <a name="cdmi"></a>Accounting v. 1.2.1-1

#### What's new
* THis update provides some enhancemenets, like allowing deployment only of the server container and of locally built images, and few bug fixes, like the ones regarding GET/POST authZ/authN issues

#### List of RfCs
* New Features:
** Accept APEL-Cloud v0.2 usage records via POST requests to the REST endpoint .../api/v1/cloud/record
** Provide access to summaries via GET requests to REST endpoint .../api/v1/cloud/record/summary
** Enhancements to the run_container.sh script, allowing for deploying only the server container and for deploying locally built images.
** Django Rest Framework static files positioned assuming standalone use.
* Patches, Bug Fixes and Documentation updates:
** GET/POST authZ/authN bugs fixed.
** Added instructions to register the service with the Indigo Identity and Access Management (IAM).
** Added "service reference card".
** Increase in test coverage (to 87%)

#### Installation & Configuration
* In order to perform an update please carefully read the instructions available in the [How to update an already deployed service to 1.2.0 (from <1.2.0)](https://indigo-dc.gitbooks.io/accounting/content/doc/admin.html)

#### Artefacts
*Docker Container:
** [indigodatacloud/accounting:indigo_1](https://hub.docker.com/r/indigodatacloud/accounting/)
