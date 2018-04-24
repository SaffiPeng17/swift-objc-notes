# Common

### 1. Several target in one project.

* How to add a new Static Library target in current project?

![add target](/assets/add_target.png)

### 2. Global variable in project - Swift.

* Class Definition.

    ```swift
    class MyNumber: NSNumber {
        ...
        
        class func getNumber() {
            ...
        }
    }
    ```

* Used in project.

    ```swift
    struct Global {
        static var myNumber = MyNumber()
    }
    
    class ViewController: UIViewController {
        
        override func viewDidLoad() {
            super.viewDidLoad()
            // Do any additional setup after loading the view, typically from a nib.
            Global.myNumber.getNumber()
        }
        
        override func didReceiveMemoryWarning() {
            super.didReceiveMemoryWarning()
            // Dispose of any resources that can be recreated.
        }
    }
    ```

### 3. Open "http" not "https"

[How can I add NSAppTransportSecurity to my info.plist file?](https://stackoverflow.com/questions/31216758/how-can-i-add-nsapptransportsecurity-to-my-info-plist-file)


