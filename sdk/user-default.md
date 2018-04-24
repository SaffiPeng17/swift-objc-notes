# UserDefaults

#### ✢ Notes

* Set

    ```swift
    func setUserData(key: String, value: Any) {
        UserDefaults.standard.set(value, forKey: key)
        UserDefaults.standard.synchronize()
    }
    ```
    
* Get

    ```swift
    func getUserData(key: String) -> String? {
        let value = UserDefaults.standard.object(forKey: key) as? String
        return value
    }
    ```
    
* Remove

    ```swift
    func removeUserData(key: String) {
        UserDefaults.standard.removeObject(forKey: key)
        UserDefaults.standard.synchronize()
    }
    ```

#### ✢ References

* [儲存資訊 NSUserDefaults](https://itisjoe.gitbooks.io/swiftgo/content/uikit/nsuserdefaults.html)
* [\[iOS\] 使用 NSUserDefaults](https://cg2010studio.com/2013/12/04/ios-使用-nsuserdefaults/)



