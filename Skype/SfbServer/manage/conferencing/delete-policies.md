---
title: Eliminar directivas de conferencia en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Resumen: Obtenga información sobre cómo eliminar las directivas de conferencia en Skype para Business Server.'
ms.openlocfilehash: 534dc52e730051b82c7f5edcb1bd2564be7dde2f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919440"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="bddc4-103">Eliminar directivas de conferencia en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="bddc4-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="bddc4-104">**Resumen:** Obtenga información sobre cómo eliminar las directivas de conferencia en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="bddc4-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="bddc4-105">Puede eliminar las directivas de conferencia mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="bddc4-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="bddc4-106">Eliminar directivas de conferencia mediante Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="bddc4-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="bddc4-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="bddc4-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="bddc4-108">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="bddc4-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="bddc4-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="bddc4-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="bddc4-110">En la lista de directivas de conferencia, haga clic en la directiva de usuario o en el sitio que desea eliminar, haga clic en **Editar** y, después, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="bddc4-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="bddc4-111">Eliminar directivas de conferencia mediante Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="bddc4-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="bddc4-112">Para eliminar las directivas de conferencia, use el cmdlet **Remove-CsConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="bddc4-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="bddc4-113">El comando siguiente quita la directiva de conferencia con el valor de identidad RedmondConferencingPolicy:</span><span class="sxs-lookup"><span data-stu-id="bddc4-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="bddc4-114">El comando siguiente quita cualquier directiva de conferencia que permita que usuarios externos graben la conferencia:</span><span class="sxs-lookup"><span data-stu-id="bddc4-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="bddc4-115">Para obtener más información, incluida la sintaxis completa y una lista de parámetros, consulte [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bddc4-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

