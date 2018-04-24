# Convert to Swift 4

#### ✢ Notes

* **@objc setting**

  * After convert project to Swift 4 automatically in Xcode, there's a warning:

    ![@objc error](/assets/swift4_@objc_error.png)

    **\#SOLVE : **[The use of Swift 3 @objc inference in Swift 4 mode is deprecated?](https://stackoverflow.com/questions/44379348/the-use-of-swift-3-objc-inference-in-swift-4-mode-is-deprecated)

  * Use **\#selector\(*\)** in Swift.

    **Swift 3**
    ```swift
    override func viewDidLoad() {
        super.viewDidLoad()
        ...
        closeButton.addTarget(self, action: #selector(closeButtonTouchUped), for: .touchUpInside)
    }
    
    //Take closeButtonTouchUped as OBJC function automatically.
    func closeButtonTouchUped() {
        ...
    }
    ```
    
    **Swift 4**
        
    ```swift
    override func viewDidLoad() {
        super.viewDidLoad()
        ...
        closeButton.addTarget(self, action: #selector(closeButtonTouchUped), for: .touchUpInside)
    }
    
    //Have to add "@objc" to mark closeButtonTouchUped is an Objective-C function.
    @objc func closeButtonTouchUped() {
        ...
    }
    ```

* **String.substring\(with: X\)**

  * [How can I use String slicing subscripts in Swift 4?](https://stackoverflow.com/questions/45562662/how-can-i-use-string-slicing-subscripts-in-swift-4)

#### ✢ References

* [Swift 4 新功能詳盡介紹：Codable, Dictionaries優化, 多行字符串等等](https://www.appcoda.com.tw/swift4-changes/)



