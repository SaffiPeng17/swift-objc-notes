# TableView

#### ✢ Extend class UITableViewDelegate, UITableViewDataSource in UIViewController
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

#### ✢ References
* [iOS学习之Table View的简单使用](http://blog.csdn.net/totogo2010/article/details/7642908)
* [iOS Programming Tutorial: Create a Simple Table View App](https://www.appcoda.com/ios-programming-tutorial-create-a-simple-table-view-app/)
* [Swift之UITableView的使用](http://www.wugaojun.com/blog/2015/05/09/ru-he-da-jian-bo-ke/)
* [UITableViewCell的重覆使用機制](http://eddychang.me/blog/swift/64-uitableviewcell-reuse.html)




