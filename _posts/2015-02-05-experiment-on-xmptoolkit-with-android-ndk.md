---
layout: post
title: Experiment on XMPToolkit with Android NDK 
date: 2015-02-06
categories:
- open-source
tags:
- open-source
status: publish
type: post
published: true
---
Last week, I had an adventure of compiling XMPToolkit with NDK.  It was a long and terrible trial.  In order to compile it with NDK, there were few existing resources to use:

- exempi : <http://libopenraw.freedesktop.org/wiki/Exempi/>
- Adobe XMPToolkit
    - modified version  
    <https://github.com/janrueegg/xmp>
    - focal link (libraries including XMPToolkit)  
    <https://github.com/xplodwild/android_external_Focal/tree/master/XMPToolkit>
    - focal link 2 (original app)  
    <https://github.com/xplodwild/android_packages_apps_Focal>

##exempi
Exempi is a library (XMPTookit included) for writing/reading information to/from image files designed to work on Linux.   However,  While assuming it might be easy to port to Android, I   I realized the developers are still trying to include XMPToolkit 2013 version in the future updates.  Old version of XMPToolkit definitely wouldn't be the thing we are looking for.

##Offical XMPToolkit
Using offical XMPTookkit is definitely the way to go.  Though, it could be hard to compile with NDK.  A lot of issues have been faced when I tried using the library with NDK.

<http://libopenraw.freedesktop.org/wiki/Exempi/>

###IDE issues
It is probably a bad timing of using NDK for our project.  The reason is that Google presents Android Studio as the main IDE for Android development, at the same time, **NDK would be replaced soon in the future**.  Therefore, there are only two strange choices left for us to use: "NDK with deprecated Eclipse ADT" or "unsupported NDK with Android Studio hacks"


##Modified version
No matter what,  I still want to try out any methods available. The modified version of XMPToolkit can be compiled into static library for Android.  After going through serveral blog posts, the way to include libraries are: 
- add ndk path to local.properties
- puting files with the name of libxxx.a into src/main/jniLibs/(arch) folder  
  (arch: x86, armeabi, armeabi-v7a, mips ...)
- modifying build.gradle to include compiling options

However, it doesn't work for me. Android Studio wasn't able to detect any libraries. XMPToolkit couldn't be compiled as shared library as well, cause the cmake/make files were modified for static linking only.

######Reference:
- <http://ph0b.com/android-studio-gradle-and-ndk-integration/>
- <http://www.shaneenishry.com/blog/2014/08/17/ndk-with-android-studio/>
- <http://stackoverflow.com/questions/25862197/importing-static-library-in-to-android-project>
- <http://stackoverflow.com/questions/27532062/android-studio-include-pre-compiled-static-library-using-ndk>

###Another approach
The focal app is another good resource , because XMPtoolkit source code is included in the focal app with Android.mk (Android make file) file.  Though, there is no instruction of adding those external source code to an app project and Android.mk file is used only for Eclipse.  Therefore, I took it as a reference and tried compiling XMPTookit inside Android Studio.  After two days of stuggling, it was finally compiled successfully without all the useless files.  Well, it turns out it is not a good result:

- takes 5 mins or more to compile. Not very long but could be very annoying.
- compile fails sometime randomly because of multiple definitions of certain object/variable
- compile errors caused by compiling XMPCore and XMPFiles together (it seems there is no way to compile them separately)

Code: <https://github.com/gklo/XmpTest>

##Conclusion
After tried serveral methods, using XMPToolkit with NDK is harder than I could imgine.  It requires the understanding of serveral things: gcc compiler, NDK, Android.mk definitions, and gradle build system.  Mohamed's method is probably the better and simpler choice for us.

UPDATE: this might be helpful!  
<http://kvurd.com/blog/compiling-a-cpp-library-for-android-with-android-studio/>
