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
    
* Reused Table Cell

    1. Define the UI style of the cells. (Class MyCell)
    2. Define every cell as MyCell.
    3. Get data & fill data into every cell.

    **重複使用Cell會節省memory，理由是：比如資料總共有10筆，畫面一次顯示5筆，則被cache住的memory就只會有5筆，就算是經過scroll出現新的cell，也只不過是更新顯示的cell內容，仍然只佔用5個cell的memory。**

#### ✢ References
* [iOS学习之Table View的简单使用](http://blog.csdn.net/totogo2010/article/details/7642908)
* [iOS Programming Tutorial: Create a Simple Table View App](https://www.appcoda.com/ios-programming-tutorial-create-a-simple-table-view-app/)
* [Swift之UITableView的使用](http://www.wugaojun.com/blog/2015/05/09/ru-he-da-jian-bo-ke/)
* [UITableViewCell的重覆使用機制](http://eddychang.me/blog/swift/64-uitableviewcell-reuse.html)




