# dCache v. 3.0.12


The goal of **dCache** project is to provide a system for storing and retrieving huge 
amounts of data, distributed among a large number of heterogenous server nodes, under a single virtual
filesystem tree with a variety of standard access methods. Depending on the Persistency Model, dCache provides 
methods for exchanging data with backend (tertiary) Storage Systems as well as space management, pool attraction, 
dataset replication, hot spot determination and recovery from disk or node failures. Connected to a tertiary storage
system, the cache simulates unlimited direct access storage space. Data exchanges to and from the underlying HSM are 
performed automatically and invisibly to the user. Beside HEP specific protocols, data in dCache can be accessed
via NFSv4.1 (pNFS) as well as through WebDav. 

## Summary:
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

* dCache 3.0.9
  * REST-api:  support querying QoS through namespace
    * Several  improvments has been done for  the error handling for RESTful interface. 
    Currently the error JSON object contains potentially useful information in the message and the bugs are logged.
  * dCache has the concept of a home directory: each user may have a directory that is somehow “theirs”. This information was not available to clients accessing dCache via the REST interface. The current release fixed this and querying /api/v1/user provides the user’s home directory in addition to other user-centric information.
    * The RESTful interface exposed some namespace-targeted information through /api/v1/namespace, and QoS information through /api/v1/qos-management/namespace. This was undesirable as dCache exposes namespace-targeted operations in two places. This is now fixed and the client may obtain information by querying /api/v1/namespace.

* dCache 3.0.8
  * FRONTEND
    * Synchronization with  REST-api changes.

* dCache 3.0.0
  * REST-api: 
    * New functionalities to  create, move and rename resources have been added.
    * The pinmanager was adjusted to perform QoS transition from “disk+tape” to “tape”.
  * WEBDAV: 
    * Spnego based Kerberos authentication mechanism for SSO has been added.
    * Webdav service is now  able to upload files with a PUT using the browser.
    * Faster webdav directory creation is now possible.
    * The generated HTML pages work correctly when proxied by some other web server
    * Fixed an unreleased bug in WebDAV door that caused it to fail to load the errorpage template.
    * Several improvements have been performed to allow clients to handle objects that they don't have permission to access.
           It may be that some users were using that dCache returns the wrong  status-code as a mechanism to clear the browser's BASIC credential  cache (e.g., to "log out").  With this patch, that is not possible and users  must use the facilities the web-browser provides.

Supported platforms:
* CentOS 7 and higher, Scientific Linux 7 and higher, Ubuntu 14.04 and higher

<a id="id3"></a>
#### List of RfCs 

* N/A

<a id="id4"></a>
### Deployment Notes

* Classical package-based installation, see [Installing dCache book](https://www.dcache.org/manuals/book.shtml) 

<a id="id5"></a>
### Known Issues
* N/A

<a id="id7"></a>
### List of Artifacts

Packages:
* [dcache_3.0.12_all.deb](http://repo.indigo-datacloud.eu/repository/indigo/2/ubuntu/dists/xenial/main/binary-amd64/dcache_3.0.12-1_all.deb) 
* [dcache-3.0.12.noarch.rpm](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/base/dcache-3.0.12-1.noarch.rpm)

<a id="id6"></a>
## Documentation

* [dCache Gitbook](https://www.gitbook.com/book/indigo-dc/dcache/details)

<a id="id8"></a>
## Support
* E-mail support is available via [support@dcache.org](support@dcache.org), and a mailing list for discussions amongst users (with the developers participating) is at [user-forum@dcache.org](user-forum@dcache.org).
* GGUS unit: [dCache Support](https://wiki.egi.eu/wiki/GGUS:DCache_Support_FAQ)
* You can also use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)
