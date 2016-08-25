---
layout: page
title: UltraLightRect
subtitle: Light-weight classes for building UIViews programmatically in Objective-C and Swift
---

This is the main documentation page for `UltraLightRect`.

UltraLightRect provides classes and heper functions to easily build UIView frames programmatically. UIView frames (CGRects) are built as percentages of screen width, which allows basic code to be adaptive depending on screen size (i.e. iPhone vs iPad).

To get started simply clone the ULRect project to your local file system and copy the helper classes into your XCode project. There are helper classes for both Objective-C and Swift. Note that the Objective-C classes can be used in a Swift project and vice versa, although the most straight-forward way is to use the Obj-C class in an Obj-C project. The same goes for the Swift helper class.

Usage:

First import the necessary header file into the class in which you would like to use the helper:
`#import ULRectHelper.h`

Create an instance of the helper class:
`ULRectHelper *helper = [[ULRectHelper alloc] init];`

To create a basic CGRect to use for a UIView frame (or UIView subclass):
`CGRect exampleFrame = [helper quickFrameWithXPoint:20.0 YPoint:15.0 Width:60.0 Height:10.0]];`

Create a UIView and use the previously designed frame:
`UIView *testView = [[UIView alloc] initWithFrame:exampleFrame];`

The `testView` will now have a width of 60% of the screen width and 10% of the screen height. The UIView will be positioned 20% left of the left screen edge and 15% from the top edge of the screen.

