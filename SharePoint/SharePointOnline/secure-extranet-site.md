---
title: "Securing a SharePoint Online extranet site"
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 6/25/2018
ms.audience: End User
ms.topic: article
ms.service: sharepoint-online
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Strat_OD_share
search.appverid:
- SPO160
- MET150
ms.assetid: c5384693-53ab-4f6f-99a2-59e74185d87f
description: "Learn how to configure SharePoint Online Admin Managed Partner Users (Guests) scenario."
---

# Securing a SharePoint Online extranet site

Depending on your business needs, there are different approaches you can take to secure and restrict access to your SharePoint Online B2B extranet site. In SharePoint Online, you can control how and if invitations are sent to external users. These settings can be set at the tenant level, globally controlling all sites. Some settings can also be set at the individual site collection level, allowing you tailor the settings based on the unique requirements for your partner relationship while keeping control on sites intended for internal corporate use only.
  
For information about how to configure the sharing settings discussed in this article, see [Manage external sharing for your SharePoint Online environment](external-sharing-overview.md).
  
> [!IMPORTANT]
> Any tenant-level sharing settings that you configure also affect OneDrive for Business. 
  
## Restricting sharing in SharePoint site collections

The following table shows a series of options for sharing SharePoint site collections. Option 1 is the most restrictive, with external sharing turned off entirely, and option 6 is the least restrictive, with users able to access content by using anonymous links.
  
Options 2 thru 5 are the primary options for use in configuring a B2B extranet site. Option 2 restricts sharing to only those external users who are already in your Office 365 directory, while options 3 and 4 use domain filtering to allow or deny sharing with specified email domains. Option 5 requires external users to authenticate, but doesn't otherwise restrict external sharing.
  
With any of these options, you can also choose to require that sharing invitations be sent only by the site owner.
  
||**1**|**2**|**3**|**4**|**5**|**6**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Sharing setting** <br/> |Don't allow sharing outside your organization  <br/> |Allow sharing only with the external users that already exist in your organization's directory  <br/> |Allow users to invite and share with authenticated external users  <br/> |Allow users to invite and share with authenticated external users  <br/> |Allow users to invite and share with authenticated external users  <br/> |Allow sharing to authenticated external users and using anonymous access links  <br/> |
|**Domain filtering (allow/deny list)** <br/> |N/A  <br/> |N/A  <br/> |Allow list  <br/> |Deny list  <br/> |None  <br/> |None  <br/> |
|**Notes** <br/> |No external sharing - used for intranet sites.  <br/> |Sharing only allowed with existing users in the directory  <br/> |Sharing only allowed with users who are from the specified Microsoft-hosted domains.  <br/> |Sharing allowed with users who are from all but the specified domains.  <br/> |Sharing allowed with users who are from all Microsoft-hosted domains.  <br/> |No restrictions on sharing.  <br/> |
||Most restricted  <br/> |||||Least restricted  <br/> |
   
The following sections look more closely at these options.
  
### Restrict sharing only to existing guests in the directory

In option 2, the sharing setting **Allow sharing only with the external users that already exist in your organization's directory** allows sharing only with existing users in your Office 365 directory. This turns off the user-based invitations approach within SharePoint Online. 
  
If you're partnering with another organization that uses Office 365 or has an Azure AD, you can import users from their tenant into your tenant, and then grant them access to your extranet site. For more information, see [What is Azure AD B2B collaboration?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b).
  
### Sharing with authenticated users

Options 3, 4, and 5 all use the **Allow external users who accept sharing invitations and sign in as authenticated users** sharing option for the site collection. With this option, the site can be shared with any account that can authenticate through a Microsoft-hosted domain (such as Outlook.com or any Office 365 or Azure AD tenant). 
  
Options 4 and 5 use domain filtering:
  
- **Allow list** - Allows sharing invitations to be sent only to those domains listed. This is the best way to narrow down the scope of who can be invited to a site. 
    
- **Deny list** - Allows sharing invitations to be sent to any domain except those listed. 
    
To set up domain filtering, see [Restricted Domains Sharing in Office 365 SharePoint Online and OneDrive for Business](restricted-domains-sharing.md).
  
## Controlling who can add users to a site

An important feature to consider in your access security is controlling who can share a site with new users. To tightly control a high business impact site collection, you can allow only the site owner the ability to invite new users.
  
Owner-only sharing can be used with any of the sharing options in the table above to help control access to your extranet site.
  
To configure this option, on the **Sharing** tab at the site collection level, select **Turn off sharing for non-owners in all sites in the site collection**
  
> [!CAUTION]
> This is a one-way switch. You cannot reenable sharing permissions for non-site owners. 
  
## See also

[Onboarding to SharePoint Hybrid Extranet Sites](plan-b2b-extranet-sites.md)
  
[Extranet for Partners with Office 365](create-b2b-extranet.md)
  
[Restricted Domains Sharing in O365 SharePoint Online and OneDrive for Business](restricted-domains-sharing.md)
  
[Set-SPOSite](https://go.microsoft.com/fwlink/p/?LinkId=624162)
  
[Set-SPOTenant](https://go.microsoft.com/fwlink/?linkid=2003900)

