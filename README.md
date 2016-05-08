# gradle sample app project  [![Build Status](https://travis-ci.org/mrduguo/gradle-sample-app.svg?branch=master)](https://travis-ci.org/mrduguo/gradle-sample-app)
A demo for spring boot based app based on [mrduguo/gradle-buildscript](https://github.com/mrduguo/gradle-buildscript) project. 


## the only requirement

* JAVA 7 or newer


## sample build command

#### build artifact locally

```
./gradlew
```

* [sample output](/src/doc/sample-build-logs/default-build.log)

#### run the application directly without build

```
./gradlew run
```

* [sample output](/src/doc/sample-build-logs/run.log)

Then the app can be accessed from:

* [http://localhost:8888](http://localhost:8888)


## continious integration build

https://travis-ci.org/mrduguo/gradle-sample-app

It run the same build command as locally, but with `JOB_NAME` environment variable to deploy the artifact to remote bintray maven repository instead of local file system.

* [sample output](https://travis-ci.org/mrduguo/gradle-sample-app/builds/126996208)

#### released artifact

https://dl.bintray.com/mrduguo/maven/com/github/mrduguo/gradle/gradle-sample-app/

After download a released jar file, you may run it with:


```
java -jar gradle-sample-app-*.jar
```

The app then can be accessed from:

* [http://localhost:8888](http://localhost:8888)


## aws deploy

This require you have `~/.aws/credentials` configured


#### build and deploy all in one

```

mavenReleaseRepoUrl=https://s3-eu-west-1.amazonaws.com/elasticbeanstalk-eu-west-1-349318639323/maven-repo/ \
awsEbOverrideExistsEnv=true \
./gradlew clean build aws_eb_deploy
 
```

* [sample output](/src/doc/sample-build-logs/aws-build-and-deploy-all-in-one.log)
* the build output log will contain the service url
* [the zero downtime build and deployment process](/src/doc/the-zero-downtime-build-and-deployment-process.md)

#### the default aws build which will upload artifact to s3

```

mavenReleaseRepoUrl=https://s3-eu-west-1.amazonaws.com/elasticbeanstalk-eu-west-1-349318639323/maven-repo/ \
./gradlew

```

* [sample output](/src/doc/sample-build-logs/aws-build.log)

#### deploy latest build to elastic beanstalk

```

mavenReleaseRepoUrl=https://s3-eu-west-1.amazonaws.com/elasticbeanstalk-eu-west-1-349318639323/maven-repo/ \
awsEbOverrideExistsEnv=true \
./gradlew aws_eb_deploy 

```

* [sample output](/src/doc/sample-build-logs/aws-deploy.log)
