---
title: "Set the OneDrive retention for deleted users"
ms.reviewer: 
ms.author: kaarins
author: kaarins
manager: pamgreen
audience: Admin
f1.keywords:
- CSH
ms.topic: article
ms.custom:
- 'O365E_ODACStorage'
- 'seo-marvel-apr2020'
ms.service: one-drive
localization_priority: Normal
ms.collection: 
- Strat_OD_admin
- M365-collaboration
search.appverid:
- ODB160
- ODB150
- MET150
ms.assetid: fa1641ea-9f03-4f34-a826-dbd8697e76fe
description: "Learn how to specify how long the files of deleted users are preserved using the OneDrive admin center. "
---

# Set the OneDrive retention for deleted users

If a user's Microsoft 365 account is deleted, their OneDrive files are preserved for a period of time. You can set this time period.
  
 **To set the retention time for OneDrive accounts**
  
1. Sign in to the [OneDrive admin center](https://admin.onedrive.com) as a global or SharePoint admin, and select **Storage** in the left pane.

    ![The Storage page of the OneDrive admin center](media/15942b88-2f71-4c85-87ec-eb14b88f8f93.png)
  
2. Enter the number of days you want to keep the OneDrive files in the **Days to retain files in OneDrive after a user account is marked for deletion** box.

    The setting is activated for the next user that is deleted as well as any users that are in the process of being deleted. The count begins as soon as the user account was deleted in the Microsoft 365 admin center, even though the deletion process takes time. The minimum value is 30 days and the maximum value is 3650 days (10 years).

3. Click **Save**.

## Related articles

[Delete a user from your organization](/office365/admin/add-users/delete-a-user)
  
[Set up OneDrive to alert managers and delegate access automatically when users leave your organization](retention-and-deletion.md)
  
[Overview of retention policies](/office365/securitycompliance/retention-policies)
