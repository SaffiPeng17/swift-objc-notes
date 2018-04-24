# Create App

#### ✢ Notes
* **UDID**: Unique Device Identifier
    * Every phone has an unique id.
    * You can install development version App into iPhone by providing UDID to developer.
* **Develop App & Make it execute in iPhone/iPad**
    1. Create a project.
    2. Connect iPhone/iPad & Mac Pro/Air by transmission line.
    3. Check iPhone/iPad connect state on Xcode.<br>
       * Maybe there are some errors, follow the instrustion to solve them.
       * The errors are like,
           * Xcode version is not match iPhone/iPad.<br>
           * App support version is not match iPhone/iPad.
           * ....
    4. Add some objects into View/Storyboard.
    5. Set view/simulator as the iPhone/iPad that connects.
    6. Run ►.
    7. If the app is not run on iPhone/iPad normally, follow the instruction that pop up.
       * iPad Mini 4 for example: the app should be permissions.
           * Setting > General > Device Management > Select App Developer Account > Trust
    8. Run ► again.
    
#### ✢ References
* [Beginning iOS Programming with Swift](https://www.appcoda.com/learnswift/index.html)
* [Configuring Your Xcode Project for Distribution](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppDistributionGuide/ConfiguringYourApp/ConfiguringYourApp.html)

