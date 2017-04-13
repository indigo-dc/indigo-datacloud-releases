# INDIGO OpenMobile Toolkit (OMT) v0.8.7

**INDIGO OpenMobile Toolkit** - Android Library Project which simplifies access to INDIGO DataCloud API

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
## Release Notes v. 0.8.6

<a id="id2"></a>
### What's new

Highlights of the second release of the toolkit:
* Now the library for Android enables the access to the Future Gateway Applications API and utilizes 
IAM tokens for user authentication and authorisation. The sample app which is a part of the Android 
library has been redesigned. There are also minor improvements in the communication with FutureGateway API

Supported Platforms:
* Mobile OS: Android 4.2+

<a id="id3"></a>
#### List of RfCs 

* [commits/v0.8.6](https://github.com/indigo-dc/omt-android/commits/v0.8.7)
  * https://github.com/indigo-dc/omt-android/issues/1
  * https://github.com/indigo-dc/omt-android/issues/2
  * https://github.com/indigo-dc/omt-android/issues/3
  * https://github.com/indigo-dc/omt-android/issues/4

<a id="id4"></a>
### Deployment Notes

* the AAR file (the library) can be run/install without sample-app
* the APK file with sample app can be installed on the device via Android Debug Bridge command: ```$ANDROID_HOME/platform-tools/adb install PATH_TO_APK_FILE```

* https://indigo-dc.gitbooks.io/omt-android/content/doc/developer.html

* Ansible playbook available on [GitHub](https://github.com/indigo-dc/omt-android/blob/master/indigo-omt.android.yml)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

* [https://bintray.com/mupsnc/maven/download_file?file_path=pl%2Fpsnc%2Findigo%2Findigo-omt-android-library%2F0.8.6%2Findigo-omt-android-library-0.8.6.aar](https://bintray.com/mupsnc/maven/download_file?file_path=pl%2Fpsnc%2Findigo%2Findigo-omt-android-library%2F0.8.6%2Findigo-omt-android-library-0.8.6.aar)
or
* [indigo-omt-android-library-0.8.7.aar](http://repo.indigo-datacloud.eu/repository/indigo/2/centos7/SRPMS/tgz/indigo-omt-android-library-0.8.7.aar)

<a id="id6"></a>
## Documentation

* [INDIGO OMT GitBook](https://www.gitbook.com/book/indigo-dc/omt-android/details)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)<br>
or
* [https://github.com/indigo-dc/omt-android/issues](https://github.com/indigo-dc/omt-android/issues)
