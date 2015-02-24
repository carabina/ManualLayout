[![Support via Gratipay](https://cdn.rawgit.com/gratipay/gratipay-badge/2.3.0/dist/gratipay.png)](https://gratipay.com/bsencan91/)
[![Gitter](https://badges.gitter.im/JOIN CHAT.svg)](https://gitter.im/isair/ManualLayout?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

**This library is under construction. Requires iOS 8 or later and Xcode 6.1+**

#Table of Contents

1. [Installation](#installation)
2. [Usage](#usage)
3. [API Cheat Sheet](#api-cheat-sheet)

#Installation

###[Carthage](https://github.com/Carthage/Carthage#installing-carthage)

Add the following line to your [Cartfile](https://github.com/Carthage/Carthage/blob/master/Documentation/Artifacts.md#cartfile).
```
github "isair/ManualLayout"
```

Then do `carthage update`. After that, add the framework to your project.

###[Cocoapods](https://github.com/CocoaPods/CocoaPods)

Not yet available.

#Usage

Coming soon.

#API Cheat Sheet

Properties provide a simple layout API while methods provide a more powerful one.

###CALayer/UIView Properties

```swift
// For fast positioning.
var origin: CGSize
var x: CGFloat 
var y: CGFloat
var centerX: CGFloat
var centerY: CGFloat
var top: CGFloat
var right: CGFloat
var bottom: CGFloat
var left: CGFloat

// For fast sizing.
var size: CGSize
var width: CGFloat
var height: CGFloat

// Alternate edges. Their names may change in the near future.
var top2: CGFloat
var right2: CGFloat
var bottom2: CGFloat
var left2: CGFloat
```

The difference between alternate edges and normal edges require a bit of explaining. Imagine we have a view at position (0, 0) of size (100, 100) named *myView*. If we do `myView.right = 200`, then its position is now (200, 0) and its size remains unchaged. However, back when our view was located at (0, 0), if we had done `myView.right2 = 200`, then *myView* would have still been at (0, 0) but would have had a size of (200, 0).

So basically, *setting a normal edge's position drags the whole view along with that edge but setting an alternative edge's position drags just that edge*. And don't worry if you, for example, try to drag a left edge past that view's right edge. Edge swapping is done automatically so you don't have to worry about.

###CALayer/UIView Methods

Replace the word "layer" with "view" for the UIView methods.

```swift
func centerInSuperlayer()
func centerDimensionInSuperlayer(dimension: ManualLayoutDimension) // .X or .Y
```

More coming soon.

###ManualLayout Methods

```swift
static func getOriginForCenteringRect(rect: CGRect, inRect container: CGRect) -> CGPoint
static func getPositionForCenteringRect(rect: CGRect, dimension: ManualLayoutDimension, inRect container: CGRect) -> CGFloat
```

More coming soon.
