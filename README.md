# Android-Programming-Tools-and-Libraries  
-Android Programming Tools and Libraries--Enhance your Coding practices

As you know that using third-party libraries in your projects can save you a lot of time and also make the projects bugs-free.
We should use this libraries and  tools to increase the quality and decrease the coding time.it will help in retain the quality and bugg free code.
# Smart programming :)  

# Sections  
# Below section will be covered:    
Fabric   
Json preview   
Image processing Library   
Common Library  
Plugins  
Web tools  

# 1. Fabric By Twitter:  

Many powerful tools, one easy platform.
Fabric is product of Twitter and is a mobile platform with modular kits you can mix and match to build the best apps. Fabric is tightly integrated into your dev environment.

#Getting Started
To get up and running with Fabric, sign up for a free account and follow the on-screen instructions to quickly get set up!
https://fabric.io/

Once your account is configured, it’s time to onboard your first app to Fabric by installing a kit. Kits can be installed manually or using the Fabric IDE plugin for Android Studio or IntelliJ.

https://fabric.io/downloads/android

# Fabric tools and library:  
Answers - Real-time analytics and event tracking  
Beta - App distribution for beta testing  
Crashlytics - Best-in-class crash reporting  
Digits - Phone number sign-in  
MoPub - In-app monetization  
Twitter Kit - Twitter login and content  
# Reference  
https://docs.fabric.io/android/crashlytics/build-tools.html  

# 2. Json Preview: 

# Jsonlint:    
This will display formatted json response and will help in debug the json error. You can also compare the json responses 
http://pro.jsonlint.com/
# json2table:  
This will display the formatted json response but the best part is you can see the json response in Table format provide a simplicity in json view.  
http://json2table.com/  
# 3. Image Processing Libraries:    
# Fresco  
Fresco is a Facebook product and powerful system for displaying images in Android applications. It takes care of image loading and display, so you don’t have to. It will load images from the network, local storage, or local resources, and display a placeholder until the image has arrived. It has two levels of cache, one in memory and another in internal storage.  

compile 'com.facebook.fresco:fresco:1.0.1'  

https://github.com/facebook/fresco  
# Picasso / Glide
Picasso/Glide. Excellent and efficient image loading libraries from network and more. But, in my opinion, Glide is the best choice for now. It was included at Google I/O 2014 official application. this is all you need to include this libraries:  
  
/** Picasso **/  
compile 'com.squareup.picasso:picasso:x.y.z'  
/** Glide **/  
compile 'com.github.bumptech.glide:glide:x.y.z'  

# 4. Common Libraries:  

# Event bus  
Android optimized event bus that simplifies communication between Activities, Fragments, Threads, Services, etc. Less code, better quality.  
# Gradle:  
compile 'com.squareup:otto:x.y.z'  

# Device Year Class  
This allows a developer to easily modify application behavior based on the capabilities of the phone’s hardware.  
#Gradle:  
compile 'com.facebook.device.yearclass:yearclass:2.0.0'  



    int year = YearClass.get(getApplicationContext());  
Then, later on, you can use the year class to make decisions in your app, or send it along with your analytics.  
if (year >= 2013) {  
    // Do advanced animation  
} else if (year > 2010) {  
  // Do simple animation  
} else {  
    // Phone too slow, don't do any animations  
}      

# Network Connection Class  
Network Connection Class is an Android library that allows you to figure out the quality of the current user’s internet connection. The connection gets classified into several “Connection Classes” that make it easy to develop against.  

# Gradle:  
compile 'com.facebook.network.connectionclass:connectionclass:1.0.1'  
  
# Stetho  
Stetho is a powerful library for debugging databases and shared preferences in Android applications.
It’s a very simple tool for viewing databases and shared preferences directly in your browser.  
# Gradle:  
compile 'com.facebook.stetho:stetho-okhttp3:1.4.2'  
# //Code snippet  
public class MyApplication extends Application {  
  public void onCreate() {  
    super.onCreate();  
    Stetho.initializeWithDefaults(this);  
  }  
}  
Once you complete the set-up instructions above   

