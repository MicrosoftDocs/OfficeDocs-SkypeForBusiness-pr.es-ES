---
title: Allow users to contact external Skype for Business users
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: e21b89c24618d2296dc44766b8d6ddbd3d527ef7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="2fc2b-103">Allow users to contact external Skype for Business users</span><span class="sxs-lookup"><span data-stu-id="2fc2b-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="2fc2b-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="2fc2b-105">Use the steps in this article when:</span><span class="sxs-lookup"><span data-stu-id="2fc2b-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="2fc2b-106">You have users on different domains in your business.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-106">You have users on different domains in your business.</span></span> <span data-ttu-id="2fc2b-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="2fc2b-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
<span data-ttu-id="2fc2b-109">-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-109">-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="2fc2b-110">If you and they use the default Skype for Business settings, this will work automatically.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="2fc2b-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="2fc2b-112">Enable business-to-business communications for your users</span><span class="sxs-lookup"><span data-stu-id="2fc2b-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="2fc2b-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2fc2b-113"></span></span>

<span data-ttu-id="2fc2b-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 to do this.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 to do this.</span></span>
  
1. <span data-ttu-id="2fc2b-115">Sign in with your Office 365 admin account.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-115">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="2fc2b-116">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-116">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="2fc2b-118">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-118">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
4. <span data-ttu-id="2fc2b-119">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-119">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="2fc2b-120">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-120">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="2fc2b-121">Esta es la configuración que se aplica normalmente.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-121">This is the default setting.</span></span>
    
5. <span data-ttu-id="2fc2b-122">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-122">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
6. <span data-ttu-id="2fc2b-123">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-123">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="2fc2b-124">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-124">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
7. <span data-ttu-id="2fc2b-125">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-125">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="2fc2b-126">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="2fc2b-126">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="2fc2b-127">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**. For instructions on how to open these ports in your firewall, check the documentation that came with it.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-127">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**. For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="2fc2b-128">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="2fc2b-128">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
8. <span data-ttu-id="2fc2b-129">**WAIT UP TO 24 HOURS TO TEST**.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-129">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="2fc2b-130">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-130">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="2fc2b-131">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span><span class="sxs-lookup"><span data-stu-id="2fc2b-131">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="2fc2b-132">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="2fc2b-132">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="2fc2b-133">Test and troubleshoot</span><span class="sxs-lookup"><span data-stu-id="2fc2b-133">Test and troubleshoot</span></span>
<span data-ttu-id="2fc2b-134"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2fc2b-134"></span></span>

 <span data-ttu-id="2fc2b-135">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span><span class="sxs-lookup"><span data-stu-id="2fc2b-135">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="2fc2b-136">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-136">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="2fc2b-137">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-137">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="2fc2b-138">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-138">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="2fc2b-139">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="2fc2b-139">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="2fc2b-140">Ask your Skype for Business contact to send you a request to chat.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-140">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="2fc2b-141">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span><span class="sxs-lookup"><span data-stu-id="2fc2b-141">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="2fc2b-142">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-142">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="2fc2b-143">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-143">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="2fc2b-144">How to find others, and be found, when connecting with another business</span><span class="sxs-lookup"><span data-stu-id="2fc2b-144">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="2fc2b-145"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2fc2b-145"></span></span>

<span data-ttu-id="2fc2b-146">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com. Then they will need to add the person to their list of contacts.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-146">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com. Then they will need to add the person to their list of contacts.</span></span>
  
![To find a user in a federated business, you must search for their email address (this is usually also their sign in name).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="2fc2b-148">Tips on setting up communications with federated businesses</span><span class="sxs-lookup"><span data-stu-id="2fc2b-148">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="2fc2b-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2fc2b-149"></span></span>

- <span data-ttu-id="2fc2b-150">To configure federation between Skype for Business 2015 and Skype for Business Online, see this TechNet article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="2fc2b-150">To configure federation between Skype for Business 2015 and Skype for Business Online, see this TechNet article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="2fc2b-151">To configure federation between Lync and Skype for Business Online, see this TechNet article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="2fc2b-151">To configure federation between Lync and Skype for Business Online, see this TechNet article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="2fc2b-152">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-152">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="2fc2b-153">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-153">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="2fc2b-154">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-154">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="2fc2b-155">Turn off external communication for specific individuals</span><span class="sxs-lookup"><span data-stu-id="2fc2b-155">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="2fc2b-156"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2fc2b-156"></span></span>

<span data-ttu-id="2fc2b-157">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-157">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="2fc2b-158">Sign in with your Office 365 admin account.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-158">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="2fc2b-159">In the Office 365 admin center, go to **Users** > **Active users**.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-159">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="2fc2b-160">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-160">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="2fc2b-162">In the **Skype for Business admin center**, choose **External communications**.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-162">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="2fc2b-163">On the **Options** page, all of the choices will be selected.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-163">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="2fc2b-164">Clear the communications you want to disable.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-164">Clear the communications you want to disable.</span></span> <span data-ttu-id="2fc2b-165">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-165">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="2fc2b-167">Elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-167">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2fc2b-168">You may have to wait for up to 24 hours for your changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="2fc2b-168">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="2fc2b-169">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2fc2b-169">Related topics</span></span>
<span data-ttu-id="2fc2b-170"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="2fc2b-170"></span></span>

[<span data-ttu-id="2fc2b-171">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="2fc2b-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="2fc2b-172">Let Skype for Business users add Skype contacts</span><span class="sxs-lookup"><span data-stu-id="2fc2b-172">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  

