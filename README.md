# Spatialite-Database-Driver

I created Spatialite-Database-Driver to enable the usage of [spatialite android](https://www.gaia-gis.it/fossil/libspatialite/wiki?name=splite-android) in Android applications in more recent Android Studio (v1.3) build environments.

See [HelloToSpatialite](https://github.com/kristina-hager/HelloToSpatialite) for an example of using this  module in a simple spatialite application.

The shared objects and source files in this repository are not mine. They were copied from other sources as explained next. My contribution here is figuring out how to package this library up in the relatively new Android Studio environment and how to use it in a separate application.

## The original sources

I copied the shared objects from [geopaparazzispatialitelibrary/libs](https://github.com/geopaparazzi/geopaparazzi/tree/master/geopaparazzispatialitelibrary/libs)

and the java jsqlite code from [geopaparazzispatialitelibrary/src/jsqlite](https://github.com/geopaparazzi/geopaparazzi/tree/master/geopaparazzispatialitelibrary/src/jsqlite)

## Why a standalone library?

Many Android apps today use libraries and lots of the time libraries are embedded in those apps instead of being separate components.

I wanted to make this library a separate component to make it easier for everyone to download it and use it in their own apps.


## Key points in setting this up

### Setting up a generic Android module

I followed these two posts to create that standalone module since it is not something Android Studio does for you automatically:
- http://stackoverflow.com/questions/22243269/how-to-share-a-single-library-source-across-multiple-projects
- https://gist.github.com/daniellevass/2c46cf33e3814e685b47

I followed the steps in the first link except for step 2 where I had to refer to the second post to know to rename the folder at the terminal and drag the build.gradle.

In this repository, [Credits.java](https://github.com/kristina-hager/Spatialite-Database-Driver/blob/master/spatialite-db-driver/src/main/java/pimp/spatialite_database_driver/Credits.java) shows a vanilla example of java that you might see in a module.

There is a lot you can do in a module, of course, beyond this.

### Setting up jsqlite in this module

I copied the contents (shared objects in their architecture specific folders) from:
- [geopaparazzispatialitelibrary/libs](https://github.com/geopaparazzi/geopaparazzi/tree/master/geopaparazzispatialitelibrary/libs)

to
- [spatialite-db-driver/src/main/java/jniLibs](https://github.com/kristina-hager/Spatialite-Database-Driver/tree/master/spatialite-db-driver/src/main/java/jniLibs)

I copied the jsqlite java from:
- [geopaparazzispatialitelibrary/src/jsqlite](https://github.com/geopaparazzi/geopaparazzi/tree/master/geopaparazzispatialitelibrary/src/jsqlite)

to:
- [spatialite-db-driver/src/main/java/jsqlite](https://github.com/kristina-hager/Spatialite-Database-Driver/tree/master/spatialite-db-driver/src/main/java/jsqlite)

*Important!* I had to remove the 'mycompany' scoping from the AndroidManifest to enable projects using this module to invoke 'import jsqlite;'.
- [spatialite-db-driver/src/main/AndroidManifest.xml](https://github.com/kristina-hager/Spatialite-Database-Driver/blob/master/spatialite-db-driver/src/main/AndroidManifest.xml)
 
Now the library is ready to use!

Any project wishing to use this module will need to take some steps as shown in [HelloToSpatialite](https://github.com/kristina-hager/HelloToSpatialite).
 

## Credits

- I used this application as an example to help me set things up and as a source for java and shared objects:
   - https://github.com/geopaparazzi/geopaparazzi

- Thanks to @mj10777 for helping me out in this thread:
   - https://github.com/geopaparazzi/libjsqlite-spatialite-android/issues/12

Some articles I found useful during this work as they explained some concept I needed to understand:
- [NDK with Android Studio](http://www.shaneenishry.com/blog/2014/08/17/ndk-with-android-studio/)
- [Java Programming Tutorial: Java Native Interface (JNI)](https://www3.ntu.edu.sg/home/ehchua/programming/java/JavaNativeInterface.html)
- These two sources helped me get started with creating a standalone library module in Android Studio
   - http://stackoverflow.com/questions/22243269/how-to-share-a-single-library-source-across-multiple-projects
   - https://gist.github.com/daniellevass/2c46cf33e3814e685b47


