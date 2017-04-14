# INDIGO iOS Library v. 0.1.2


## About

iOS Library Project which simplifies interaction with FutureGateway from mobile devices.

Using the library simplifies your interaction with FutureGateway API.
Implemented requests list:

* Getting tasks list
* Creating new tasks
* Getting details about the task
* Uploading input files
* Downloading output files
* Deleting the task
* Getting applications list

All API requests are performed in separate dispatch queue, so developers don't have to take care about asynchronous calls. Each call returns its result in a callback.

The simple example app is available [here](https://github.com/indigo-dc/omt-ios/tree/master/Example).

## Summary:
* [Release Notes v. 0.1.2](#id1)
  * [What's new](#id2)
  * [List of RfCs](#id3)
  * [Deployment Notes](#id4)
  * [Known Issues](#id5)
  * [List of Artifacts](#id7)
* [Documentation](#id6)
* [Support](#id8)


<a id="id1"></a>
## Release Notes v. 0.1.2

<a id="id2"></a>
### What's new

This is the first versions of library. It allows to access Future Gateway Applications API with IAM tokens.

Supported Platforms:
* iOS >= 9.0

<a id="id3"></a>
#### List of RfCs 

* https://github.com/indigo-dc/omt-ios/issues/1
* https://github.com/indigo-dc/omt-ios/issues/2
* https://github.com/indigo-dc/omt-ios/issues/3
* https://github.com/indigo-dc/omt-ios/issues/4
* https://github.com/indigo-dc/omt-ios/issues/7
* https://github.com/indigo-dc/omt-ios/issues/8
* https://github.com/indigo-dc/omt-ios/issues/10
* https://github.com/indigo-dc/omt-ios/issues/12
* https://github.com/indigo-dc/omt-ios/issues/13
* https://github.com/indigo-dc/omt-ios/issues/15
* https://github.com/indigo-dc/omt-ios/issues/16

<a id="id4"></a>
### Deployment Notes

* https://github.com/indigo-dc/omt-ios#installation

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

* As for the artefacts, the CocoaPods that I used to create and iOS library is to manage source code, not binary code 
  * CocoaPods recursively resolves dependencies between libraries, fetches source code for all dependencies, and creates and maintains an Xcode workspace to build your project. (https://github.com/CocoaPods/CocoaPods)
This library was publish to a public CocoaPods repository here https://cocoapods.org/pods/IndigoOmtIosLibrary
However, a binary is available [here](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/x86_64/tgz/IndigoOmtIosLibrary-0.1.3.zip)


<a id="id6"></a>
## Documentation

* [INDIGO OMT iOS GitBook](https://www.gitbook.com/read/book/indigo-dc/omt-ios)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)<br>
or
* [https://github.com/indigo-dc/omt-android/issues](https://github.com/indigo-dc/omt-ios/issues)
