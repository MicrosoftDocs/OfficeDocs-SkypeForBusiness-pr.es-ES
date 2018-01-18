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
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="7997e-104">Set up and troubleshoot Skype for Business Online delegation</span><span class="sxs-lookup"><span data-stu-id="7997e-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="7997e-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span><span class="sxs-lookup"><span data-stu-id="7997e-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="7997e-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span><span class="sxs-lookup"><span data-stu-id="7997e-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="7997e-107">Guidelines and requirements</span><span class="sxs-lookup"><span data-stu-id="7997e-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="7997e-108">Guidelines for delegation</span><span class="sxs-lookup"><span data-stu-id="7997e-108">Guidelines for delegation</span></span>

<span data-ttu-id="7997e-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span><span class="sxs-lookup"><span data-stu-id="7997e-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="7997e-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span><span class="sxs-lookup"><span data-stu-id="7997e-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="7997e-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span><span class="sxs-lookup"><span data-stu-id="7997e-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="7997e-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span><span class="sxs-lookup"><span data-stu-id="7997e-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="7997e-113">That mail profile should contain only one account.</span><span class="sxs-lookup"><span data-stu-id="7997e-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="7997e-114">Skype for Business for the delegator and the delegate should be Online users.</span><span class="sxs-lookup"><span data-stu-id="7997e-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="7997e-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span><span class="sxs-lookup"><span data-stu-id="7997e-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="7997e-116">Both the delegator and delegate should be using the same major version of Outlook.</span><span class="sxs-lookup"><span data-stu-id="7997e-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="7997e-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span><span class="sxs-lookup"><span data-stu-id="7997e-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="7997e-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span><span class="sxs-lookup"><span data-stu-id="7997e-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="7997e-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span><span class="sxs-lookup"><span data-stu-id="7997e-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="7997e-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span><span class="sxs-lookup"><span data-stu-id="7997e-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="7997e-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span><span class="sxs-lookup"><span data-stu-id="7997e-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="7997e-122">Skype for Business client version support</span><span class="sxs-lookup"><span data-stu-id="7997e-122">Skype for Business client version support</span></span>

||<span data-ttu-id="7997e-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="7997e-123">**Outlook 2013**</span></span>|<span data-ttu-id="7997e-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="7997e-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7997e-125">**Lync/Skype for Business Basic Client**</span><span class="sxs-lookup"><span data-stu-id="7997e-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="7997e-126">Not supported</span><span class="sxs-lookup"><span data-stu-id="7997e-126">Not supported</span></span> |<span data-ttu-id="7997e-127">Not supported</span><span class="sxs-lookup"><span data-stu-id="7997e-127">Not supported</span></span>
|<span data-ttu-id="7997e-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="7997e-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="7997e-129">Compatible</span><span class="sxs-lookup"><span data-stu-id="7997e-129">Supported</span></span>| <span data-ttu-id="7997e-130">Compatible</span><span class="sxs-lookup"><span data-stu-id="7997e-130">Supported</span></span>|
|<span data-ttu-id="7997e-131">**Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="7997e-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="7997e-132">Compatible</span><span class="sxs-lookup"><span data-stu-id="7997e-132">Supported</span></span>| <span data-ttu-id="7997e-133">Compatible</span><span class="sxs-lookup"><span data-stu-id="7997e-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="7997e-134">Licensing requirements</span><span class="sxs-lookup"><span data-stu-id="7997e-134">Licensing requirements</span></span>

<span data-ttu-id="7997e-135">**Enterprise E3 licensing scenario**</span><span class="sxs-lookup"><span data-stu-id="7997e-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="7997e-136">**License**</span><span class="sxs-lookup"><span data-stu-id="7997e-136">**License**</span></span>|<span data-ttu-id="7997e-137">**Clients**</span><span class="sxs-lookup"><span data-stu-id="7997e-137">**Clients**</span></span>|<span data-ttu-id="7997e-138">**Notas**</span><span class="sxs-lookup"><span data-stu-id="7997e-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7997e-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="7997e-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="7997e-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7997e-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7997e-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7997e-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="7997e-142">Skype for Business Basic client doesn't support delegation.</span><span class="sxs-lookup"><span data-stu-id="7997e-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7997e-143">For Mac clients, you can delegate calls but not meetings.</span><span class="sxs-lookup"><span data-stu-id="7997e-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="7997e-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span><span class="sxs-lookup"><span data-stu-id="7997e-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="7997e-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7997e-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7997e-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7997e-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7997e-147">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="7997e-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="7997e-148">Skype for Business Basic client doesn't support delegation.</span><span class="sxs-lookup"><span data-stu-id="7997e-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7997e-149">For Mac clients, you can delegate calls but not meetings.</span><span class="sxs-lookup"><span data-stu-id="7997e-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="7997e-150">**Enterprise E5 licensing scenario**</span><span class="sxs-lookup"><span data-stu-id="7997e-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="7997e-151">**License**</span><span class="sxs-lookup"><span data-stu-id="7997e-151">**License**</span></span>|<span data-ttu-id="7997e-152">**Clients**</span><span class="sxs-lookup"><span data-stu-id="7997e-152">**Clients**</span></span>|<span data-ttu-id="7997e-153">**Notas**</span><span class="sxs-lookup"><span data-stu-id="7997e-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7997e-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="7997e-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="7997e-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="7997e-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="7997e-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7997e-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="7997e-157">Skype for Business Basic client doesn't support delegation.</span><span class="sxs-lookup"><span data-stu-id="7997e-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7997e-158">For Mac clients, you can delegate calls but not meetings.</span><span class="sxs-lookup"><span data-stu-id="7997e-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="7997e-159">Enterprise E5 plus Office 365 Calling Plan</span><span class="sxs-lookup"><span data-stu-id="7997e-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="7997e-160">Skype for Business for Mac 2016</span><span class="sxs-lookup"><span data-stu-id="7997e-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="7997e-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7997e-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7997e-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7997e-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="7997e-163">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="7997e-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="7997e-164">Skype for Business Basic client doesn't support delegation.</span><span class="sxs-lookup"><span data-stu-id="7997e-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="7997e-165">For Mac clients, you can delegate calls but not meetings.</span><span class="sxs-lookup"><span data-stu-id="7997e-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="7997e-166">Set up and verify delegation</span><span class="sxs-lookup"><span data-stu-id="7997e-166">Set up and verify delegation</span></span>

