# HelloAppleMaps

# Hello Apple Maps and Location

This example was written by Dr. Ricker, for students in the <a href="http://www.tacoma.uw.edu/urban-studies/ms-program-overview">Masters of Geospatial Technologies at the University of Washington Tacoma</a>. To complete this example you will need a Mac with XCode installed. 

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
6. Navigate to the local repository you plan to save your work and click "Create" 
7. The Xcode interface will now be open.asdf

[![solarized dualmode](https://github.com/altercation/solarized/raw/master/img/solarized-yinyang.png)](#features)
(https://github.com/bricker0/HelloAppleMaps/edit/master/blob/master/xcode1.png)

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
