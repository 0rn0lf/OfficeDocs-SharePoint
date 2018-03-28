---
title: "Missing server side dependencies (SharePoint Server)"
ms.author: stevhord
author: bentoncity
manager: pamgreen
ms.date: 8/31/2017
ms.audience: ITPro
ms.topic: troubleshooting
ms.prod: sharepoint-server-itpro
localization_priority: Normal
ms.collection:
- IT_Sharepoint_Server
- IT_Sharepoint_Server_Top
ms.assetid: b67550f6-fc12-4734-950f-6e2f50ef0ca2
description: "Summary: Learn how to resolve the SharePoint Health Analyzer ruleMissing server side dependenciesin SharePoint Server 2016 and SharePoint 2013."
---

# Missing server side dependencies (SharePoint Server)

 **Summary:** Learn how to resolve the SharePoint Health Analyzer rule "Missing server side dependencies" in SharePoint Server 2016 and SharePoint 2013. 
  
 **Rule Name:** Missing server side dependencies. 
  
## 

 **Summary:** When you first deploy SharePoint Server 2016 this rule can generate false errors. To resolve this, update to the [August 2016 PU release](https://www.microsoft.com/en-us/download/details.aspx?id=53399).
  
Typically when you see this rule, it states that some Search service web parts are missing. If this is the case then you can ignore this message.
  
 **Cause:** This rule typically occurs when you have deployed the Search service in a SharePoint Server farm. 
  
 **Resolution: Reference the following Microsoft documentation**
  
1. For more information, see [SharePoint 2013 Health Analyzer: Missing Server Side Dependencies](https://social.technet.microsoft.com/wiki/contents/articles/24495.sharepoint-2013-health-analyzer-missing-server-side-dependencies.aspx).
    
2. For more information on cleanup of missing server side dependencies, see [Video: Cleanup of databases after upgrade procedure](https://technet.microsoft.com/en-us/library/mt809168%28v=office.16%29.aspx).﻿
    
3. For additional information, see ["Missing Server Side Dependencies" error message in health analyzer in the Microsoft SharePoint Server 2013 central administration site](https://go.microsoft.com/fwlink/?LinkID=142689).
    

