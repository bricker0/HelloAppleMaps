# Hello Apple Maps and Location

This example was written by Dr. Ricker, for students in the <a href="http://www.tacoma.uw.edu/urban-studies/ms-program-overview">Masters of Geospatial Technologies at the University of Washington Tacoma</a>. To complete this example you will need a Mac with XCode installed. This tutorial is written for traditional GIS analyst interested in building location based services using Swift and XCode for iOS.

For this assignment, Lab 4 for the course titled Mobile GIS offered during the Winter of 2017, we build a native iOS application. To achieve this aim, we will be learning how to navigate XCode, basics of Swift, and we will quickly create a generic location based service! This example walks you through how to create an app that puts a point on the map based on the user's current location. This example assumes you have never used XCode, you know little to know programming and **you are ready to rock**!

If you are interested in reading more about swift here is <a href="https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/index.html#//apple_ref/doc/uid/TP40014097-CH3-ID0">information about Swift straight from Apple.</a> In this tutorial, I will be teaching you to use <a href="https://developer.apple.com/reference/mapkit">MapKit Framework</a> and the<a href="https://developer.apple.com/reference/corelocation"> CoreLocation Framework</a>. MapKit displays a map an annotation for the end user while CoreLocation taps into the sensors in the iOS device to find the users location. Used together, you can offer information to the end user based on their current location. 

Other recommended reading include: Bucanek, J., (2014). _Chapter 17 Where Are You?_ Learn iOS 8 App Development, Apress. Second Edition.
Online tutorials also helpful for this assignment include <a href ="https://www.raywenderlich.com/90971/introduction-mapkit-swift-tutorial">this one by Audrey Tam.</a>

### Student deliverables  

There are a number of questions posed in this example - for full credit - please answer these questions and upload a doc to canvas. You will also need to zip and upload the code you generate as you follow this example to a private repo. More on this in class. If you are not in the program - you are welcome to follow along but I will not review your work! 

## Get Started

Assuming XCode is installed, 

1. Open XCode 
2. Click "Create a new Xcode project"
3. Select "Single View Application" and click "Next"
4. In the Product Name field "YOURLASTNAME_Lab4_2017" and leave the rest of the fields as default. 
-This means that the Language you will be programming in is Swift, and your target device is the iPhone. 
-If you pick universal - it will work on iPad or iPhone but this is more work. You can do that later if you would like. 
-Let's keep it simple for now. 

5. Now click Next 
- Navigate to the local repository you plan to save your work and click "Create" 
- Note: If you are using MacBooks that belong to the department, do not forget to **backup your work on an external drive** or upload directly to GitHub regularily as to not loose your work!!

- The Xcode interface will now be open.

[![screenshot](https://github.com/bricker0/HelloAppleMaps/blob/master/xcode1.png)](#features)

## Question 1. What are the default device orientations that are selected? What does this do or enable? 

When I am building an app for the first time, I want instant gratification. For this reason, let's go straight to the interface builder. With interface builder (IB) is called the "Storyboard" (I will use storyboard and IB interchangably) you can start designing the user interface (UI) the end user will interact with. To navigate to the IB...

8. Click Main.storyboard file in Project navigator on the left 

This will load the IB with the View Controller. In the view controller, we will place objects like maps for the end user to interact with. In the Object library on the right, select "Label" and then drag and drop a label into your view controller storyboard interface. Then change the label by clicking on it. Please give it a title with something descriptive like "First Map"

[![screenshot2](https://github.com/bricker0/HelloAppleMaps/blob/master/xcode2.png)](#features)

9. Change the style of the label
Click "Show Attributes Inspector" in the top right and you can change the style and color of your text. Click the ruler icon to "Show Size Inspector" which is part of the responsive design. We will not go into much detail about this here, but if you "lock" an object to the sides of the interface, it will remain relative to the sides of the interface you tell it to snap to, if not when the screen is oriented certain directions an object might not be visible.

###Test your app###
Now click play and test your app on the emulator. Then use the emulator to see if your first app works! In the simulator click "Hardware-->rotate left" how does your label respond? 

##Question 2. Provide a screenshot of your app working in the emulator and rotated. 

10. Now, since we care about maps and location, **let's add a map!**
In the objects library on the bottom right, in the "filter" box, type "map" and then the only object in the library will be "Map Kit View". Drag that into your View Controller in storyboard. Then resize the box to make it as big as possible and fit in the view. We love maps, we want them to be big!

After you add ojects to the View controller, you will need connect an IBOutlet to tell the View Controller what to do with the object in the ViewController.swift file. 

"An object of the UIViewController class (and its subclasses) comes with a set of methods that manage its view hierarchy. iOS automatically calls these methods at appropriate times when a view controller transitions between states. When you create a view controller subclass (like the ViewController class you’ve been working with), it inherits the methods defined in UIViewController and lets you add your own custom behavior for each method." <a href="https://developer.apple.com/library/content/referencelibrary/GettingStarted/DevelopiOSAppsSwift/WorkWithViewControllers.html">Quote From this Apple Tutorial</a>about view controllers.

There are a number of ways to do this. 
I recommend using view called "Show Assistant Editor" and then you can see your storyboard and your viewcontroller.swift file at the same time. XCode has some drag and drop functionality that makes programming pretty awesome and easy. Here is what the Assistant Editor view will look like. 
[![screenshot3](https://github.com/bricker0/HelloAppleMaps/blob/master/xcode3.png)](#features)

11. In the ViewController.swift document add the following:
Under import UIKit add

```markdown
import MapKit

```
Now delete the following 

```markdown
 override internal func viewDidLoad()

    override internal func didReceiveMemoryWarning()
  
  ```
This will introduce an error since we haven't added the UIMapKit framework to our project yet!
  
To do this, using the project navigator, the pane on the far left (think of the table of contents in ArcGIS) we need to navigate to the project file, then select "Capabilities" and toggle on maps. Notice all of the things toggled in blue to get to this screen. Once you toggle Maps on, this will link the MapKit.framework to your project, meaning it will call Apple Maps!

[![screenshot4](https://github.com/bricker0/HelloAppleMaps/blob/master/xcode4.png)](#features)

12. Click Save. Now, your bug should be gone! 

When you navigate to the folder called "Frameworks" in Project Navigator, you should see a little suitcase with MapKit.framework
This isn't enough though, we still need to make our outlet. To do this...

13. In the IB select the map box and hold down control and drag your curser to where you want to connect your IBOulet. In the popup window enter the name of the object, which I named map.
Leave the rest as default. You will see the storage is "Weak" meaning that when you close the app, the map will stop.
14. Click connect and then your code should autogenerate. 

[![screenshot5](https://github.com/bricker0/HelloAppleMaps/blob/master/xcode5.png)](#features)

If you did this succesfully your code should now look like this under the import MapKit


  ```markdown
class ViewController: UIViewController {
    @IBOutlet weak var map: MKMapView!

    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
    }

   ```
   You should now be ready to run your first map app! If you see any red warnings, click on them to see what might be wrong. 
   If you see no warnings, click Run and see what happens! 
   
   Not written by Britta Below this point
```markdown

Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/UWTMGIS/GIS504_W17/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
