---
title: "Performance in the modern SharePoint experience"
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/15/2019
ms.audience: Admin
ms.topic: article
ms.service: sharepoint-online
localization_priority: Priority
search.appverid: MET150
description: "Learn about performance improvements in the SharePoint modern experience."
---

# Performance in the modern SharePoint experience

The modern experience in SharePoint is designed to be compelling, flexible and – importantly -- more performant. Both SharePoint performance as a whole and the performance of individual SharePoint components such as search, lists and document libraries are affected by many factors, all of which contribute to the decisive performance metric: perceived end user latency, or the speed with which pages are rendered in the client browser. The SharePoint modern experience incorporates several performance improvements that help to minimize latency and improve SharePoint page responsiveness:

+ Client-side caching
+ Client-side processing and data requests
+ Use of content delivery networks (CDNs)

More powerful computers and modern advancements in network architectures and web browsers have made it possible to improve the overall SharePoint user experience by shifting much of the data caching and processing from the server to the client machine. In this article, you will learn about how the SharePoint modern experience leverages client-side processing, caching and CDNs.

## Client-side caching

Caching helps to improve the speed at which web pages load in the browser by storing a copy of requested objects on disk so that they can be quickly retrieved for future requests. The traditional SharePoint architecture provides several server-side disk-based caches: the BLOB cache, the page output cache, the object cache, and the anonymous search results cache. When a client requests objects that have already been cached, the SharePoint server can return the objects to the client without having to look them up in the database or retrive them from their native location.

The SharePoint modern experience is designed to minimize the time required to render cached content by allowing blobs and other objects to be cached locally on the user machine, minimizing latency and reducing network traffic between the client and the SharePoint front-end servers.

## Client-side processing and data requests

In the traditional SharePoint architecture, the SharePoint server farm executes data requests and other processing operations, returning results and rendered pages to the client. This model was intended to reduce the load on the the client machine and browser, and also to reduce network traffic between the client and server, factors which were critical performance bottlenecks in legacy environments.

The SharePoint modern experience architecture leverages the computing power of contemporary user computers, high-bandwidth low-latency networks and modern web browser capabilities to allow the client computer to directly perform certain data requests and processor-intensive operations such as page rendering.

Note that the SharePoint modern experience client-side processing model can provide dramatic improvement in perceived end user latency over the traditional SharePoint architecture, but there may be a significant increase in client-to-server network traffic and a greater dependency on the client-side execution environment as compared to the traditional SharePoint architecture.

## Content delivery networks (CDNs)

A Content delivery network, or CDN, is a worldwide network of servers that host the same files. Microsoft hosts an [Office 365 CDN](https://developer.microsoft.com/en-us/office/blogs/general-availability-of-office-365-cdn/) for common libraries (such as JavaScript and CSS files) that you may include in your SharePoint solution.

SharePoint Online latency can be affected by the physical distance between your users and the location of the SharePoint Online instance. This is particularly important for organizations that have a global presence where a site may be hosted on one continent while users on the other side of the world are accessing its content. CDNs help mitigate this situation by hosting certain popular web assets in different locations closer to the end users.

The SharePoint modern experience architecture uses CDNs to optimize network performance by enabling the client browser to access common SharePoint libraries from the fastest possible location relative to the client machine.

# Related topics

[Performance guidance for SharePoint Online portals](https://docs.microsoft.com/en-us/sharepoint/dev/solution-guidance/portal-performance)

[Tune SharePoint Online performance](https://docs.microsoft.com/en-us/office365/enterprise/tune-sharepoint-online-performance)

[Using content delivery networks with SharePoint Online](https://docs.microsoft.com/en-us/office365/enterprise/using-content-delivery-networks-with-sharepoint-online)