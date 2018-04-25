---
title: "Add and edit user profile properties in SharePoint Online"
ms.author: kaarins
author: kaarins
manager: pamgreen
ms.date: 12/19/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- GSA150
- BSA160
- GSP150
ms.assetid: 85091402-737f-4bb9-99a7-bc5f194502a8
description: "Learn how to add and edit properties on SharePoint User profiles that are configured from information that your organization supplies to the Office 365 directory service."
---

# Add and edit user profile properties in SharePoint Online

If your organization uses the cloud identity model, your Office 365 user accounts are stored in Azure AD and you can manage most user profile info in the Office 365 admin center. For info, see [Edit or change a user in Office 365](https://support.office.com/article/42bb3f17-8f9d-4182-b434-5f1c8024e614). You can also manage user profiles (including adding user pictures and defining user managers) in the Azure AD admin center. For info, see [Add or change profile information for a user in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=864809). If you need to create custom user profile properties, such as languages spoken, emergency contact info, or sales account, you can use user properties in SharePoint Online. Note that these properties are NOT synced back to Azure AD. 
  
## Add a property for a user profile
<a name="__top"> </a>

1. [Sign in to Office 365](e9eb7d51-5430-4929-91ab-6157c5a050b4.md) as a global admin or SharePoint admin. 
    
2. Select the app launcher icon ![The icon that looks like a waffle and represents a button click that will reveal multiple application tiles for selection.](media/3b8a317e-13ba-4bd4-864e-1ccd47af39ee.png) in the upper-left and choose **Admin** to open the Office 365 admin center. (If you don't see the Admin tile, you don't have Office 365 administrator permissions in your organization.) 
    
3. In the left pane, choose **Admin centers** > **SharePoint**.
    
4. Click **user profiles** in the left pane. 
    
5. Under **People**, choose **Manage User Properties**. 
    
    ![Manage User Properties link under Admin user profiles.](media/ab8985da-a2f9-4839-b4a2-f0feeb379f31.png)
  
6. Select **New Property**.
    
7. In the **Name** box, enter a unique name for the property. 
    ![Property settings under User Profile in Admin](media/b18946ee-7db7-4587-9f0b-2ea1d892415f.png)
  
8. In the **Display Name** box, enter the profile property name that will be displayed to all users. (This name doesn't have to be unique.) 
    
9. In the **Type** list, select the data type for the property. 
    
    > [!NOTE]
    >  If you select **string (Multi Value)**, the property will be permanently set as a multi-valued property. You cannot change this setting after you select **OK**. You can only delete the property and add it again as a new single-value property. 
  
10. If you selected binary, HTML, or string, use the **Length** box to enter the maximum number of characters allowed for property values. 
    
11. If you selected string and want to associate the profile property with a [managed metadata term set](introduction-to-managed-metadata.md), select **Configure a Term Set to be used for this property**. Then select a term set from the list. 
    
12. Make sure **Default User Profile Subtype** is selected so the default user profile subtype is associated with this user profile property. 
    
13. In the **Description** box, enter the instructions or information that is displayed to users about this profile property. 
    
14. In the **Policy Settings** section, select the policy setting and default privacy setting that you want for this property. Click the **User can override** box to enable users to override these settings. 
    
15. If you want users to be able to change this profile information for themselves, select **Allow users to edit values for this property**.
    
16. In the **Display Settings** section, specify whether and how the property will be viewed by users. 
    
17. In the **Search Settings** section, select **Alias** if the property is the equivalent of a user's name. For example, you might do this if you create a property for a "Stage name" and want searches for all documents by John Kane to return the same results as searches for the user's real name. Select the **Indexed** if you want searches to return all the user profiles matching that property. For example, if you have a property for "University," a search for that value would return all alumni from that university. 
    
    > [!NOTE]
    >  The **Alias** check box is available only if you set the **Default Privacy Setting** "Everyone." 
  
18. Click **OK**.
    
## Edit or delete a property you added
<a name="__top"> </a>

1. In the SharePoint admin center, click **user profiles** in the left pane. 
    
2. Under **People**, choose **Manage User Properties**. 
    
    ![Manage User Properties link under Admin user profiles.](media/ab8985da-a2f9-4839-b4a2-f0feeb379f31.png)
  
3. In the **Property Name** column, click the profile property that you want to change, and then click **Edit** or **Delete**.
    
4. Edit the elements you want to change. 
    
    > [!NOTE]
    >  Some elements of profile properties, such as the **Type** element, are unavailable because they can't be edited. To define these elements, create a new property. The exception is the Source Data Connection property. It's predefined in SharePoint Online and can't be changed. 
  
5. When you're done, click **OK**.
    

