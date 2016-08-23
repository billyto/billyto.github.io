---
layout: post
title: "[Updated] Subclassing XCTestCase Trick"
date: 2015-04-01 22:34:34.000000000 -04:00
---
###Update:###


As **XCode 6.3** this no longer an issue, now is possible to name *XCTestCase* subclasses with any prefix without losing the ability to run tests from the test method signature. Let's try:

![Example](http://f.cl.ly/items/1D1C172w3E3k3O2M3V0A/Image%202015-04-22%20at%208.55.55%20PM.png)

PS. As we initially mentioned, subclassing XCTestCase is not an elegant solution (I would prefer [Class Categories](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/CustomizingExistingClasses/CustomizingExistingClasses.html) ), but if this is your last resort, be my guest. 

* * *

As the old saying goes, "Prefer composition over inheritance", but in some cases subclassing is the way to go, like when you can extract some common code for all your tests cases classes in an overridden setup method. 


But If you subclass XCTestCase with your own implementation, subsequent classes will lose  the ability to run the test directly from the testing method. 

**How to fix it?**

~~Make your subclasses name to start with **'XC'** prefix.~~

~~i.e.~~ 
<pre><code class="language-objectivec">
@interface XCRBTTestCase : XCTestCase{...}
</code></pre>

~~This will tell XCode to enable running from method again.~~
