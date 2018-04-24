# Upload App - TestFlight


#### ✢ Notes

* **上傳 App**

    * 要先在 Apple Developer 網站上建立一個 App 發布憑證
    * App 的 schema 記得把 archive 設定成 release 模式
    * App icon 是一定要有的，並且要按照正確的 size 放置好
    * archive 之後，先用 Validate 來檢查 App 是否可以正確上傳，有錯誤的部分都要解決
    * Validate 成功後，要 Upload to App Store 才可以在 iTunes Connect 裡看到

        ![upload archive](/assets/upload_archive.png)

    * App 上傳成功後，要至 iTunes Connect 確認，並打開 TestFlight

        ![upload testing](/assets/upload_testing.png)

* **TestFlight**

    * 要先把測試人員的 **Apple ID** 加入測試人員清單，才可以進行測試
    * 若是有使用第三方SDK，如: FB SDK，就會跳出 **Missing Compliance** 警告
        * **SOLVE**: [Encryption Export Compliance for iOS apps](https://kitefaster.com/2017/08/10/encryption-export-compliance-ios-apps/)

        ![missing compliance](/assets/missing_compliance.png)
             
    * 測試人員要收到 App 的 TestFlight 邀請才能使用 TestFlight 來安裝 App

        ![enter invite code](/assets/enter_invitecode.jpg)    ![install app](/assets/Install_App.jpg)


#### ✢ References
* [Apple App Store : TestFlight Beta Testing - 讓 App 飛！](http://logme.logdown.com/posts/1156225/apple-app-store-testflight-beta-testing-individual)



