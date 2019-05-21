---
title: Eliminar una directiva de archivado existente en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Resumen: Aprenda a eliminar una directiva de archivado para Skype empresarial Server.'
ms.openlocfilehash: 04ea9db10a2f95ba5010471f262d58c269c173d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278415"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="ee3c5-103">Eliminar una directiva de archivado existente en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ee3c5-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="ee3c5-104">**Resumen:** Aprenda a eliminar una directiva de archivado para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ee3c5-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="ee3c5-105">Puede eliminar una directiva de usuario o de sitio, pero no puede eliminar una directiva global.</span><span class="sxs-lookup"><span data-stu-id="ee3c5-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="ee3c5-106">Si elimina la directiva global, Skype empresarial Server restablece automáticamente la Directiva a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="ee3c5-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="ee3c5-107">Eliminar una directiva con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="ee3c5-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="ee3c5-108">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ee3c5-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="ee3c5-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ee3c5-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ee3c5-110">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="ee3c5-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="ee3c5-111">En la lista de directivas de archivado, haga clic en la directiva de usuario o sitio que desea eliminar, haga clic en **Editar** y, luego, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ee3c5-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="ee3c5-112">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ee3c5-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="ee3c5-113">Eliminar una directiva con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee3c5-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="ee3c5-114">También puede eliminar directivas de archivado con el cmdlet **Remove-CsArchivingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="ee3c5-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="ee3c5-p102">Por ejemplo, el siguiente comando elimina la directiva con el sitio de identidad: Redmond. Cuando se elimina una directiva configurada en el nivel del sitio, los usuarios a los que anteriormente administraba esta directiva de sitio se regirán de forma automática por la directiva de archivado global:</span><span class="sxs-lookup"><span data-stu-id="ee3c5-p102">For example, the following command deletes the policy with the Identity site:Redmond. When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="ee3c5-117">Este comando quita todas las directivas de archivado aplicadas al nivel por usuario:</span><span class="sxs-lookup"><span data-stu-id="ee3c5-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="ee3c5-118">Este comando quita todas las directivas de archivado donde se deshabilitó el archivado interno:</span><span class="sxs-lookup"><span data-stu-id="ee3c5-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="ee3c5-119">Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="ee3c5-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
