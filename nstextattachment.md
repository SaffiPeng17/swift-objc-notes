# TextView

#### ✢ NSTextView with Rich Strings

* Paste (Ctrl+V): paste item is image  
*After get keyDown event Ctrl+V, the unicode character **\u{fffc}** will be added into textStorage of TextView as mark.*

* The contents of NSTextView are all stored in textStorage.  
*When content is **string**, stored in textStorage as **string**.*  
*When content is **image**, stored in textStorage as **attachment**.*

* If there are attachments(images) in textStorage, call `attributeRuns` func to get them all.

#### ✢ textStorage: write & read image

* Write

```swift
let textView = NSTextView()
let image = NSImage(contentsOfFile: path) 
let att = NSTextAttachment()
att.attachmentCell = NSTextAttachmentCell(imageCell: image)
let attString = NSAttributedString(attachment: att)
textView.textStorage.append(attString)
```

* Read

```swift
let attRuns = textStorage.attributeRuns
for attRun in attRuns {
    var effRange = NSRange()
    let attrs = attRun.attributes(at: 0, effectiveRange: &effRange)
    let att = attrs[NSAttachmentAttributeName] as NSTextAttachment
    let attCell = att.attachmentCell as NSCell
    let image = attCell.image
}
```
<br>

#### ✢ References

* [How to pull NSImage from NSTextAttachment in NSTextView?](http://www.anhuiyouxi.com/how-to-pull-nsimage-from-nstextattachment-in-nstextview/)
* [How to add image and text in UITextView in IOS?](https://stackoverflow.com/questions/24010035/how-to-add-image-and-text-in-uitextview-in-ios)
* [iOS 7 TextKit - How to insert images inline with text?](https://stackoverflow.com/questions/20930462/ios-7-textkit-how-to-insert-images-inline-with-text)
* [iOS NSAttributedString的21种属性详细介绍(图文混排)](http://blog.csdn.net/Sponge_CMZ/article/details/49794691)
* [iOS 富文本属性NSMutableAttributedString使用详解](http://www.jianshu.com/p/8c7dd7d8501b)
