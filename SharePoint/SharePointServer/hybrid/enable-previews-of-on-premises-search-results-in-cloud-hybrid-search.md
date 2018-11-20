---
title: "Enable previews of on-premises search results in cloud hybrid search"
ms.author: tlarsen
author: tklarsen
manager: arnek
ms.date: 3/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: sharepoint-server-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_SharePoint_Hybrid_Top
- IT_Sharepoint_Server
- IT_Sharepoint_Server_Top
- Strat_SP_gtc
ms.custom: 
ms.assetid: ccd99adc-b00a-4a0b-8609-a51ebe19c982
description: "Learn how to enable display of previews of on-premises search results in a Search Center in Office 365 for cloud hybrid search."
---

# Enable previews of on-premises search results in cloud hybrid search

[!INCLUDE[appliesto-2013-2016-2019-SPO-md](../includes/appliesto-2013-2016-2019-SPO-md.md)]

Learn how to enable display of previews of on-premises search results in a Search Center in Office 365 for cloud hybrid search.
  
In [cloud hybrid search](https://support.office.com/article/af830951-8ddf-48b2-8340-179c1cc4d291), when users search in Office 365, they get search results from both on-premises and Office 365 content. When a user hovers over a search result that comes from Office 365, information about the content as well as a preview of the content is displayed. Information about the content from search results that come from SharePoint Server is displayed automatically, but display of previews is not automatic. You can enable such display of previews for content from SharePoint Server 2013 and SharePoint Server 2016, but not for content from SharePoint Server 2010. Users can click search results that come from SharePoint Server 2010, SharePoint Server 2013, and SharePoint Server 2016 to access the content.
  
To enable previews for on-premises content in SharePoint Server you need to set up an on-premises Office Online Server and configure SharePoint Server to use it.
  
## What is Office Online Server?

Office Online Server is an Office server product that lets users access their documents online using a web browser. For SharePoint Server content farms, it's the stand-alone Office Online Server that delivers the browser-based versions of Word, PowerPoint, Excel, and OneNote.
  
![The illustration shows information flowing from a search result in the search center in Office 365, via an Office Web Apps Server, to SharePoint Server 2013 content, back via the Office Web Apps Server, to a preview of the content in the search center.](../media/2377b7af-2800-437c-8431-b903e8e30482.png)
  
1. In an Office 365 Search Center, a user hovers over a search result for a Word document that's stored on a SharePoint Server on-premises content farm.
    
2. The request to show a preview of the document goes to the Office Online Server. You have to ensure that the Office Online Server is accessible from where the user is. For example, if you want to support users that are outside the corporate network, you can make the Office Online Server accessible through a reverse proxy.
    
3. The Office Online Server gets the document from the content farm and renders the document in the user's web browser.
    
## Turn on previews for on-premises content in SharePoint Server

Follow these procedures:
  
1. [Deploy the Office Web Apps Server farm](http://technet.microsoft.com/library/08532dbd-3cd9-4508-a0a4-2d343667d239.aspx#BKMK_Deploy_Web_Apps_Server)
    
2. [Configure SharePoint Server 2013 to use the Office Web Apps Server](http://technet.microsoft.com/library/08532dbd-3cd9-4508-a0a4-2d343667d239.aspx#BKMK_Config_SP_Use_Web_Apps)
    
3. Optional: Make the Office Online Server accessible outside the corporate network.
    
### Deploy the Office Online Server farm
<a name="BKMK_Deploy_Web_Apps_Server"> </a>

Office Online Server needs to be on a separate server than SharePoint Server. Here are the steps for deploying the Office Online Server farm:
  
1. [Plan how to use the Office Web Apps Server](https://technet.microsoft.com/en-us/library/jj219435%28v=office.15%29.aspx).
    
2. [Deploy Office Web Apps Server](https://technet.microsoft.com/en-us/library/jj219455.aspx), here's an overview of the steps:
    
  - Prepare each server in the Office Online Server farm to run Office Online Server. This includes installing prerequisite software of Office Online Server, installing Office Online Server and related updates, and installing language packs for Office Online Server.
    
  - Deploy the Office Online Server farm. If you're deploying for test purposes, deploy a single server Office Online Server farm that uses HTTP. If you're deploying for production, deploy a single server Office Online Server farm that uses HTTPS.
    
### Configure SharePoint Server to use the Office Online Server
<a name="BKMK_Config_SP_Use_Web_Apps"> </a>

1. [Plan how you want to use Office Web Apps with SharePoint 2013.](https://technet.microsoft.com/en-us/library/ff431682.aspx)
    
2. [Configure SharePoint 2013 to use Office Web Apps Server](https://technet.microsoft.com/en-us/library/ff431687.aspx). Here's an overview of the steps:
    
  - Create a binding between SharePoint Server and the Office Online Server so traffic from the Office Online Server can enter SharePoint Server.
    
  - Office Online Server uses zones to determine which URL (internal or external) and which protocol (HTTP or HTTPS) to use when it communicates with SharePoint Server. By default, SharePoint Server uses the internal-https zone. If you've deployed Office Online Server for test purposes, set SharePoint Server to use the internal-http zone and set SharePoint Server to allow authentication over HTTP. If you've deployed Office Online Server for production, set SharePoint Server to use the internal-https zone.
    
  - Verify that Office Online Server is working.
    
## See also

#### Other Resources

[Learn about cloud hybrid search for SharePoint](https://support.office.com/article/af830951-8ddf-48b2-8340-179c1cc4d291)
  
[Plan cloud hybrid search for SharePoint](https://support.office.com/article/33926857-302c-424f-ba78-03286cf5ac30)
  
[Configure cloud hybrid search for SharePoint](https://technet.microsoft.com/library/0bba350d-ec33-43db-a873-930559c78dee%28v=office.16%29.aspx)

