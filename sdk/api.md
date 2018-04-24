# API

#### ✢ Notes

* API is two-way in the most of time.
* Use closure is a easy way to control the response from API.

  ```swift
  func requestAPI(api: String, param: [String: Any], success: @escaping (NSDictionary?) -> Void, fail: @escaping (NSDictionary) -> Void) {

      guard let url = URL(string: api) else {
          NSLog("%@ is not exist !", api)
          return
      }

      var request = URLRequest(url: url)
      let data = JSON(param) //Dictionary -> JSON
      var requestData = ""
    
      //prepare request data (follow the API request define)
      requestData = ...
      ...

      //set-up API connection (follow the API request define)
      request.httpBody = requestData.data(using: .utf8, allowLossyConversion: true)
      request.timeoutInterval = 30
      request.httpMethod = "POST"
      request.setValue("application/x-www-form-urlencoded", forHTTPHeaderField: "Content-Type")

      //send request
      let task = URLSession.shared.dataTask(with: request) { (data, response, error) in
          guard error == nil else {
              NSLog("Session error: %@", String(describing: error))
              return
          }

          //parse response
          if let dict = DICT(data!) { //JSON -> Dictionary
              if success {
                  success(data)
              } else {
                  fail(data)
              }
          }
      }
      task.resume()
  }
  ```

#### ✢ References

* [Tutorial: Build an iOS App in Swift that uses a REST API and Stormpath](https://stormpath.com/blog/build-note-taking-app-swift-ios)
* [取得遠端 API 資料並儲存](https://itisjoe.gitbooks.io/swiftgo/content/apps/taipeitravel/fetchdataandstorage.html)
* [URLSession 教學（swift 3, iOS）- part 2](https://medium.com/@jerrywang0420/urlsession-教學-swift-3-ios-part-2-a17b2d4cc056)
* [詳細解說幾個建置網站時常用的編碼方法](https://blog.miniasp.com/post/2008/11/05/Explain-web-related-encoding-decoding-method-in-detail.aspx)
* [How to make GET request in swift 3](https://stackoverflow.com/questions/37555773/how-to-make-get-request-in-swift-3)
* [Swift 3 — APIs , Network Requests, & JSON: Getting the data](https://code.bradymower.com/swift-3-apis-network-requests-json-getting-the-data-4aaae8a5efc0)