<span data-ttu-id="7997e-167">To set up Skype for Business Online delegation, follow these steps:</span><span class="sxs-lookup"><span data-stu-id="7997e-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="7997e-168">For Windows clients</span><span class="sxs-lookup"><span data-stu-id="7997e-168">For Windows clients</span></span>

 <span data-ttu-id="7997e-169">**Call Forwarding tab**</span><span class="sxs-lookup"><span data-stu-id="7997e-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="7997e-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span><span class="sxs-lookup"><span data-stu-id="7997e-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="7997e-171">Select **Edit my delegate members**.</span><span class="sxs-lookup"><span data-stu-id="7997e-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="7997e-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span><span class="sxs-lookup"><span data-stu-id="7997e-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="7997e-173">**No Call Forwarding tab**</span><span class="sxs-lookup"><span data-stu-id="7997e-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="7997e-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span><span class="sxs-lookup"><span data-stu-id="7997e-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="7997e-175">Locate and then add the name of the person who is going to be the delegate.</span><span class="sxs-lookup"><span data-stu-id="7997e-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="7997e-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span><span class="sxs-lookup"><span data-stu-id="7997e-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="7997e-177">For Mac clients - Lync</span><span class="sxs-lookup"><span data-stu-id="7997e-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="7997e-178">**Call Forwarding tab**</span><span class="sxs-lookup"><span data-stu-id="7997e-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="7997e-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span><span class="sxs-lookup"><span data-stu-id="7997e-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="7997e-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span><span class="sxs-lookup"><span data-stu-id="7997e-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="7997e-181">Verify success</span><span class="sxs-lookup"><span data-stu-id="7997e-181">Verify success</span></span>

<span data-ttu-id="7997e-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span><span class="sxs-lookup"><span data-stu-id="7997e-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="7997e-183">The delegator should see that the **Delegates** group is created.</span><span class="sxs-lookup"><span data-stu-id="7997e-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7997e-184">Delegation permissions usually appear within 30 minutes of the setup process.</span><span class="sxs-lookup"><span data-stu-id="7997e-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="7997e-185">However, this process can take up to 24 hours to complete.</span><span class="sxs-lookup"><span data-stu-id="7997e-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="7997e-186">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="7997e-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="7997e-187">Common issues</span><span class="sxs-lookup"><span data-stu-id="7997e-187">Common issues</span></span>

- > <span data-ttu-id="7997e-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span><span class="sxs-lookup"><span data-stu-id="7997e-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="7997e-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span><span class="sxs-lookup"><span data-stu-id="7997e-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="7997e-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span><span class="sxs-lookup"><span data-stu-id="7997e-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="7997e-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span><span class="sxs-lookup"><span data-stu-id="7997e-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="7997e-192">Other common issues</span><span class="sxs-lookup"><span data-stu-id="7997e-192">Other common issues</span></span>

- <span data-ttu-id="7997e-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span><span class="sxs-lookup"><span data-stu-id="7997e-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="7997e-194">The Skype for Business Basic client isn't supported.</span><span class="sxs-lookup"><span data-stu-id="7997e-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7997e-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span><span class="sxs-lookup"><span data-stu-id="7997e-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="7997e-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span><span class="sxs-lookup"><span data-stu-id="7997e-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7997e-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span><span class="sxs-lookup"><span data-stu-id="7997e-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="7997e-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span><span class="sxs-lookup"><span data-stu-id="7997e-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="7997e-199">MAPI is unavailable.</span><span class="sxs-lookup"><span data-stu-id="7997e-199">MAPI is unavailable.</span></span> <span data-ttu-id="7997e-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="7997e-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="7997e-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span><span class="sxs-lookup"><span data-stu-id="7997e-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="7997e-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span><span class="sxs-lookup"><span data-stu-id="7997e-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="7997e-203">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7997e-203">Related topics</span></span>
[<span data-ttu-id="7997e-204">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="7997e-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="7997e-205">Let Skype for Business users add Skype contacts</span><span class="sxs-lookup"><span data-stu-id="7997e-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
