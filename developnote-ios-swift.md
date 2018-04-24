# Develop Note: Swift

#### ✢ Notes

* Launch page
    1. Add a Launch Screen storyboard.
    2. Design Launch page on Launch Screen storyboard.
    3. Check up Launch setting of project.
        1. Open **Info.plist**.
        2. Find key: **Launch screen interface file base name**.
        3. Check the Launch screen is the storyboard that created for Launch screen.<br>
            If create Launch Screen storyboard by add file in Xcode, the Launch screen will be set to Launch Screen storyboard you just added automatically. If not, set to the storyboard you want to use.
    4. Run ► again.


* Button border

    ```swift
    button1.layer.cornerRadius = 4
    button2.layer.cornerRadius = 6
    //setup border style
    button1.layer.borderColor = UIColor.white.cgColor
    button1.layer.borderWidth = 2.0
    ```
    
* TableView: `UITableViewDelegate`, `UITableViewDataSource`
    * Set how many rows in table
        ```swift
        func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
            return foods.count //data counts
        }
        ```
    * Draw every cell view
        ```swift
        func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
            let cell = tableView.dequeueReusableCell(withIdentifier: "cell", for: indexPath) as! IngredientTableViewCell
            //Setup cell
            ....
        
            return cell
        }
        ```
    * Set selected style of cell
        ```swift
        func tableView(_ tableView: UITableView, didSelectRowAt indexPath: IndexPath) {
            //setup action when select cell
            //Show .actionSheet or .alert or any else
            ...
            //Show checkmark
            let cell = tableView.cellForRow(at: indexPath)
            ...
            cell?.accessoryType = self.selected ? .checkmark : .none
        }
        ```
    * Edit cell of table
        ```swift
        func tableView(_ tableView: UITableView, commit editingStyle: UITableViewCellEditingStyle, forRowAt indexPath: IndexPath) {
            if editingStyle == .delete {
                //delete item of model
            }
        }
        ```
    * Edit swipe action on cell
        ```swift
        func tableView(_ tableView: UITableView, editActionsForRowAt indexPath: IndexPath) -> [UITableViewRowAction]? {
            //swipe action: share
            let share = UITableViewRowAction(style: .default, title: "Share") {
                ...
            }
            //swipe action: add
            let add = ...
        
            return [share, add, ...]
        }
        ```

<br>
#### ✢ References
* [Human Interface Guidelines iOS](https://developer.apple.com/ios/human-interface-guidelines/overview/design-principles/)
* [Launch Image does not show up in my iOS App](https://stackoverflow.com/questions/26141731/launch-image-does-not-show-up-in-my-ios-app)
* [UITableView example for Swift](https://stackoverflow.com/questions/33234180/uitableview-example-for-swift)



