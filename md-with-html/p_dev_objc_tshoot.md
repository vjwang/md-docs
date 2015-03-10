<!--

    Copyright (c) 2007-2013, Kaazing Corporation. All rights reserved.

--> <!--#include virtual="/_header.html"-->

-   [Home](../../index.html)
-   [Documentation](../index.html)
-   Troubleshoot Your Objective-C Client

<article>
<section>
<!-- CONTENT GOES HERE -->
Troubleshoot Your Objective-C Client
====================================

${gateway.ce.client.note}
This topic contains descriptions of common errors that might occur when using the Objective-C Client API and provides steps on how to prevent these errors.

Before You Begin
----------------

This procedure is part of Checklist: [Build Objective-C (iOS) WebSocket Clients](o_dev_objc.html):

1.  [Use the Objective-C WebSocket Client API](p_dev_objc_client.html)
2.  [Secure Your Objective-C Client](p_dev_objc_secure.html)
3.  [Display Logs for the Objective-C Client](p_dev_objc_log.html)
4.  **Troubleshoot Your Objective-C Client**

<!-- <p><span class="note"><b>Note:</b> Learn about supported browsers, operating systems, and platform versions in the ${certification.matrices.inline}.</span></p> -->
<span id="What Problem Are You Having"></span></a>What Problem Are You Having?
------------------------------------------------------------------------------

-   [Lexical or Preprocessor Issue: KGWebSocket not found](#problem1)
-   [Apple Mach-O Linker (Id) Error](#problem2)
-   [Error: Selector Not Recognized or NSInvalidArgumentException](#problem3)

<span id="problem1"></span></a>Lexical or Preprocessor Issue: KGWebSocket not found
-----------------------------------------------------------------------------------

**Cause:** This error occurs because Xcode cannot locate the KGWebSocket.framework file that references a header file.

**Solution:** To resolve this error, correct the **Framework Search Paths** setting by performing the following steps:

1.  Navigate to the location of the ${gateway.name.long} Objective-C framework:

    The Objective-C framework is available on [kaazing.org](http://kaazing.org).</span>

    <!-- <p>Expand kaazing-ios-library.zip if necessary.</p></li>
        <li>Double-click the the <strong>KGWebSocket.dmg</strong> image to mount it.</li> -->

2.  Drag the **KGWebSocket.framework** file from the mounted volume into the **Frameworks** folder in the Xcode project navigator.
3.  In the **Choose options for adding these files** dialog that appears, enable the **Copy items into destination group’s folder** checkbox, select your project in **Add to targets**, and click **Finish**.

    Xcode adds the framework to the project navigator, updates the **Framework Search Paths** setting in **Build Settings** with the path to the framework, and updates the **Link Binary With Libraries** settings in **Build Phases** automatically.

<span id="problem2"></span></a>Apple Mach-O Linker (Id) Error
-------------------------------------------------------------

**Cause:** This error will refer to "undefined symbols" beginning with <span class="uri">\_CFHTTP</span>, for example <span class="uri">\_CFHTTPMessageAddAuthentication</span>. The error occurs because the Xcode project is missing the CFNetwork.framework file. Clients built using the ${gateway.name.long} Objective-C library also require the CFNetwork.framework.

**Solution:** To resolve this error, add CFNetwork.framework by performing the following steps:

1.  Click **Build Phases** at the top of the project editor.
2.  Open the **Link Binary With Libraries** section.
3.  Click the **Add (+)** button to add a library or framework.
4.  Enter <span class="uri">CFNetwork.framework</span> in the search field. **CFNetwork.framework** is displayed automatically.

    If you do not see **CFNetwork.framework**, then you might not have iOS SDK 5.1 or later installed. You can install the SDK as part of the Xcode bundle.

5.  Select **CFNetwork.framework** and click **Add**. CFNetwork.framework is added to the Xcode project and appears in the Xcode project navigator. You can drag CFNetwork.framework into the **Frameworks** folder.

<span id="problem3"></span></a>Error: Selector Not Recognized or NSInvalidArgumentException
-------------------------------------------------------------------------------------------

**Cause:** These errors occur because the Xcode project is linking against an Objective-C static library that contains categories and the <span class="uri">-ObjC</span> value for the **Other Linker Flags** build setting is not configured. Basically, the error occurs when a library extends one of the built-in classes using a category. An example of the Selector Not Recognized error:

[\_\_NSCFConstantString indexOf:]: unrecognized selector sent to instance 0x...

Objective-C does not define linker symbols for each function (or method, in Objective-C). Linker symbols are only generated for each class. If you extend a pre-existing class with categories, the linker does not know to associate the object code of the core class implementation and the category implementation. This prevents objects created in the resulting application from responding to a selector that is defined in the category. The <span class="uri">-ObjC</span> flag causes the linker to load every object file in the library that defines an Objective-C class or category.

For more information, see [Building Objective-C static libraries with categories](http://developer.apple.com/library/mac/#qa/qa1490/_index.html).

**Solution:** To resolve this error, add the <span class="uri">-ObjC</span> value for the **Other Linker Flags** build setting by performing the following steps:

1.  In the project navigator, select the target to which you want to add a library or framework.
2.  Click the **Build Settings** tab and scroll down to the **Linking** section.
3.  In **Other Linker Flags**, add the value <span class="uri">-ObjC</span>.

<span class="note">**Note:** NSInvalidArgumentException is a constant in the Foundation framework (defined by NSException) and is thrown whenever you pass an invalid argument to a method. Consequently, it might be thrown for reasons other than the missing <span class="uri">-ObjC</span> flag.</span>
See Also
--------

-   [Mac Developer Library Technical Q&As](http://developer.apple.com/library/mac/navigation/#section=Resource%20Types&topic=Technical%20Q%26amp%3BAs)
-   [Instruments User Guide](http://developer.apple.com/library/ios/#documentation/DeveloperTools/Conceptual/InstrumentsUserGuide/Introduction/Introduction.html)
-   [How to inspect iOS's HTTP traffic without spending a dime](http://www.tuaw.com/2011/02/21/how-to-inspect-ioss-http-traffic-without-spending-a-dime/)

</section>
</article>

<!-- #main -->

<!-- #main-container --> <!--#include virtual="/_footer.html"-->
