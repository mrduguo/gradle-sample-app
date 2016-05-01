# gradle sample app project  [![Build Status](https://travis-ci.org/mrduguo/gradle-sample-app.svg?branch=master)](https://travis-ci.org/mrduguo/gradle-sample-app)
A demo for spring boot based app based on [mrduguo/gradle-buildscript](https://github.com/mrduguo/gradle-buildscript) project. 


### the only requirement

* JAVA 7 or newer


### sample build command

Build artifact locally

```
./gradlew
```

Run the application directly without build

```
./gradlew run
```

The app then can be accessed from:

[http://localhost:8888](http://localhost:8888)


### continious integration build

https://travis-ci.org/mrduguo/gradle-sample-app


### released artifact

https://dl.bintray.com/mrduguo/maven/com/github/mrduguo/gradle/gradle-sample-app/

After download a released jar file, you may run it with:


```
java -jar gradle-sample-app-*.jar
```

The app then can be accessed from:

[http://localhost:8888](http://localhost:8888)