# Security

#### ✢ Notes

* SHA1 encryption

    ```swift
    func encryptSHA1(string: String) -> String {
        let data = string.data(using: .utf8)!
        var digest = [UInt8](repeating: 0, count: Int(CC_SHA1_DIGEST_LENGTH))
        let crypt = digest.map{ String(format: "%02x", $0) }
        
        data.withUnsafeBytes{ CC_SHA1($0, CC_LONG(data.count), &digest) }
        return crypt.joined(separator: "")
    }
    ```

#### ✢ References

* [\[swift\] String To MD5](http://toyo0103.blogspot.tw/2015/03/swift-string-to-md5.html)
* [swift 3.0 MD5加密](http://www.jianshu.com/p/540427de6b5e)
* [字符串加密 - String md5 in swift3.0](http://www.jianshu.com/p/a832dc2e7000)
* [Swift3 使用ＭＤ5](https://h81061678.blogspot.tw/2017/02/swift3-5.html)
* [Swift 3 making sha1, sha256 and md5 functions](https://stackoverflow.com/questions/39684092/swift-3-making-sha1-sha256-and-md5-functions)
* [哈希\(Hash\)与加密\(Encrypt\)的基本原理、区别及工程应用](http://www.cnblogs.com/leoo2sk/archive/2010/10/01/hash-and-encrypt.html)
* [Swift 3 making sha1, sha256 and md5 functions](https://stackoverflow.com/questions/39684092/swift-3-making-sha1-sha256-and-md5-functions)
* [How to crypt string to sha1 with Swift?](https://stackoverflow.com/questions/25761344/how-to-crypt-string-to-sha1-with-swift)
* [Using CommonCrypto in Swift](http://iosdeveloperzone.com/2014/10/03/using-commoncrypto-in-swift/)



