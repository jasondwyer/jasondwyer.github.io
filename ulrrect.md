---
layout: page
title: ULRRect
subtitle: Light-weight classes for building UIViews programmatically in Objective-C and Swift
---

This is the main documentation page for `UltraLightRect`. You can get the source code here:[ULRRect Github Project](https://github.com/jasondwyer/ulrrect)

Why does `ULRRect` exist?


Building `UIView` frames programmatically is challenging. The options are to hard-code fixed sizes, which does not scale depending on device size. Alternatives include setting the size as a ratio of the width or height of the screen: `self.view.frame.size.width / 2` or `self.view.frame.size.width * 0.2`. The latter method is problematic for a couple reasons. First, it is verbose, which makes it harder to write. And second, it is hard to read and get a *picture* in your head of how the view will look on screen. `UltraLightRect` abstracts away the verbose code required for setting `UIView` frames programmatically and allows you to pass percentages (i.e. 28%) to build the view frame. The sizes scale depending on the size of the iPhone or iPad. 

`UltraLightRect` provides classes and he;per functions to easily build `UIView` frames programmatically. `UIView` frames (`CGRect`) are built as percentages of screen width, which allows basic code to be adaptive depending on screen size (i.e. iPhone vs iPad).

To get started simply clone the `ULRRect` project to your local file system and copy the helper classes into your XCode project. There are helper classes for both Objective-C and Swift. Note that the Objective-C classes can be used in a Swift project and vice versa, although the most straight-forward way is to use the Obj-C class in an Obj-C project. The same goes for the Swift helper class.

***Usage:***

First import the necessary header file into the class in which you would like to use the helper:

**Objective-C**

`#import ULRRectHelper.h`

**Swift**

`//Importing is not necessary.`


***


Create an instance of the helper class:


**Objective-C**


`ULRRectHelper *helper = [[ULRRectHelper alloc] init];`


**Swift**


`let helper = ULRRectSwiftHelper()`


***

To create a basic `CGRect` to use for a `UIView` frame (or `UIView` subclass):


**Objective-C**


`CGRect exampleFrame = [helper quickFrameWithXPoint:20.0 YPoint:15.0 Width:60.0 Height:10.0];`


**Swift**

`let exampleFrame = helper.quickFrameWithXPoint(20.0, YPoint: 15.0, Width: 60.0, Height: 10.0)`


***

Create a `UIView` and use the previously designed frame:


**Objective-C**


`UIView *testView = [[UIView alloc] initWithFrame:exampleFrame];`


**Swift**

`let testView = UIView.init(frame: exampleFrame)`

The `testView` will now have a width of 60% of the screen width and 10% of the screen height. The `UIView` will be positioned 20% left of the left screen edge and 15% from the top edge of the screen.


***

Create a square frame:

**Objective-C**

`CGRect squareFrame = [helper squareFrameWithXPoint:20.0 YPoint:10.0 sideLengthAsPercentOfWidth:50.0];`


All `squareFrame` sides will be 50% of the device width.

***

Determine the user's device:


**Objective-C**

`BOOL phone = [helper isPhone];`


**Swift**

`let phone = helper.isPhone()`

`phone` will return `true` if the user's device is an iPhone, and `false` if the device is an iPad


***

Create a `UILabel` with an adaptive font:


**Objective-C**


```objective-c
CGRect labelFrame = [helper quickFrameWithXPoint:20.0 YPoint:15.0 Width:60.0 Height:10.0];
UILabel *exampleLabel = [[UILabel alloc] initWithFrame:labelFrame];
exampleLabel.font = [UIFont systemFontOfSize:[helper adaptiveFontSized:32]];
```

**Swift**

```swift
let labelFrame = helper.quickFrameWithXPoint(20.0, YPoint: 15.0, Width: 60.0, Height: 10.0)
let exampleLabel = UILabel.init(frame: labelFrame)
exampleLabel.font = UIFont.systemFontOfSize(self.adaptiveFontSized(32))
```

Creates a `UILabel` with either the entered size or scale up 1.8x if the device is an iPad 

