# Upload App - Error Fix


#### 1. ERROR ITMS-90166
##### _“Missing Code Signing Entitlements. No entitlements found in bundle ‘com.x.x’ for executable ‘Payload/xxx.app/PlugIns/xxx_yyy.bundle/xxx’.”_

![bundle error](/assets/upload_bundleError.png)

##### # SOLVE
1. 將 .bundle 內的 Info.plist 打開. (Xcode)
2. 刪除 **Executable file**.

  ![bundle plist](/assets/upload_bundleplist.png)

3. rebuild .bundle & Archive .app.

##### # Reference
* [Missing Code Signing Entitlements for resource bundle xcode 6.3](https://stackoverflow.com/questions/29684966/missing-code-signing-entitlements-for-resource-bundle-xcode-6-3)


#### 2. Error ITMS-90717
##### _"Invalid App Store Icon. The App Store Icon in the asset catalog in 'xxx.app' can't be transparent nor contain an alpha channel."_

![icon error](/assets/upload_iconError.png)

##### # SOLVE
* [Error ITMS-90717: “Invalid App Store Icon”](https://stackoverflow.com/questions/46585809/error-itms-90717-invalid-app-store-icon)


#### 3. ERROR ITMS-90171
##### _"Invalid Bundle Structure - The binary file 'xxx.app/xxx.bundle' is not permitted. Your app can’t contain standalone executables or libraries, other than the CFBundleExecutable of supported bundles. Refer to the Bundle Programming Guide at https://developer.apple.com/go/?id=bundle-structure for information on the iOS app bundle structure."_

![bundle invalid](/assets/upload_bundleInvalid.png)

##### # 說明
這個錯誤較常出現在專案內有加入靜態library的情況，錯誤主因是：靜態library會被視為「不能執行、純粹的資料」，當有需要靜態library內的資料時，才會去讀取的被動角色。所以當靜態library內包含任何可執行的檔案，就會出現這個錯誤。

備註：.bundle也是一個靜態library。

##### # SOLVE
1. 開啟 .bundle 所在資料夾.
2. 對著 .bundle 按滑鼠右鍵 > Show Package Contents.

  ![bundle invalid solve1](/assets/upload_bundleinvalid_sol1.png)

3. 找尋有沒有 execute file，有就刪除.

  ![bundle invalid solve2](/assets/upload_bundleinvalid_sol2.png)

##### # REFERENCE
* [ERROR ITMS-90171: "Invalid Bundle Structure - The binary file 'XYZ.app/abc.bundle/Contents/MacOS/Abcbundle' is not permitted](https://stackoverflow.com/questions/43521188/error-itms-90171-invalid-bundle-structure-the-binary-file-xyz-app-abc-bundl)
* [上传ipa包.Bundle文件问题](http://wangt.me/blog/2016/08/01/shang-chuan-ipazhong-dot-bundlewen-jian-wen-ti/)


