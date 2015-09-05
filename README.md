# Spatialite-Database-Driver

This is a standalone Android library that can be used in an Android application.

See https://github.com/kristina-hager/HelloToSpatialite for an example of using this in a simple spatialite application.

The shared objects and source files in this repository are not mine. They were copied from other sources as explained next. My contribution here is figuring out how to package this library up in the relatively new Android Studio environment, and how to use it in a separate application.

## The original sources

I copied the shared objects from https://github.com/geopaparazzi/geopaparazzi/https://github.com/geopaparazzi/geopaparazzi/tree/master/geopaparazzispatialitelibrary/libs

and the java jsqlite code from https://github.com/geopaparazzi/geopaparazzi/tree/master/geopaparazzispatialitelibrary/src/jsqlite

## Why a standalone library?

Many Android apps today use libraries and lots of the time libraries are built into those apps instead of being separate components.

I wanted to make this library a separate component to make it easier for everyone to download it and use it in their own apps.

Again, see https://github.com/kristina-hager/HelloToSpatialite for an example of using this in a simple spatialite application.

## Credits

I used this application as an example to help me set things up:
https://github.com/geopaparazzi/geopaparazzi

Also thanks to @mj10777 for helping me out in this thread:
https://github.com/geopaparazzi/libjsqlite-spatialite-android/issues/12

and also thanks to countless StackOverflow postings/answers and online tutorials for helping me understand Android Studio, library modules, JNI and so on.

Some articles I found useful during this work as they explained some concept I needed to understand:
- [NDK with Android Studio](http://www.shaneenishry.com/blog/2014/08/17/ndk-with-android-studio/)
- [Java Programming Tutorial: Java Native Interface (JNI)](https://www3.ntu.edu.sg/home/ehchua/programming/java/JavaNativeInterface.html)
- These two sources helped me get started with creating a standalone library module in Android Studio
   - http://stackoverflow.com/questions/22243269/how-to-share-a-single-library-source-across-multiple-projects
   - https://gist.github.com/daniellevass/2c46cf33e3814e685b47

