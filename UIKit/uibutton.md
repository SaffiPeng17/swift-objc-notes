# UIButton

#### ✢ Notes

* Put a image before title of button & control the image size.

    ```swift
    //add image
    setImage(UIImage(named: "checkbox_n.png"), for: .normal)
    //fine tune edge of image
    imageEdgeInsets = UIEdgeInsetsMake(2.0, 0.0, 2.0, 0.0)
    //scaling image to fit size
    imageView?.contentMode = .scaleAspectFit
    ```

#### ✢ References

* [How to adjust an UIButton's imageSize?](https://stackoverflow.com/questions/10576593/how-to-adjust-an-uibuttons-imagesize)
* [\[iOS\]调整UIButton的title和image详解](http://www.jianshu.com/p/fb20bce230d9)
* [How to create radio buttons and checkbox in swift (iOS)?](https://stackoverflow.com/questions/29117759/how-to-create-radio-buttons-and-checkbox-in-swift-ios)

