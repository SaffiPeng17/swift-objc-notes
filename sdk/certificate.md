# Certificate

#### ✢ Notes

* Developer account: needs to pay
    1. Create a Apple Developer ID.
    2. Pay for distribution & Publish.
        * __Personal__: pay for __1__ developer ID only.
        * __Organization__: pay for __1+__ developer IDs. Add the personal developer ID in organization and all developer ID in organization can use paid functions.


* Add Certificate Steps
    * Develop Authority
        * Create **certificate private key** on Mac.
            * Created by _KeyChain_.
            * Certificate private key is a file: _*.certSigningRequest_.
        * Upload **certificate private key** to Apple developer web site and create **certificate file** on the web site.
            * **Have to login account which has paid.**
            * Apply certificates for Mac by uploading **certificate private key**.
            * Every Mac has a certificate only. So if already apply before, just download.
            * Apply certificates has to wait for approve.
                * If the developer account is personal, it will be approved immediately.
                * If the developer account is a group, like company, it has to wait for manager to approve.
            * Download 2 certificate files:
                * **ios_development.cer**
                * **AppleWWDRCA.cer**           
        * Add **certificate file** into Mac keychain.
            * Click certificate files to install.
            * Check the certificate files are in _KeyChain_.
    * iOS Device Authority
        * Apply a **certificate file** for iOS device.
            * Get the identifier ID of iOS Device and add in Apple Developer web site.
            * Apply for adding identifier ID of iOS Device.
        * Add **certificate file** in Xcode.

#### ✢ References

* [iOS 各憑證概念說明](https://medium.com/@kuanweilin/ios-%E5%90%84%E6%86%91%E8%AD%89%E6%A6%82%E5%BF%B5%E8%AA%AA%E6%98%8E-2fd3eb83d3f5)
* [ios app 发布流程](http://miclee.cn/2015/08/19/ios-app-publish/)
* [製作xcode憑證，讓開發的APP可以安裝到iOS裝置做測試](http://app-island.com/app/2560/%E8%A3%BD%E4%BD%9Cxcode%E6%86%91%E8%AD%89%EF%BC%8C%E8%AE%93%E9%96%8B%E7%99%BC%E7%9A%84APP%E5%8F%AF%E4%BB%A5%E5%AE%89%E8%A3%9D%E5%88%B0iOS%E8%A3%9D%E7%BD%AE%E5%81%9A%E6%B8%AC%E8%A9%A6)
* [想上架？有些憑證觀念你必須要知道](http://tech.tripviewpost.com/ios%E9%96%8B%E7%99%BC/%E6%83%B3%E4%B8%8A%E6%9E%B6%EF%BC%9F%E4%BD%A0%E5%BF%85%E9%A0%88%E7%9F%A5%E9%81%93%E7%9A%84%E6%86%91%E8%AD%89%E3%80%81%E5%AE%89%E8%A3%9D%E6%8F%8F%E8%BF%B0%E6%AA%94)
* [[iOS] App 上架憑證流程筆記](http://andyyou.logdown.com/posts/216618-ios-app-shelves-certificate-process-notes)
* [iOS開發筆記](http://seanysh.blogspot.tw/2014/03/ioscertificates-provisioning-profiles.html)
* [Apple 續約 更新憑證](http://bahole.blogspot.tw/2016/08/apple.html)
* [iOS App 上架流程, (1/3) 申請 Apple ID for Company](http://gogoprivateryan.blogspot.tw/2015/08/ios-app-13-apple-id-for-company.html)
* [【iOS - App上架流程圖文教學】](https://medium.com/@mikru168/ios-app%E4%B8%8A%E6%9E%B6%E6%B5%81%E7%A8%8B%E5%9C%96%E6%96%87%E6%95%99%E5%AD%B8-724636ddc78b)
* [iOS推播通知憑證申請流程](https://medium.com/@chiaping.collyn/ios%E6%8E%A8%E6%92%AD%E9%80%9A%E7%9F%A5%E6%86%91%E8%AD%89%E7%94%B3%E8%AB%8B%E4%BD%9C%E6%A5%AD-b5a3e51486a1)
* [[iOS] 第一次 Ad Hoc 就上手](https://kirkhsutw.blogspot.tw/2015/05/ios-ad-hoc.html)
* [自動幫我們產生 certificate 的 Xcode](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E5%95%8F%E9%A1%8C%E8%A7%A3%E7%AD%94%E9%9B%86/%E8%87%AA%E5%8B%95%E5%B9%AB%E6%88%91%E5%80%91%E7%94%A2%E7%94%9F-certificate-%E7%9A%84-xcode-85a8dc79ba2b)
