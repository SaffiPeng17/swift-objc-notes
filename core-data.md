# Core Data

#### ✢ query

```swift
//from Entity: Employee
let entity = NSEntityDescription.entity(forEntityName: "Employee", in: self.moc)
//sort by: entryDate
let sortDescriptor = NSSortDescriptor(key: "entryDate", ascending: true)
//when predicate: 2017/3 < entryDate < 2017/6
let predicate = NSPredicate(format: "entryDate > %lf AND entryDate < %lf", start, end)
//create request
let request = NSFetchRequest<NSFetchRequestResult>()
request.entity = entity
request.predicate = predicate
request.sortDescriptors = [sortDescriptor]
do {
    let results = try moc.executeFetchRequest(request) as! [Employee]
    for result in results {
        print("Employee ID: \(results.id)")
    }
} catch {
    fatalError("Failed to fetch data: \(error)")
}
```

#### ✢ Concepts

* Core data will not get real data when recevie request.<br>
  * In order to improve performance, Core data would not return real data when recevie request.  Than return real data when program needs those data to do some operations, for example: show data in screen.
  * If needed to return real data all the time. Add code:
  ```swift
request.returnsObjectsAsFaults = true
```
    * **true**: real data all the time
    * **false**: real data when needed 

<br>

#### ✢ References

* [Core Data](https://itisjoe.gitbooks.io/swiftgo/content/database/coredata.html)
* [【 IOS Swift 】CoreData 儲存、查詢、修改、刪除](http://zfejdje.blogspot.tw/2016/01/ios-coredata-save.html)
* [Core Data 使用教學(一)](http://www.iotec.tw/?p=170)
* [[Xcode][Swift3] 使用 CoreData 儲存資料](https://disp.cc/b/11-9ZSr)
