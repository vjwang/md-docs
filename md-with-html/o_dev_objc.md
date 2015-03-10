<!--

    Copyright (c) 2007-2013, Kaazing Corporation. All rights reserved.

--> <!--#include virtual="/_header.html"-->

-   [Home](../../index.html)
-   [Documentation](../index.html)
-   Checklist: Build Objective-C (iOS) WebSocket Clients

<article>
<section>
<!-- CONTENT GOES HERE -->
Checklist: Build Objective-C (iOS) WebSocket Clients
====================================================

${gateway.ce.client.note}
This checklist provides the steps necessary to create an Objective-C client using the ${gateway.name.long} [Objective-C Client API](../apidoc/client/ios/gateway/index.html):

<table class="checklist">
<tr>
<th scope="col">
\#
</th>
<th scope="col" width="400">
Step
</th>
<th scope="col">
Topic or Reference
</th>
</tr>
<!-- <tr>
  <td>1</td>
    <td>Learn about supported browsers, operating systems, and platform versions.</td>
    <td>${certification.matrices.inline}</td>
  </tr> -->
<tr>
<td>
1
</td>
<td>
Learn how to use the Objective-C Client API.
</td>
<td>
[Use the Objective-C WebSocket Client API](p_dev_objc_client.html)
</td>
</tr>
<tr>
<td>
2
</td>
<td>
Learn how to authenticate your client by implementing a challenge handler to respond to authentication challenges from ${gateway.name.long}.
</td>
<td>
[Secure Your Objective-C Client](p_dev_objc_secure.html)
</td>
</tr>
<tr>
<td>
3
</td>
<td>
Learn how to gather data on ${gateway.name.long}
Objective-C client.
</td>
<td>
[Display Logs for the Objective-C Client](p_dev_objc_log.html)
</td>
</tr>
<tr>
<td>
4
</td>
<td>
Troubleshoot the most common issues that occur when using Objective-C clients.
</td>
<td>
[Troubleshoot Your Objective-C Client](p_dev_objc_tshoot.html)
</td>
</tr>
</table>
Introduction
------------

In this how-to, you will learn how to use the ${gateway.name.long} Objective-C client library to enable your iOS client to communicate with any back-end service over WebSocket via the ${gateway.name.long} or any RFC-6455 WebSocket endpoint.

This document contains information for an Objective-C developer who wants to add Objective-C to an iOS client to enable communication with a back-end server through ${gateway.name.long} or any RFC-6455 WebSocket endpoint.

For more information on the Objective-C API, see [Objective-C Client API](../apidoc/client/ios/gateway/index.html).

<span id="WebSocket and Objective-C"></span></a>WebSocket and Objective-C
-------------------------------------------------------------------------

${gateway.name.long} provides support for the HTML5 Communication protocol libraries in Objective-C. Using the Objective-C Client API, you can enable the HTML5 WebSocket protocols in new or existing Objective-C applications. For example, you can create an Objective-C client to get streaming financial or news data from a back-end server using WebSocket. The following figure shows a high-level overview of the architecture:

<figure>
![](../images/f-html5-objc-client-web.png)
<figcaption>
**Figure: Enable Communication Between Your iOS Client and a Back-end Server over WebSocket**
</figcaption>
</figure>
</section>
</article>

<!-- #main -->

<!-- #main-container --> <!--#include virtual="/_footer.html"-->
