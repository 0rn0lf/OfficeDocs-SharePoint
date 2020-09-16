---
title: "How to migrate your file share content to SharePoint using the Azure Data Box"
ms.reviewer: 
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.service: sharepoint-online
search.appverid: MET150
ms.collection: 
- IT_Sharepoint_Server_Top
- Strat_SP_gtc
- SPMigration
- M365-collaboration
localization_priority: Normal
description: "Learn how to migrate your file share content to SharePoint in Microsoft 365 by using the Azure Data Box"
---

# Migrate your file share content to SharePoint using the Azure Data Box

Use your Azure Data Box and the SharePoint Migration Tool (SPMT) to easily migrate your file share content to SharePoint and OneDrive in Microsoft 365. By using the Data Box, you can remove dependency on your WAN link to transfer the data.  

The Microsoft Azure Data Box is a service that lets you order a device from the Microsoft Azure portal. You can then copy terabytes of data from your servers to the device. After shipping it back to Microsoft, your data is copied into Azure. Depending on the size of data you intend to transfer, you can choose from:

- [Data Box Disk](https://docs.microsoft.com/azure/databox/data-box-disk-overview) with 35-TB usable capacity per order for small-to-medium datasets.
- [Data Box](https://docs.microsoft.com/azure/databox/data-box-overview) with 80-TB usable capacity per device for medium-to-large datasets.
- [Data Box Heavy](https://docs.microsoft.com/azure/databox/data-box-heavy-overview) with 770-TB usable capacity per device for large datasets.

This article specifically talks about how to use the Data Box to migrate your file share content to SharePoint in Microsoft 365.  

## Requirements and costs

#### For Data Box

- Data Box is only available for Enterprise Agreement (EA), Cloud solution provider (CSP), or Pay-as-you-go subscription offers. If your subscription does not fall in any of the above types, contact Microsoft Support to upgrade your subscription, or see [Azure subscription pricing](https://azure.microsoft.com/pricing/).
- There is a fee to use Data Box. Make sure to review the [Data Box pricing](https://azure.microsoft.com/pricing/details/databox/).

#### For SharePoint

- Review the minimum requirements for the [SharePoint Migration Tool (SPMT)](/sharepointmigration/how-to-use-the-sharepoint-migration-tool).


## Workflow overview

This workflow requires you to perform steps on Data Box as well as on SharePoint.

1. Order Data Box.

2. Receive and set up your Data Box.

3. Copy data from your on-premises file share to folder for Azure Files on your device.

4. After the copy is complete, ship the device back as per the instructions.

5. Wait for the data to completely upload to Azure.

The following steps relate to SharePoint.

1. Create a VM in the Azure portal and mount the Azure file share on it.

2. On the Azure VM, install SPMT.

3. Using the Azure file share as the SOURCE, run SPMT.

4. Complete the final steps of SPMT.

5. Verify and confirm your data.


## Use Data Box to copy data

Take the following steps to copy data to your Data Box.

1. [Order your Data Box](https://docs.microsoft.com/azure/databox/data-box-deploy-ordered).

2. After you receive your Data Box, [Set up the device](https://docs.microsoft.com/azure/databox/data-box-deploy-set-up). You'll cable and configure your device.

3. [Copy data to Data Box](https://docs.microsoft.com/azure/databox/data-box-deploy-copy-data). While copying, make sure to:

    - Use only the *StorageAccountName_AzFile* folder in the Data Box to copy the data. This is because you want the data to end up in an Azure file share, not in block blobs or page blobs.
    - Copy files to a folder within *StorageAccountName_AzFile* folder. A subfolder within *StorageAccountName_AzFile* folder creates a file share. Files copied directly to *StorageAccountName_AzFile* folder fail, and are uploaded as block blobs. This is the file share that you will mount on your VM in the next step.

4. Run [Prepare to ship](https://docs.microsoft.com/azure/databox/data-box-deploy-picked-up#prepare-to-ship) on your device. A successful 'prepare to ship' ensures a successful upload of files to Azure.

5. [Return the device](https://docs.microsoft.com/azure/databox/data-box-deploy-picked-up#ship-data-box-back).

6. [Verify the data upload to Azure](https://docs.microsoft.com/azure/databox/data-box-deploy-picked-up#verify-data-upload-to-azure).


## Migrating your data to Microsoft 365 using SPMT

After you receive confirmation from the Azure data team that your data copy has completed, you can now proceed to migrate your data to Microsoft 365. For best performance and connectivity, we recommend that you create an Azure Virtual Machine (VM).

1. Sign into the Azure portal, and then create a virtual machine.  To learn how, see  [Quickstart: Create Windows virtual machine in the Azure portal](/azure/virtual-machines/windows/quick-create-portal).

2. [Mount the Azure file share onto that VM](/azure/storage/files/storage-how-to-use-files-windows).

3. Download the SharePoint Migration Tool, and install it on your Azure VM. 

Download here: [SharePoint Migration Tool](https://spmtreleasescus.blob.core.windows.net/install/default.htm).
4. Start SPMT.  Select **Sign in**, and enter your Microsoft 365 username and password.<br><br>![SharePoint Migration Tool](media/spmt-intro.png).

5. Select **File share**. Enter the path to your Azure file share where your data is located.

6. Follow the remaining prompts as normal, including your target location. For more info, see [How to use the SharePoint Migration Tool](/sharepointmigration/how-to-use-the-sharepoint-migration-tool). 


> [!IMPORTANT]
> - The speed at which data is ingested into SharePoint is impacted by several factors, regardless if you have your data already in Azure. Understanding these factors will help you plan and maximize the efficiency of your migration.  For more info, see  [SharePoint and OneDrive Migration Speed](/sharepointmigration/sharepoint-online-and-onedrive-migration-speed).
> - There is a risk of losing existing permissions on files when migrating the data to SharePoint. You may also lose certain metadata, such as "Created by" and "Date modified by".

