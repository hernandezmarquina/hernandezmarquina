+++
author = "Jonathan Hdez"
categories = ["Xcode", "Swift"]
date = "2017-12-11"
description = "Swift and Objective-C in the Same Project"
featuredalt = "Download Objetive-C library"
featuredpath = "date"
linktitle = ""
title = "Using Objective-C libraries in Swift"
type = "post"

+++

In this post I'm going to write how you can use Objective-c libraries in your Swift project. 

Xcode projects can contain either language, you can use this feature called _Mix and Match_ to implement the latest swift features in your existing Objective-C proyect, or use objective-c code in new swift apps.


For this example, I'm going to import **[ProgressHUD](https://github.com/relatedcode/ProgressHUD)** library, a lightweight and easy-to-use HUD for iOS. (Objective-C)


**1. Clone or Download [ProgressHUD](https://github.com/relatedcode/ProgressHUD)  from Github.**

!["Download ProgressHUD"](/img/2017/12/Step1-Download-ObjectiveC-Library.png)

In Objective-C, there are `.m` and `.h` files. A `.m` file, is where methods are implemented, and the `.h` file is for public declarations of your class like an API.

**2. Copy the `.bundle`, `.h` and `.m` files into your project and the next alert will appear.**

!["Copy files into your proyect"](/img/2017/12/Step2-Copy-into-your-project.png)

Check your project Target, and press _Finish_.

**3.  Xcode offers to configure a Bridging header, select option _Create bridging header_.**

!["Configure header alert"](/img/2017/12/Step3-Configure-Objective-C-header.png)


**4. Now, you can see your Bridging header file in the Navigator**

!["BrdgingHeader file in navigator"](/img/2017/12/Step4-BrdgingHeader-created.png)

**5. Click on your Bridging header to open, add all your headers files (.h) that you would like to expose to Swift. In my case, I'm going to import the `ProgressHUD.h` file.**

!["Import header"](/img/2017/12/Step5-Import-Target.png)

**6. Build your project (cmd+B). Now you can use your Objective-C library in your Swift app.**

!["Use library"](/img/2017/12/Step6-Use-Obj-C-Library.png)


# If the option to create Bridging Header automatically has been denied, there’s still an option  to create this file manually.

**1. Create a new Header File**

!["Create File"](/img/2017/12/StepManually1-Create-file.png)

!["Select Header file"](/img/2017/12/StepManually1.2-Select-Header-File.png)

**2. Click on your new Bridging header file to open, remove the default text and add all your headers files (.h) that you would like to expose to Swift.**

!["Import Targets"](/img/2017/12/StepManually2-Import-Targets.png)

**3. Now, you need to set the path to the new Bridging Header file in your project Build Settings.**

To set the path to your Bridging Header file you need to navigate to your project **Build Settings** where look for **Swift Compiler – General** section.

!["Build Settings"](/img/2017/12/StepManually3-Build-Settings.png)

**4. Double click on _Objective-C Bridging Header_ option to open the Editor.**

!["Open Editor"](/img/2017/12/StepManually4-Path-Objective-Header.png)

Set the path to your Bridging Header file.

!["Set Header Path"](/img/2017/12/StepManually4.2-Set-Path.png)

**5. Build your project (cmd+B). Now you can use the Objective-C classes in your Swift project.**

!["Set Header Path"](/img/2017/12/StepManually5-Using-Library.png)

If you want to directly play with the code, I have added the example code on ***[Github repository](https://github.com/hernandezmarquina/BridgingHeader)***.

## References

[Developer Apple](https://developer.apple.com/library/content/documentation/Swift/Conceptual/BuildingCocoaApps/MixandMatch.html)