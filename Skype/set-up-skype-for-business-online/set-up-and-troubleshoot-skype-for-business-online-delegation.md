---
title: Set up and troubleshoot Skype for Business Online delegation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: This article explains how to set up and troubleshoot Skype for Business Online delegation. This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.
ms.openlocfilehash: bf3bf61a633366408e2584a89dfee9ad771ce78e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Set up and troubleshoot Skype for Business Online delegation

This article explains how to set up and troubleshoot Skype for Business Online delegation. This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.
  
## <a name="guidelines-and-requirements"></a>Guidelines and requirements

### <a name="guidelines-for-delegation"></a>Guidelines for delegation

Setting up and getting delegation to work correctly depends on you following these guidelines:
  
- You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.
    
- You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.
    
- Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile. That mail profile should contain only one account.
    
- Skype for Business for the delegator and the delegate should be Online users. Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.
    
- Both the delegator and delegate should be using the same major version of Outlook.
    
- The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy. You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.
    
- Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.
    
- Shared mailboxes aren't supported for Skype for Business Online delegation. This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).
    
### <a name="skype-for-business-client-version-support"></a>Skype for Business client version support

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype for Business Basic Client**| Not supported |Not supported
|**Skype for Business 2015**|Compatible| Compatible|
|**Skype for Business 2016**|Compatible| Compatible|

   
### <a name="licensing-requirements"></a>Licensing requirements

**Enterprise E3 licensing scenario**

|**License**|**Clients**|**Notas**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016  <br/> Skype for Business 2016 used with Outlook 2013 or Outlook 2016  <br/> |Skype for Business Basic client doesn't support delegation.  <br/> For Mac clients, you can delegate calls but not meetings.  <br/> |
|Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan  <br/> |Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016  <br/> Skype for Business 2016 used with Outlook 2013 or Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype for Business Basic client doesn't support delegation.  <br/> For Mac clients, you can delegate calls but not meetings.  <br/> |
   
**Enterprise E5 licensing scenario**

|**License**|**Clients**|**Notas**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.  <br/> Skype for Business 2016 used with Outlook 2013 or Outlook 2016  <br/> |Skype for Business Basic client doesn't support delegation.  <br/> For Mac clients, you can delegate calls but not meetings.  <br/> |
|Enterprise E5 plus Office 365 Calling Plan  <br/> |Skype for Business for Mac 2016  <br/> Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016  <br/> Skype for Business 2016 used with Outlook 2013 or Outlook 2016  <br/> Lync para Mac 2011  <br/> |Skype for Business Basic client doesn't support delegation.  <br/> For Mac clients, you can delegate calls but not meetings.  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>Set up and verify delegation

To set up Skype for Business Online delegation, follow these steps:
  
### <a name="for-windows-clients"></a>For Windows clients

 **Call Forwarding tab**
  
1. Select **Tools** > **Options** > **Call Forwarding Settings**.
    
2. Select **Edit my delegate members**.
    
3. Select **Add**, select the delegate that you want to add, and then select **OK**.
    
 **No Call Forwarding tab**
  
1. In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.
    
2. Locate and then add the name of the person who is going to be the delegate.
    
3. Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.
    
### <a name="for-mac-clients---lync"></a>For Mac clients - Lync

 **Call Forwarding tab**
  
- If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation. This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.
    
### <a name="verify-success"></a>Verify success

If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created. The delegator should see that the **Delegates** group is created.
  
> [!NOTE]
> Delegation permissions usually appear within 30 minutes of the setup process. However, this process can take up to 24 hours to complete. 
  
## <a name="troubleshooting"></a>Solución de problemas

### <a name="common-issues"></a>Common issues

- > **Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.
    
  - > **Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.
    
- > **Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.
    
  - > **Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.
    
### <a name="other-common-issues"></a>Other common issues

- Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.
    
- The Skype for Business Basic client isn't supported.
    
    > [!NOTE]
    > If you install the Skype for Business Basic client, it will remove and break delegation. 
  
- If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.
    
    > [!NOTE]
    > It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.
  
- Creating a security group and adding delegation permissions for that security group isn't supported.
    
- MAPI is unavailable. See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).
    
- The Exchange Online mailbox isn't accessible through the Skype for Business client. If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.
    
## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](set-up-skype-for-business-online.md)

[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md)
