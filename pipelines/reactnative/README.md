## ReactNative
To use this pipeline in your ReactNative project, follow below mentioned steps:

### Prerequisites:
#### iOS:
To generate **Certificate (Certificates.p12) file**:
  1. Login to https://developer.apple.com
  2. Download Development and Distribution Certificates of your project
  3. Open "Keychain Access" application
  4. Select your project related **Development** and **Distribution** certificates
  5. Export as ".p12"

To generate **Provisioning profiles (.mobileprovision)**:
  1. Login to https://developer.apple.com
  2. Download **Development** and **Distribution** Provisioning Profile of your project

To generate **Plist (ExportOptions.plist) file**:
  1. Setup your project in Xcode
  2. Install Provisioning profiles and certificates related to the project from ci-cd directory
  3. Archive the project
  4. Select the "Archive" and click on "Distribute App"
  5. Select "iOS App Store" option and complete the "Export" process

#### Android:

 1. [Generating an upload key](https://facebook.github.io/react-native/docs/signed-apk-android#generating-an-upload-key)
 2. [Setting up gradle variables](https://facebook.github.io/react-native/docs/signed-apk-android#setting-up-gradle-variables)
 3. [Adding signing config to your apps gradle config](https://facebook.github.io/react-native/docs/signed-apk-android#adding-signing-config-to-your-apps-gradle-config)

### Steps:
 1. Create a directory named **ci-cd** at project root
 2. Inside the **ci-cd** directory create a directory named **iOS**
 3. Put below mentioned files inside **iOS** directory
	 - Provisioning profiles (.mobileprovision)
	 - Plist (ExportOptions.plist) file
	 - Certificate (Certificates.p12) file
 4. Within this repository goto **reactnative** directory and copy **gitlab-ci.yml** to your project root as **.gitlab-ci.yml** (do not forget to put the **.** before file name) <br/>
 ***NOTE:*** To use a particular version of the pipeline, update the ref section in the .gitlab-ci.yml file with the specific tag. Click this link for the tags changelog: [ReactNative Changelog](../CHANGELOG.md#reactnative)
 To view the changelog click 
 5. Change values of: 
	 1.  **PROJECT_NAME**: This would be name of your project e.g. (**BrivityHome**)
	 2.  **IOS_PROJECT_NAME**: This would be xcode workspace project name
		 - e.g If your xcode workspace name is **BrivityHome.xcodeproj** or **BrivityHome.xcworkspace** then the value of **IOS_PROJECT_NAME** variable would be **BrivityHome**
	 3.  **IOS_SCHEME_NAME**:  This would be xcode workspace scheme name<br/>
	variables inside **.gitlab-ci.yml** file as per your project, without **<<** & **>>**
 6. Commit and push


**Note: This document presumes that you have experience working with Xcode and Android Studio**
