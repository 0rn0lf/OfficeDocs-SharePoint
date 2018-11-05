---
title: "The unattended Service Account Application ID is not specified or has an invalid value (SharePoint Server)"
ms.author: stevhord
author: bentoncity
manager: pamgreen
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: troubleshooting
ms.prod: sharepoint-server-itpro
localization_priority: Normal
ms.collection:
- IT_Sharepoint_Server
- IT_Sharepoint_Server_Top
ms.assetid: ec3a8cb2-141f-4c4b-a3c3-068ea89121cf
description: "Learn how to resolve the SharePoint Health Analyzer rule: The Unattended Service Account Application ID is not specified or has an invalid value, for SharePoint Server."
---

# The unattended Service Account Application ID is not specified or has an invalid value (SharePoint Server)

[!INCLUDE[appliesto-2013-2016-2019-xxx-md](../includes/appliesto-2013-2016-2019-xxx-md.md)] 
  
 **Rule name:** The Unattended Service Account Application ID is not specified or has an invalid value. 
  
 **Summary:** The Unattended Service Account Application ID setting stores an application identifier (ID) in the registered Secure Store Service. The application ID is used to reference the Unattended Service Account credentials. The Unattended Service Account is a single, low-privileged account that Visio Graphics Service impersonates when it connects to data sources external to SharePoint Server, such as SQL Server. This account is required to connect to these external data sources. For more information about Visio Graphics Service, see [Plan for Visio Services in SharePoint Server](http://technet.microsoft.com/library/4385b870-c3ec-462f-a43d-49f18e4d8675%28Office.14%29.aspx) and [Plan Visio Services security in SharePoint Server](http://technet.microsoft.com/library/6d871772-b90b-4e48-9122-a6d9a1122b8d%28Office.14%29.aspx).
  
 **Resolution: Specify a valid application ID value**
  
1. Verify that the user account that is performing this procedure is an administrator of the Visio Graphics Service service application and the Secure Store Service service application.
    
2. In Central Administration, on the Home page, in the **Application Management** section, click **Manage service applications**.
    
3. On the Service Applications page, click the Secure Store Service service application.
    
4. On the Secure Store Service page, record the application ID from the **Target Application ID** column. 
    
    For more information about the Secure Store Service service application, see [Plan the Secure Store Service in SharePoint Server](http://technet.microsoft.com/library/e1196de0-1eb9-4c50-aeca-93e0eba7be0d%28Office.14%29.aspx).
    
5. On the Service Applications page, click the Visio Graphics service application.
    
6. On the Manage the Visio Graphics Service page, click **Global Settings**.
    
7. On the Visio Graphics Service Settings page, in the **External Data** section, in the **Unattended Service Account** text box, type the application ID that you recorded in step 4 of this procedure. 
    
8. Click **OK**.
    

