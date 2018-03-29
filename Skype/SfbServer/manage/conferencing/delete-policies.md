---
title: Eliminar directivas de conferencia en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Summary: Learn how to delete conferencing policies in Skype for Business Server 2015.'
ms.openlocfilehash: 783e2ef4c1bc0732fd93949427cea21c5ca165ea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="delete-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="5c55d-103">Eliminar directivas de conferencia en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5c55d-103">Delete conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5c55d-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5c55d-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5c55d-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5c55d-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5c55d-106">Delete conferencing policies by using Skype for Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="5c55d-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="5c55d-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5c55d-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="5c55d-108">Open Skype for Business Server Control Panel.</span><span class="sxs-lookup"><span data-stu-id="5c55d-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5c55d-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="5c55d-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="5c55d-110">En la lista de directivas de conferencia, haga clic en la directiva de usuario o en el sitio que desea eliminar, haga clic en **Editar** y, después, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5c55d-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5c55d-111">Delete conferencing policies by using Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="5c55d-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5c55d-112">Para eliminar las directivas de conferencia, use el cmdlet **Remove-CsConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="5c55d-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5c55d-113">El comando siguiente quita la directiva de conferencia con el valor de identidad RedmondConferencingPolicy:</span><span class="sxs-lookup"><span data-stu-id="5c55d-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="5c55d-114">El comando siguiente quita cualquier directiva de conferencia que permita que usuarios externos graben la conferencia:</span><span class="sxs-lookup"><span data-stu-id="5c55d-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="5c55d-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5c55d-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

