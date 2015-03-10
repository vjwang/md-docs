<!--

    Copyright (c) 2007-2013, Kaazing Corporation. All rights reserved.

--> <!--#include virtual="/_header.html"-->

-   [Home](../../index.html)
-   [Documentation](../index.html)
-   Display Logs for the Objective-C Client

<article>
<section>
<!-- CONTENT GOES HERE -->
Display Logs for the Objective-C Client
=======================================

${gateway.ce.client.note}
In this procedure, you will learn how to gather data on your ${gateway.name.long} Objective-C client.

Before You Begin
----------------

This procedure is part of Checklist: [Build Objective-C (iOS) WebSocket Clients](o_dev_objc.html):

1.  [Use the Objective-C WebSocket Client API](p_dev_objc_client.html)
2.  [Secure Your Objective-C Client](p_dev_objc_secure.html)
3.  **Display Logs for the Objective-C Client**
4.  [Troubleshoot Your Objective-C Client](p_dev_objc_tshoot.html)

<!-- <p><span class="note"><b>Note:</b> Learn about supported browsers, operating systems, and platform versions in the ${certification.matrices.inline}.</span></p> -->
<span id="logging"></span></a>To Display Logs for the Objective-C Client
------------------------------------------------------------------------

1.  Build your Objective-C client, as described in [Checklist: Build Objective-C (iOS) WebSocket Clients](o_dev_objc.html).
2.  Add the following line into one of the existing functions, such as `viewDidLoad()`:

    <span class="uri">KGTracerDebug = YES;</span>

    For example:

    ``` auto-links:
    - (void)viewDidLoad {
      [super viewDidLoad];
      KGTracerDebug = YES;
    }
    ```

3.  Build your Xcode project, run the Objective-C client in the Xcode Simulator, and perform some actions for the Objective-C client to log.

    The output is displayed in the Xcode Target Output area.

</p>
Notes
-----

<!-- Use "Note" and a paragraph tag when there's only one note -->
-   If you run the Objective-C client on an iOS device, the logging output is also displayed in **Console** for the device in Xcode Organizer. In Xcode, click **Window**, click **Organizer**, locate the iOS device in **DEVICES**, and click **Console**.
-   See [KGTracer](../apidoc/client/ios/gateway/Classes/KGTracer.html) for more information.

Next Step
---------

[Troubleshoot Your Objective-C Client](p_dev_objc_tshoot.html)

</section>
</article>

<!-- #main -->

<!-- #main-container --> <!--#include virtual="/_footer.html"-->
