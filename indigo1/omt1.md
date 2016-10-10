# INDIGO OpenMobile Toolkit (OMT) v0.7.3

**INDIGO OpenMobile Toolkit** - Android Library Project which simplifies access to INDIGO DataCloud API

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

Highlights of the first release of the toolkit:
* basic communication with FutureGateway API
* getting tasks
* creating tasks
* filtering tasks by status and by user
* getting task's details
* preparation for passing the access token from IAM

Supported Platforms:
* Mobile OS: Android 4.2+

<a id="id3"></a>
#### List of RfCs 

* [commits/v0.7.3](https://github.com/indigo-dc/omt-android/commits/v0.7.3)

<a id="id4"></a>
### Deployment Notes

* the AAR file (the library) can be run/install without sample-app
* the APK file with sample app can be installed on the device via Android Debug Bridge command: ```$ANDROID_HOME/platform-tools/adb install PATH_TO_APK_FILE```

* Ansible playbook available on [GitHub](https://github.com/indigo-dc/omt-android/blob/master/indigo-omt.android.yml)

<a id="id5"></a>
### Known Issues

* N/A

<a id="id7"></a>
### List of Artifacts

* [https://jcenter.bintray.com/pl/psnc/indigo/indigo-omt-android-library/0.7.3/indigo-omt-android-library-0.7.3.aar](https://jcenter.bintray.com/pl/psnc/indigo/indigo-omt-android-library/0.7.3/indigo-omt-android-library-0.7.3.aar)

<a id="id6"></a>
## Documentation

* [INDIGO OMT GitBook](https://www.gitbook.com/book/indigo-dc/omt-android/details)

<a id="id8"></a>
## Support

* Please use the [INDIGO - DataCloud CatchAll GGUS Support Unit](https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ)<br>
or
* [https://github.com/indigo-dc/omt-android/issues](https://github.com/indigo-dc/omt-android/issues)
