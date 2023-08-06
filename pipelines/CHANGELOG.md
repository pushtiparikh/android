
# Changelog
This document contains all the version history of the mobile CI-CD pipelines for the technologies - [Android](#android), [Flutter](#flutter), [iOS](#ios), [Kotlin](#kotlin), [ReactNative](#reactnative).
These tags refer to a particular pipeline code which contains the features listed in this document.
To use a particular version of the pipeline, update the **ref** section in the **.gitlab-ci.yml** file with the specific tag. <br/>
***NOTE:*** To get the latest updates, use **latest** tag.

## Firebase App Distribution

This feature is available for technologies - Flutter, iOS and Kotlin.
The support for the app distribution is from the releases and above:
 - ios-v1.4
 - flutter-v1.2
 - kotlin-v1.3 <br/>

To use this feature in the project, the following code snippet must be added:
```
- project: sunflowerlab/operations/pipelines
  ref: <tag>
  file: 'flutter/firebase.yml'
```
where we need to replace the value of \<tag> with the respective tag release we want to use. </br>

***NOTE:*** You can refer to the individual technology **.gitlab-ci.yml** file and their documentation for further reference.

You can disable this feature by setting the variable APP_DISTRIBUTION to value "False" in your .gitlab-ci.yml file's variable section.
## Android

### android-v1.2 - 2020-10-15
#### Changes:
- Every pipeline job manual except SonarQube analysis.
- Pipeline code enhancements.
- S3 upload path changes.
- Release builds restricted to develop, stage and master branches.

### android-v1.1 - 2020-02-06
#### Fixes:
- Gitlab runner concurrency issue by having separate runner for every technology.
- Sonarqube PROJECT_NAME and PROJECT_KEY ambiguity.

### android-v1.0  - 2020-01-03
#### Additions:
- SonarQube analysis performed on every push in the repository.
- Generating and storing artifacts in Gitlab for debug and release builds (without flavor support ) for 1 day.
- S3 deployment for the corresponding artifact build.
- Release builds restricted to develop and master branches.

## Flutter

### flutter-v1.2 - 2020-12-1
#### Additions:
- Firebase App Distribution for debug builds. For more information, refer [Firebase App Dist](#firebase-app-distribution)

### flutter-v1.1 - 2020-10-15
#### Additions:
- SonarQube analysis perfomed on every push in the repository.
- Generating and storing artifacts in Gitlab for debug and release builds (with flavor support) for 1 day.
- S3 deployment for the corresponding artifact build.
- Release builds restricted to develop and master branches.

## iOS

### ios-v1.4 - 2020-12-1
#### Additions:
- Firebase App Distribution for debug builds. For more information, refer [Firebase App Dist](#firebase-app-distribution)

### ios-v1.3 - 2020-10-15
#### Additions:
- Generating and storing artifacts in Gitlab for debug and release builds (with flavor support) for 1 day.

#### Changes:
- Pipeline code enhancements.
- All stages kept manual.
- S3 upload path changes.

### ios-v1.2 - 2020-06-22
#### Changes:
- SonarQube analysis disabled as iOS code analysis is not yet fully supported in SonarQube.

### ios-v1.1 - 2020-02-06
#### Fixes:
- Gitlab runner concurrency issue by having separate runner for every technology.
- Sonarqube PROJECT_NAME and PROJECT_KEY ambiguity.

### ios-v1.0 - 2020-01-03
#### Additions:
- SonarQube analysis perfomed on every push in the repository.
- Generating and storing artifacts in Gitlab for debug and release builds (without flavor support) for 1 day.
- S3 deployment for the corresponding artifact build.
- Release builds restricted to develop and master branches.
- Automated certificate and mobile provision installations.

## Kotlin

### kotlin-v1.3 - 2020-12-1
#### Additions:
- Firebase App Distribution for debug builds. For more information, refer [Firebase App Dist](#firebase-app-distribution)

### kotlin-v1.2 - 2020-10-15
#### Additions:
- Generating and storing artifacts in Gitlab for debug and release builds (with multiple flavor support) for 1 day.

#### Changes:
- Pipeline code enhancements.
- All stages kept manual except SonarQube analysis.
- S3 upload path changes.
- Release builds restricted to develop, stage and master branches.

### kotlin-v1.1 - 2020-02-06
#### Fixes:
- Gitlab runner concurrency issue by having separate runner for every technology.
- Sonarqube PROJECT_NAME and PROJECT_KEY ambiguity.

### kotlin-v1.0 - 2020-01-03
#### Additions:
- SonarQube analysis perfomed on every push in the repository.
-  Unit testing (beta phase).
- Generating and storing artifacts in Gitlab for debug and release builds (with flavor support for Dev and Production flavors only) for 1 day.
- S3 deployment for the corresponding artifact build.
- Release builds restricted to develop and master branches.

## ReactNative

### reactnative-v1.5 - 2020-10-15
#### Changes:
- Pipeline code enhancements.
- All stages kept manual.
- S3 upload path changes.

### reactnative-v1.4 - 2020-02-06
#### Fixes:
- Gitlab runner concurrency issue by having separate runner for every technology.
- Sonarqube PROJECT_NAME and PROJECT_KEY ambiguity.

### reactnative-v1.3 - 2020-01-03
#### Fixes:
- SonarQube block fixes.
- Tag fixes.
- When condition fixes.

### reactnative-v1.2 - 2019-12-17
#### Fixes:
- SonarQube analysis script command changes.
- Android licences accept block changes.
- Tag changes.
- Dependency block fixes.
- Release builds restricted to develop and master branches.

### v1.1 - 2019-12-12
#### Fixes:
- Release profile build and deployment automated.
- No logs redirection for xcodebuild.

### v1.0 - 2019-12-11
#### Additions:
- SonarQube analysis perfomed on every push in the repository.
- Generating and storing artifacts in Gitlab for debug and release builds (without flavor support) for 1 day.
- S3 deployment for the corresponding artifact build.
- Automated certificate and mobile provision installations.
