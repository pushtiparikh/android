
## Flutter

To use this pipeline in your Flutter project, follow below mentioned steps:

### Prerequisites:

#### iOS:

To generate **Certificate (Certificates.p12) file**:

1. Login to https://developer.apple.com

2. Download Development and Distribution Certificates of your project

3. Open "Keychain Access" application

4. Select your project related **Development** and **Distribution** certificates

5. Install the Development and Distribution certifactes to your keychain.

6. Export as ".p12"

7. Copy the ".p12" file into the **ci-cd**/**iOS**/**certificates** directory in your project root.


To generate **Provisioning profiles (.mobileprovision)**:

1. Login to https://developer.apple.com

2. Download **Development** and **Distribution** Provisioning Profile of your project

3. Copy the ".mobileprovision" file inside **ci-cd**/**iOS**/**provisioningprofiles** directory inside your project root.

***NOTE:*** There will be each provisioning profile for each Flavor and it's related Export Mode. eg: A separate provisioning profile for Dev_Debug and Dev_Release.

  
To generate **Plist (ExportOptions.plist) file**:

1. Setup your project in Xcode.

2. Install Provisioning profiles and certificates related to the project from ci-cd/iOS directory.

3. Archive the project.

4. Select the "Archive" and click on "Distribute App".

5. Select "Development" and complete the "Export" process for Development mode and Select "App Store Connect" option and complete the "Export" process for Production mode.

6. Generate and save Plist files as mentioned in step 5 for all flavors - develop, mock, stage and production which are used in the project.
  

#### Android:

1. [Generating an upload key](https://facebook.github.io/react-native/docs/signed-apk-android#generating-an-upload-key)

2. [Setting up gradle variables](https://facebook.github.io/react-native/docs/signed-apk-android#setting-up-gradle-variables)

3. [Adding signing config to your apps gradle config](https://facebook.github.io/react-native/docs/signed-apk-android#adding-signing-config-to-your-apps-gradle-config)

A typical directory structure will look like below:<br/>
<img src=img/flutter.png>


### Steps:

1. Create a directory named **ci-cd** at project root

2. Inside the **ci-cd** directory create directories named **iOS** and **android**.

3. Put the below directory structure under **iOS** directory with their respective files as mentioned below:

-  **certificates**: This directory will contain Certificate (Certificates.p12) file.

-  **provisioningprofiles**: This directory will contain the Provisioning profiles (.mobileprovision)

-  **\<flavor>** The respective flavor folder in lowercase - develop, mock, stage, production.

-  **debug**: The mentioned flavor's export mode Development specific Plist (ExportOptions.plist) file.

-  **release**: The mentioned flavor's export mode Production specific Plist (ExportOptions.plist) file.


**NOTE:** This structure is supported for more than one flavor.

4. Put the below directory structure under the **android** directory with their respective files as mentioned below:

-  **jks**: This directory will contain the Java KeyStore file required for signing builds.

5. Within this repository goto **flutter** directory and copy **gitlab-ci.yml** to your project root as **.gitlab-ci.yml** (do not forget to put the **.** before file name) <br/>
***NOTE:*** To use a particular version of the pipeline, update the ref section in the .gitlab-ci.yml file with the specific tag. Click this link for the tags changelog: [Flutter Changelog](../CHANGELOG.md#flutter)

6. Change values of the following variables inside **.gitlab-ci.yml** file as per your project, without **<<** & **>>**:

  1.  **PROJECT_NAME**: This would be name of your project e.g. (**BrivityHome**)  

  2. **IOS_PROJECT_NAME**: This would be xcode workspace project name

  - e.g If your xcode workspace name is **BrivityHome.xcodeproj** or **BrivityHome.xcworkspace** then the value of **IOS_PROJECT_NAME** variable would be **BrivityHome** 

  3. **FLAVOR**: This would be the default flavor for the pipeline which would be common for both iOS and Android. eg: develop, mock, stage, production. <br/>

7. Commit and push


**Note: This document assumes that you have experience working with Xcode and Android Studio**

## Firebase App Distribution

We can use the **latest** tag for getting the latest updates. This feature is available from the release and above:
 - flutter-v1.2 <br/>

To use this feature in the project, the following code snippet must be added:
```
- project: sunflowerlab/operations/pipelines
  ref: <tag>
  file: '<technology>/firebase.yml'
```
where we need to replace the value of \<tag> with the respective tag release we want to use and the value of \<technology> from either of ios, kotlin and flutter. <br/>

***NOTE:*** You can refer to the [CHANGELOG.md](../CHANGELOG.md) for the reference of the tags

You can disable this feature by setting the variable APP_DISTRIBUTION to value "False" in your .gitlab-ci.yml file's variable section.