just start your app and point your laptop browser to chrome://inspect. Click the "Inspect" button to begin.  
  
# Leak Canary  
LeakCanary will automatically show a notification when an activity memory leak is detected in your debug build.  
# Gradle:  
dependencies {  
   debugCompile 'com.squareup.leakcanary:leakcanary-android:1.5'  
   releaseCompile 'com.squareup.leakcanary:leakcanary-android-no-op:1.5'  
   testCompile 'com.squareup.leakcanary:leakcanary-android-no-op:1.5'  
 }   
   
# //Code snippet   
  
public class ExampleApplication extends Application {  
  @Override public void onCreate() {  
    super.onCreate();  
    if (LeakCanary.isInAnalyzerProcess(this)) {  
      // This process is dedicated to LeakCanary for heap analysis.   You should not init your app in this process.  
      return;  
    }  
    LeakCanary.install(this);  
      }  
}  
  
# Retrofit 2  
Retrofit still my favorite library when it comes to implementing REST APIs. “Retrofit turns your REST API into a Java interface.”  The request method and relative URL are added with an annotation, which makes code clean and simple. With annotations, you can easily add a request body, manipulate the URL or headers and add query parameters.  
# To include this library add this into your build.gradle file:  
compile 'com.squareup.retrofit2:retrofit:2.y.z'   
compile 'com.squareup.retrofit2:converter-gson:2.y.z'   
compile 'com.squareup.retrofit2:adapter-rxjava:2.y.z' 
    
    
Here’s a simple example how you can use Retrofit with RxJava:   
public interface RestAPI{  
@GET(BuildConfig.PATH_TO_MOVIES_SERVICE)  
Observable<List<Movie>> loadMovies();  
}  
  
# RxJava/RxAndroid  
# RxJava  
is a Java VM implementation of Reactive Extensions, helps you to compose asynchronous, event-based, stream like code and adds functional programming paradigm.  
#Gradle:  
compile 'io.reactivex:rxjava:x.y.z'  

# RxAndroid  
wraps RxJava library. It adds functionality around Android specific threading. Note RxAndroid automatically includes a version of RxJava. However, because RxAndroid releases are behind it and if you want to use latest RxJava,  
# then include both like:  
compile 'io.reactivex:rxandroid:x.y.z'  
compile 'io.reactivex:rxjava:x.y.z'  
# Yeah! Say goodbye to AsyncTasks.  
  
# ButterKnife  
In every Android application, you have to use the findViewById() method for each view in the layout that you want to use in your application’s code. But as applications’ designs get more complex layouts, the call to this method becomes repetitive and this is where the ButterKnife library comes in.
# this is all you need to include this library:   
compile 'com.jakewharton:butterknife:x.y.z'  
//Example:   
@Bind(R.id.firstnameLabel) TextView mFirstNameLabel;  
@Bind(R.id.lastnameLabel) TextView mLastNameLabel;  
@OnClick(R.id.submitButton) void submit() {}  
  
  

# RetroLambda  
it’s a way of using Java 8 Lambdas to Java 6/7 (as well as Android). Makes your code much cleaner, combine it with RxJava and you are solid.  
#Gradle:  
classpath 'me.tatarka:gradle-retrolambda:x.y.z'  
apply plugin: 'me.tatarka.retrolambda'  
Here’s is a simple example how you can use Retrolambda & RxJava  
Observable.just("Hello, world!")  
          .subscribe(s -> System.out.println(s))  ;
Yeah! Clean & concise code.  

# Realm  
is another type of database in Android. But, what is very important, Realm doesn’t use SQLite. If you use ORMLite or ActiveAndroid or any other similar library, your data is stored in SQLite database, because these libraries give us only an overlay on SQLite. With Realm it’s quite different there is no SQLite at all.  
#Gradle:  
classpath 'io.realm:realm-gradle-plugin:x.y.z'  
  
apply plugin: 'realm-android'  
  
# Timber  
Timber is a lightweight library to write logs in different places and control how it’s done in a centralized manner. It’s easy to add it as a dependency of your Android Studio project.  
#Gradle:  
compile 'com.jakewharton.timber:timber:x.y.z'  

