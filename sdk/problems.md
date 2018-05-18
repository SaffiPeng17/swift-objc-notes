# Problems

#### ❄ Apple Mach-O Linker \(ld\) Error

![link id error](/assets/link_id_error.png)

* What did I do?

  * There was a framework, I had ever add in the project. Someday I'd like to remove framework and added source code of framework in project. After I added those source code and built project, this error appeared.

* How to solve this error?

  * In project editor &gt; **Target** &gt; **Build Phases** tab &gt; **Link Binary with Libraries** &gt; Select X.framework &gt; press **-** to delete

* Why?

  * This error is cause there are duplicate code in project. The source code of framework that I add in project are the same as X.framework. But I'd like to use source code of framework not X.framework. So remove X.framework can solve this problem.

* **Note: There are more than one possibility to cause this problem, so the solution may not satisfy every case.**

#### ❄ libMobileGestalt MobileGestaltSupport.m:153: pid 11309 \(Project\) does not have sandbox access for frZQaeyWLUvLjeuEK43hmg and IS NOT appropriately entitled

![sandbox error](/assets/error_sandbox.png)

* [MobileGestaltSupport](https://intellij-support.jetbrains.com/hc/en-us/community/posts/115000191784-MobileGestaltSupport)
* [libMobileGestalt MobileGestaltSupport.m:153 MobileGestalt.c:550 Xcode Console](http://howtodevelop.eu/question/xcode-ios-libmobilegestalt-mobilegestaltsupport-m-153-mobilegestalt-c-550-xcode-console,193120)
* Cannot find the right solution for now and there many people have this problem. Seem like a issue in XCode, wait for Apple to solve it. \(**TRACING: 2017-8-18**\)

#### ❄ dyld: Library not loaded: @rpath/\(.framework\)/\(framework\) Referenced from: ~/Bundle/Application/D9E2EBAB-21F4-4E41-BD2E-43D4C1CC71AF/\(.app\)/\(project\) Reason: image not found

![lib not load](/assets/lib_notload.png)

* [dyld: Library not loaded: @rpath/Alamofire.framework/Alamofire on my iPhone\(iOS8\) while debuging \#101](https://github.com/Alamofire/Alamofire/issues/101)
* Check all libraries are included correctly.

#### ❄ \[App\] if we're in the real pre-commit handler we can't actually add any new fences due to CA restrictiond

![rotate screen error](/assets/error.png)

* What did I do?

  * I build & run the project in my iPhone. When I rotate iPhone, this error message is appeared in console.

* How to solve this error?

  1.Xcode Toolbar &gt; **Product** &gt; **Scheme** &gt; **Edit Scheme**

  ![go to edit scheme](/assets/setup_1.png)

  2.Add an _Envirornment Variables_: **OS\_ACTIVITY\_MODE = disable**

  ![add argument](/assets/setup_2.png)

* [iOS 10: “\[App\] if we're in the real pre-commit handler we can't actually add any new fences due to CA restriction”](https://stackoverflow.com/questions/38458170/ios-10-app-if-were-in-the-real-pre-commit-handler-we-cant-actually-add-any/39493900#39493900?newreg=9cbcaefe398d4f83b0df1d011e9e9041)

#### ❄ Main Thread Checker: UI API called on a background thread: -\[UIView setHidden:\] PID: 4635, TID: 2399059, Thread name: \(none\), Queue name: NSOperationQueue 0x1c423aa20 \(QOS: UNSPECIFIED\), QoS: 0

![](/assets/thread_error.png)

* What did I do?

  * I'd like to show error message that API feedback on View. And I prepare a callback function to show error message on View when API feedback error. But when I run the App, this error is appeared in console and error message did not show on View.

* How to solve this error?

  * Move show error message function to the Main Thread to execute.

  ```swift
  DispatchQueue.main.async {
      //show error message on View
  }
  ```

* [Swift 4 - UIApplication.registerForRemoteNotifications() must be called from main thread only](https://stackoverflow.com/questions/44391367/swift-4-uiapplication-registerforremotenotifications-must-be-called-from-mai/44392584#44392584)

#### ❄ which is not the architecture being linked (armv7s)

The Scheme of framework have to be setting all to "Release".

* [Error: “File was built for archive which is not the architecture being linked (armv7s)”](https://stackoverflow.com/questions/14828693/error-file-was-built-for-archive-which-is-not-the-architecture-being-linked-a)

#### ❄ Invalid bitcode signature

* [Invalid bitcode signature，你们有有没有遇到这个问题？](http://www.cocoachina.com/bbs/read.php?tid-1717806-page-1.html)
* [理解Bitcode：一种中间代码](http://www.cocoachina.com/ios/20150818/13078.html)
* [关于invalid bitcode signature（ linker command failed with exit code 1）](http://www.jianshu.com/p/6b69f30243a1)

* [Xcode beta error: “iPhone has denied the launch request”](https://stackoverflow.com/questions/45421179/xcode-beta-error-iphone-has-denied-the-launch-request)
* [Could not launch，has denied the launch request.](https://blog.csdn.net/lee727n/article/details/78921845)

* [How to resolve “Missing Info.plist key … NSPhotoLibraryUsageDescription”](https://stackoverflow.com/questions/41611987/how-to-resolve-missing-info-plist-key-nsphotolibraryusagedescription)

* [Invalid Swift Support / The SwiftSupport folder is empty](https://stackoverflow.com/questions/32559204/invalid-swift-support-the-swiftsupport-folder-is-empty#comment55664690_32685513)
