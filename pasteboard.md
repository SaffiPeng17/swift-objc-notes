# Pasteboard

#### ✢ NSPasteboard: write & read

* Write

```swift
let pb = NSPasteboard.general()
pasteboard.clearContents()
result = pb.writeObjects(array)
```
*# array: [NSString], [NSImage], ...*

*Example*

```swift
let paths = [path1, path2, ...]
var images: = [NSImage]()
for path in paths {
    let image = NSImage(contentsOfFile: path)
    images.append(image)
}
let pb = NSPasteboard.general()
pasteboard.clearContents()
result = pb.writeObjects(images)
```

* Read

```swift
let pb = NSPasteboard.general()
let objects = pb.readObjects(forClasses: array1, options: nil) as! array2
let obj = objects[2]
```
*# array1: [NSString.type], [NSImage.type], ...*
*# array2: [NSString], [NSImage], ...*

*Example*

```swift
let pb = NSPasteboard.general()
let images = pb.readObjects(forClasses: [NSImage.self], options: nil) as! [NSImage]
let image = images[1]
```
<br>

#### ✢ References

* [Writing a string to NSPasteBoard](https://stackoverflow.com/questions/598587/writing-a-string-to-nspasteboard)
* [Swift and NSPasteboard](http://swiftrien.blogspot.tw/2015/03/swift-and-nspasteboard.html)
* [NSPasteboard and simple custom data](https://codexample.org/questions/290055/nspasteboard-and-simple-custom-data.c)
* [iOS8剪贴板Pasteboard](https://www.swiftmi.com/topic/180.html)
