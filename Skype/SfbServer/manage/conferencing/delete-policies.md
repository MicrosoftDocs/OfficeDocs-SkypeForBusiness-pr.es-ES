---
title: Eliminar directivas de conferencia en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Resumen: obtenga información sobre cómo eliminar directivas de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119509"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="51f65-103">Eliminar directivas de conferencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="51f65-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="51f65-104">**Resumen:** Obtenga información sobre cómo eliminar directivas de conferencia en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="51f65-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="51f65-105">Puede eliminar directivas de conferencia mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="51f65-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="51f65-106">Eliminar directivas de conferencia mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="51f65-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="51f65-107">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="51f65-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="51f65-108">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="51f65-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="51f65-109">En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Directiva **de conferencia.**</span><span class="sxs-lookup"><span data-stu-id="51f65-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="51f65-110">En la lista de directivas de conferencia, haga clic en el sitio o la directiva de usuario que desea eliminar, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="51f65-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="51f65-111">Eliminar directivas de conferencia mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="51f65-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="51f65-112">Para eliminar directivas de conferencia, use el cmdlet **Remove-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="51f65-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="51f65-113">El comando siguiente quita la directiva de conferencia con el valor de identidad RedmondConferencingPolicy:</span><span class="sxs-lookup"><span data-stu-id="51f65-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="51f65-114">El siguiente comando elimina las directivas de conferencia que permiten a los usuarios externos grabar la conferencia:</span><span class="sxs-lookup"><span data-stu-id="51f65-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="51f65-115">Para obtener más información, incluida la sintaxis completa y una lista de parámetros, [vea Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="51f65-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
