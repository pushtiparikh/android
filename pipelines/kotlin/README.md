## Kotlin

To use this pipeline in your Kotlin project, follow below mentioned steps:

### [](#prerequisites)Prerequisites:

Integrate the  **SonarQube plugin** inside gradle and verify the sonar properties.

### [](#steps)Steps:

1.  Within this repository goto **kotlin** directory and copy **gitlab-ci.yml** to your project root as **.gitlab-ci.yml** (do not forget to put the **.** before file name) <br/>
***NOTE:*** To use a particular version of the pipeline, update the ref section in the .gitlab-ci.yml file with the specific tag. Click this link for the tags changelog: [Kotlin Changelog](../CHANGELOG.md#kotlin)
2.  Change values of:
    1.  **PROJECT_NAME**: This would be name of your project. e.g. (**BaseProjectKotlin**)
    2.  **ANDROID_COMPILE_SDK**: This would be the Android version of your project. e.g. (**28**)
    3.  **ANDROID_BUILD_TOOLS**: This would be the build tools version of your project. e.g. (**28.0.3**)
    4.  **FLAVOR**: This would be the default Android Flavor your project. e.g (**Dev**) The currently allowed values are: Dev, Mock and Production.
3.  Commit and push


**Note: This document presumes that you have experience working with  Android Studio**

## Firebase App Distribution

We can use the **latest** tag for getting the latest updates. This feature is available from the release and above:
 - kotlin-v1.3 <br/>

To use this feature in the project, the following code snippet must be added:
```
- project: sunflowerlab/operations/pipelines
  ref: <tag>
  file: '<technology>/firebase.yml'
```
where we need to replace the value of \<tag> with the respective tag release we want to use and the value of \<technology> from either of ios, kotlin and flutter. <br/>

***NOTE:*** You can refer to the [CHANGELOG.md](../CHANGELOG.md) for the reference of the tags

You can disable this feature by setting the variable APP_DISTRIBUTION to value "False" in your .gitlab-ci.yml file's variable section.
