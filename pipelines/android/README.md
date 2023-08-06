## Android

To use this pipeline in your Kotlin project, follow below mentioned steps:

### [](#prerequisites)Prerequisites:

Integrate the  **SonarQube plugin** inside gradle and verify the sonar properties.

### [](#steps)Steps:

1.  Within this repository goto **android** directory and copy **gitlab-ci.yml** to your project root as **.gitlab-ci.yml** (do not forget to put the **.** before file name) <br/>
***NOTE:*** To use a particular version of the pipeline, update the ref section in the .gitlab-ci.yml file with the specific tag. Click this link for the tags changelog: [Android Changelog](../CHANGELOG.md#android)
2.  Change values of:
    1.  **PROJECT_NAME**: This would be name of your project. e.g. (**BaseProjectAndroid**)
    2.  **ANDROID_COMPILE_SDK**: This would be the Android version of you project. e.g. (**28**)
    3.  **ANDROID_BUILD_TOOLS**: This would be the build tools version of your project. e.g. (**28.0.3**)
3.  Commit and push


**Note: This document presumes that you have experience working with  Android Studio**
