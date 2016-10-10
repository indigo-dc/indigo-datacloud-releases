# dCache v. 2.16.7


The goal of **dCache** project is to provide a system for storing and retrieving huge amounts of data, distributed among a large number of heterogenous server nodes, under a single virtual filesystem tree with a variety of standard access methods. Depending on the Persistency Model, dCache provides methods for exchanging data with backend (tertiary) Storage Systems as well as space management, pool attraction, dataset replication, hot spot determination and recovery from disk or node failures. Connected to a tertiary storage system, the cache simulates unlimited direct access storage space. Data exchanges to and from the underlying HSM are performed automatically and invisibly to the user. Beside HEP specific protocols, data in dCache can be accessed via NFSv4.1 (pNFS) as well as through WebDav. 

**Summary**:
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
Highlights of changes for INDIGO - DataCloud project:

* dCache 2.16.6
  * dcache-restful-api: RestfulAPI for QoS(CDMI) CHANGE current QoS for the specified file
    * Users can query Qos for file objects. The current release provides rest-api call to change QoS for files.
* dCache 2.16.5
  * FRONTEND
    * Users can query existing Quality of Services, for example, storage requirements such as flexible allocation of disk or tape storage space. Possibility to query QoS for the specified file object.
  * dcache-restful-api: 
    * fix data type for cdmi_geographic_placement
    * RestfulAPI for QoS(CDMI) get current QoS for the specified file
    * RestfulAPI for QoS(CDMI)
    * make exception and error handling resful
* dCache 2.16.3
  * webdav: avoid NPE if client fails to send a User-Agent header
  * build: add code-coverage reports
    * A code coverage profile was added to the build system to check the coverage of our unit tests. The coverage analysis uses JaCoCo as the technical foundation.
  * WEBDAV
    * There are WebDAV clients that do not send a User-Agent header along with their requests.
    * dCache’s WebDAV code has been updated to avoid NullPointerExceptions occuring in those cases.
* dCache 2.16.2
  * REST-api: fix permission denied.
  * webdav: Fix error reporting when client is unauthorized
    * Until now, trying to access a file for which the client was not authorized would generate a reply with a status code 200 OK, but an empty body, rather than an error page. This patch corrects that behaviour and also improves exception handling for that case.
* dCache 2.16
  * Pin manager database backend was rewritten
    * The pinmanager database backend was rewritten to no longer use the DataNucleus ORM. Minor schema changes are applied during upgrade. Upon downgrade these schema changes must be rolled back using the dcache database rollbackToDate command.
  * Added caching of gPlazma mappings in webdav service
    * The WebDAV service now caches gPlazma mappings. See webdav.service.gplazma.cache.size and webdav.service.gplazma.cache.timeout for the new configuration properties.
  * Generic gPlazma mapping plugin
    * A new generic mapping plugin (multimap) was added to gPlazma. It allows mappings from any principal to multiple other principals. Currently only dn, oidc, username, uid, gid, kerberos, email principals are supported

Supported platforms:
* CentOS 7 and higher, Scientific Linux 7 and higher, Ubuntu 14.04 and higher

<a id="id3"></a>
#### List of RfCs 

* N/A


<a id="id4"></a>
### Deployment Notes

* Classical package-based installation, see [Installing dCache book](https://www.dcache.org/manuals/Book-2.16/start/in-fhs.shtml) 

<a id="id5"></a>
### Known Issues
* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* dcache_2.16.7-1_all.deb
* dcache-2.16.6-1.noarch.rpm

<a id="id6"></a>
## Documentation

* [dCache Gitbook](https://www.gitbook.com/book/indigo-dc/dcache/details)

<a id="id8"></a>
## Support
* E-mail support is available via [support@dcache.org](support@dcache.org), and a mailing list for discussions amongst users (with the developers participating) is at [user-forum@dcache.org](user-forum@dcache.org).
* GGUS unit: [dCache Support](https://wiki.egi.eu/wiki/GGUS:DCache_Support_FAQ)
* You can also use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
