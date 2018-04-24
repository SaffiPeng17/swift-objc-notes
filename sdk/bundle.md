# Bundle

#### ✢ Notes

##### 1. Add .bundle into SDK.

* After create a framework project, you may need icons, languages, ... using in the framework. Here are the steps for add bundle in framework.

    1. Create a Bundle target in project.<br><br>![add bundle](/assets/add_bundle.png)<br>([How to add target?](/sdk/common.md))<br><br>
    2. Set the __Base SDK__ from __macosx__ to __iphoneos__.<br><br>![](/assets/set_basesdk.png)<br><br>
    
* Error solved.

    * When I build MyBundle.bundle target, there is an error:

    ![Linker Fail](/assets/linker_fail.png)
    
    * Solve:
    
        1. open __MyBundle__ target setting.
        2. set __Enable Bitcode__ to __NO__.
    
        ![set no](/assets/set_no.png)
        
##### 2. Read images from .bundle.

* Init .bundle.

    ```swift
    //instruct bundle with file path
    myBundle = Bundle(path: Bundle.main.path(forResource: "MyBundle", ofType: "bundle"))
    //instruct .strings file in bundle
    myStrings = "MyStrings" //instruct .strings file name
    ```

* Read images from .bundle.

    ```swift
    let filePath = myBundle.path(forResource: image, ofType: "jpg")!
    let image = UIImage(contentsOfFile: filePath)
    ```
    
* Read string from .strings.

    ```swift
    let string = NSLocalizedString(strid, tableName: "MyStrings", bundle: myBundle, value: "", comment: "")
    ```

#### ✢ References

* [How to Create Resource Bundle in iOS with Images, XIBs, Audios, Videos, etc. ?](http://jaym2503.blogspot.tw/2014/03/how-to-create-resource-bundle-in-ios.html)
* [Swift 3 : How to get path of file saved in Documents folder](https://stackoverflow.com/questions/40598942/swift-3-how-to-get-path-of-file-saved-in-documents-folder)
