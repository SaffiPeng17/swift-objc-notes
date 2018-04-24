# Develop Note: Objective-C

#### ✢ Notes

* After add a new Button into nib/storyboard, there are some general define ways:
  * define **variable**: **Referencing Outlets** connect to the **ViewController.h**.

    ```objective-c
    @interface ViewController : UIViewController  
      @property (weak, nonatomic) IBOutlet UIButton *firstButton;  
    @end
    ```

  * define **action** operation: **ctrl + Button** connect to the **ViewController.m**.

    ```objective-c

    @implementation ViewController
      - (IBAction)firstBtnTapped:(id)sender {
          ....
      }
    @end
    ```

* NSInteger -&gt; Int

  ```objective-c
  NSInteger number = 20;
  int number2 = (int)number;
  
  NSIndexPath *indexPath;
  int row = (int)indexPath.row;
  ```
  
* Get selected row on TableView
  * Implement UITableView func: **didSelectRowAtIndexPath**

    ```objective-c
    - (void)tableView:(UITableView *)tableView didSelectRowAtIndexPath:(NSIndexPath *)indexPath {
      selectedRow = (int)indexPath.row;
    }
    ```
    
#### ✢ Extend class `UITableViewDelegate`, `UITableViewDataSource` in `UIViewController`
* Swift

    ```swift
    class myViewController: UIViewcontroller {
        ....
    }
    
    extension myViewController: UITableViewDelegate, UITableViewDataSource {
        //Set table rows
        func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
            ....
        }
        //Draw table cells
        func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
            ....
        }
        ....
    }
    ```

* Objective-C

    ```objective-c
    @interface ViewController : UIViewController<UITableViewDelegate, UITableViewDataSource>
        ....
    @end
    
    @implementation ViewController
        //Set table rows
        - (NSInteger)tableView:(UITableView *)tableView numberOfRowsInSection:(NSInteger)section {
            ....
        }
        //Draw table cells
        - (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath {
            ....
        }        
        ....
    @end
    ```
    
<br>
#### ✢ References

* [How to write the ok button action in Objective-c?](https://stackoverflow.com/questions/30211495/how-to-write-the-ok-button-action-in-objective-c)
* [\[iOS 8\] 從Objective-C到Swift : UIAlertController取代UIAlertView, UIActionSheet \(含Objective-C 語法\)](http://www.takobear.tw/2014/10/14/ios-8objective-cswift-uialertcontrolleruialertview-uiactionsheet-objective-c)
* [在iOS 8中使用UIAlertController](http://www.cocoachina.com/ios/20141126/10320.html)
* [How to convert An NSInteger to an int?](https://stackoverflow.com/questions/1752701/how-to-convert-an-nsinteger-to-an-int)
* [iOS, How to find selected row Of UITableView?](https://stackoverflow.com/questions/18637332/ios-how-to-find-selected-row-of-uitableview)
* [How to delete objects from NSArray through tableview in Objective C?](https://stackoverflow.com/questions/12122041/how-to-delete-objects-from-nsarray-through-tableview-in-objective-c)
* [How to open new view from UITableViewRow button click event?](https://stackoverflow.com/questions/40062931/how-to-open-new-view-from-uitableviewrow-button-click-event)
* [How To Handle Row Selection in UITableView](https://www.appcoda.com/how-to-handle-row-selection-in-uitableview/)
* [Open new View Controller by clicking Cell in Table View - Swift iOS](https://stackoverflow.com/questions/30773529/open-new-view-controller-by-clicking-cell-in-table-view-swift-ios)
* [iOS学习之Table View的简单使用](http://blog.csdn.net/totogo2010/article/details/7642908)
* [iOS Programming Tutorial: Create a Simple Table View App](https://www.appcoda.com/ios-programming-tutorial-create-a-simple-table-view-app/)
* [Swift之UITableView的使用](http://www.wugaojun.com/blog/2015/05/09/ru-he-da-jian-bo-ke/)



