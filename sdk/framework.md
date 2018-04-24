# Framework

#### ✢ Notes

* Use Swift framework in Objective-C app.

  * Framework (Swift)
      1. Create a __Cocoa Touch Framework__ project.<br><br>![create framework](/assets/create_fmwk.png)<br>
      2. Add a __Swift File__ into project.<br><br>![create swift](/assets/create_swift.png)<br>
      3. Add **Class**, **Functions**, ... into Swift file
      
          ```swift
          public class MyClass: NSObject {
          
              var label: UILabel?
              public func aaaa() { //can be called din App
                  ....
              }
              func bbbb() { //cannot be called in App
                  ....
              }
          }
          ```
          
          * **public**
              * Mark the Classes or functions that can be used in App.
              * In other words, the Classes or functions that are not add **public** cannot be used in App.
          * **NSObject**
              * All the classes in Objective-C have to inherit **NSObject**.
              * If you want the Swift classes can be used in Objective-C, the Swift classes have to inherit **NSObject**.<br><br>
              
      4. Build Framework
          * for __Device__
              1. Select build target: __Generic iOS Device__<br><br>![target dv](/assets/select_device.png)<br><br>
              2. Framework file in Finder: __~/Debug-iphoneos/__<br><br>![finder sim](/assets/simulator_finder.png)<br><br>
          * for __Simulator__
              1. Select build target: any Simulator, e.g. __iPhone 5__<br><br>![target sim](/assets/select_simulator.png)<br><br>
              2. Framework file in Finder: __~/Debug-iphonesimulator/__<br><br>![finder dv](/assets/device_finder.png)<br><br>
  
  * When you use Swift to create framework, it will create a header file __{project_name}-Swift.h__ automatically. The contents of __{project_name}-Swift.h__ are Classes, functions, ... that can be used in App and they are defined by Objective-C language.
  
  * App (Objective-C)
  
      1. Create a __Single View Application__ project and using __Objective-C__ language to develop.<br><br>![create app](/assets/create_app.png)<br><br>
      2. Copy framework to App folder and add into project. Must decide your App want to run in Device or Simulator, and copy different framework into project.<br><br>![add framework](/assets/add_fw.png)<br>
      3. General > Embedded Binaries > + > add framework<br><br>![](/assets/addin_fw.png)<br>
      4. Use framework
      
          ```objective-c
          #import "ViewController.h"
          #import "t_sdk2/t_sdk2.h"
          #import "t_sdk2/t_sdk2-Swift.h"
          
          @interface ViewController ()
          
          @end
          
          @implementation ViewController
          
          - (void)viewDidLoad {
              [super viewDidLoad];
              // Do any additional setup after loading the view, typically from a nib.
              MyClass *class = [MyClass new];
              [class aaaa];
          }
          
          - (void)didReceiveMemoryWarning {
              [super didReceiveMemoryWarning];
              // Dispose of any resources that can be recreated.
              
          }
          
          @end
          ```
          
          * Import framework: __{framework_name}/{project_name}-Swift.h__
          * After import framework, you can use all classes, functions, ... that provide by framework.
              
          
#### ✢ References

* [Swift and Objective-C in the Same Project](https://developer.apple.com/library/content/documentation/Swift/Conceptual/BuildingCocoaApps/MixandMatch.html)
* [\[iOS\] 建立與使用Framework](https://dotblogs.com.tw/clark/2015/11/13/153918)
* [Build your own Cocoa Touch Frameworks, in pure Swift](https://medium.com/@PyBaig/build-your-own-cocoa-touch-frameworks-in-swift-d4ea3d1f9ca3)
* [如何制作支持多平台的Swift Framework \(上\)](http://www.jianshu.com/p/3830ef9687d1)
* [Swift - Framework的制作与使用教程1（纯Swift实现）](http://www.hangge.com/blog/cache/detail_1425.html)
* [Swift - Framework的制作与使用教程2（引用第三方库）](http://www.hangge.com/blog/cache/detail_1426.html)
* [Swift - Framework的制作与使用教程3（与Objective-C混合编程）](http://www.hangge.com/blog/cache/detail_1427.html)
* [Swift: Calling Swift functions from Objective-C](http://ericasadun.com/2014/08/21/swift-calling-swift-functions-from-objective-c/)
* [Installing the iOS libraries in a Swift app](https://www.ibm.com/support/knowledgecenter/en/SSFRDS_6.3.0/com.ibm.mqa.uau.doc/topics/t_Installing_IOS_Swift.html)
* [iOS Framework ＆ CocoaPods 心得上架分享](http://tech.tripviewpost.com/ios%E9%96%8B%E7%99%BC/ios-framework-%EF%BC%86-cocoapods-%E5%BF%83%E5%BE%97%E4%B8%8A%E6%9E%B6%E5%88%86%E4%BA%AB)