# Calligraphy  
Custom fonts in Android an OK way.Are you fed up of Views to set fonts.This library make it easy to integrate multiple custom fonts in an app.  
#Gradle:  
dependencies {  
    compile 'uk.co.chrisjenx:calligraphy:2.2.0'  
}  

# 5. Plugins:  
#Gson Format  
quickly to convert a JSON string to an InnerClassEntity class .  
Reference:   
https://plugins.jetbrains.com/androidstudio/plugin/7654-gsonformat  
  
# ADB Idea  
A plugin for Android Studio and Intellij IDEA that speeds up your day to day android development.  
The following commands are provided:  
-Uninstall App  
-Kill App  
-Start App  
-Restart App  
-Clear App Data  
-Clear App Data and Restart  
Reference:  
https://plugins.jetbrains.com/androidstudio/plugin/7654-gsonformat 

# Android-butterknife-zelezny  
Plugin for generating ButterKnife injections from selected layout XMLs in activities/fragments/adapters.  
Reference:  
https://github.com/avast/android-butterknife-zelezny  

# Android   Drawable Import  
Select assets (or a whole folder) and specify the source resolutions. You can change the source size of every image as well. Specify all resolutions, to which it should be resized to. This works also with 9-Patch-Images. But take care: sometimes it's necessary to remove / add the one or other "pixel" in the 9-Patch-Editor. But just give it a try :)  
Refrence:   
https://plugins.jetbrains.com/idea/plugin/7658-android-drawable-importer  

# Android   Parcelable Code Generator  
Plugin which generates Android Parcelable boilerplate code for you.  
Reference:  
https://github.com/mcharmas/android-parcelable-intellij-plugin  

# Create Intent Method Generator  
Plugin for generates createIntent method for Android Activity  
Refrence:  
https://plugins.jetbrains.com/androidstudio/plugin/8069-createintent-method-generator  

# Genymotion  
This plugin allows you to create and start Genymotion virtual devices from Android Studio.  
Reference:  
https://www.genymotion.com/  

# Android   Methods Count  
A simple Studio/IntelliJ plugin that parses your Android library dependencies and shows the methods count as an handy hint.  
For more information, you can simply tap on the blue circle to the left and you will land on the appropriate library page of this website.  
  
# 6. Web tools  
  
  
# JPEGmini/TinyPng
Your photos, on a diet. Reduce image size by up to 80%, without compromising quality.  
Reference:  
https://tinypng.com/  
http://www.jpegmini.com/  

# Compressify  
One of the best tools to optimize video files online.  
Reference:  
https://compressify.herokuapp.com/  

# Google Fonts  
A showcase of individual type designers and foundries as well as hub to download font families to use in design files.  
Reference:  
https://fonts.google.com/  

# Android   Asset Studio.  
A collection of tools to easily generate assets such as launcher icons for your Android app. Launcher icon generator.  
Reference:  
https://romannurik.github.io/AndroidAssetStudio/  

# Angrytools  
Angrytools offer free online tools for web development and mobile application. online gradient generator for browser and android devices.  
Reference:  
http://angrytools.com/  

# learn Git  
Git allows groups of people to work on the same documents (often code) at the same time, and without stepping on each other's toes. It's a distributed version control system.  
Reference:  
https://try.github.io/levels/1/challenges/1  
  
# Device Art Generator
The device art generator enables you to quickly wrap app screenshots in device artwork. This provides better visual context for your app screenshots.  
Reference:  
https://developer.android.com/distribute/tools/promote/device-art.html  

# At last have great day and happy coding. I have gathered all the information just to give you brief informaion related to the handy tool and library. Hope information will help you and save your time :).  

# References Used:  
https://developer.android.com/index.html  

https://plugins.jetbrains.com/androidstudio  

https://blog.mindorks.com/awesome-android-open-source-libraries-56a008c776c0#.gl8z17dvg  

https://medium.com/cmd-t/75-of-the-best-resources-for-web-designers-98208e8709a#.95j9nd7jy  

https://android.jlelse.eu/android-development-some-useful-libraries-part-i-587626f9e303#.yqr8aqfax  

