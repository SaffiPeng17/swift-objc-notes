# Animation

#### ✢ Create Animation: func

```swift
NSAnimationContext.runAnimationGroup({ (ani_content) in
    //animation settings
    }, completionHandler: {
        //when animation end
})
```

#### Example

* Moving liner path and then Hide

```swift
NSAnimationContext.runAnimationGroup({ content in
    content.duration = 1.0
    content.timingFunction = CAMediaTimingFunction(name: kCAMediaTimingFunctionLinear) //liner moving
    }, completionHandler: {
        self.animating = false
})
```

* From Hide to Show, and then from Show to Hide

```swift
NSAnimationContext.runAnimationGroup({ content in
    content.duration = 0.5
    content.timingFunction = CAMediaTimingFunction(name: kCAMediaTimingFunctionEaseIn) //fade-in
    self.animator().isHidden = false
    }, completionHandler: {
        NSAnimationContext.runAnimationGroup({ content in
            content.duration = 0.5
            content.timingFunction = CAMediaTimingFunction(name: kCAMediaTimingFunctionEaseOut) //fade-out
            self.animator().isHidden = true
            }, completionHandler: {
               self.animating = false
    })
})
```
<br>


#### ✢ References

* [Cocoa - animating NSWindow](https://stackoverflow.com/questions/36372547/cocoa-animating-nswindow)
* [iOS Core Animation: Advanced Techniques中文译本](https://zsisme.gitbooks.io/ios-/content/ "Core Animation: Advanced Techniques中文译本")
* [Swift: 深入理解Core Animation](http://www.cnblogs.com/ziyi--caolu/p/5038097.html "深入理解Core Animation")
* [UIView Animation in Swift 3](https://medium.com/ios-os-x-development/uiview-animation-in-swift-3-2b499abb58c5)
