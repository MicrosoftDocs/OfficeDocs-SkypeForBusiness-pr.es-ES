---
title: Eliminar una directiva de archivado existente en Skype Empresarial Server
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Resumen: obtenga información sobre cómo eliminar una directiva de archivado para Skype Empresarial Server.'
ms.openlocfilehash: 2baad7d862b1b6739019a4459492bfb3b67e04cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095394"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="a9779-103">Eliminar una directiva de archivado existente en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="a9779-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="a9779-104">**Resumen:** Obtenga información sobre cómo eliminar una directiva de archivado para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a9779-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="a9779-105">Puede eliminar una directiva de usuario o una directiva de sitio, pero no la directiva global.</span><span class="sxs-lookup"><span data-stu-id="a9779-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="a9779-106">Si elimina la directiva global, Skype Empresarial Server restablece automáticamente la directiva a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a9779-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="a9779-107">Eliminar una directiva mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="a9779-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="a9779-108">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="a9779-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="a9779-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a9779-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a9779-110">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="a9779-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="a9779-111">En la lista de directivas, haga clic en la directiva de usuario o sitio que desea eliminar, haga clic en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a9779-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="a9779-112">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a9779-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="a9779-113">Eliminar una directiva mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9779-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="a9779-114">También puede eliminar directivas de archivado mediante el cmdlet **Remove-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="a9779-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="a9779-115">Por ejemplo, el siguiente comando elimina la directiva con el objeto Identity site:Redmond.</span><span class="sxs-lookup"><span data-stu-id="a9779-115">For example, the following command deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="a9779-116">Cuando se elimina una directiva configurada en el nivel de sitio, los usuarios administrados anteriormente por la directiva de sitio se regirán automáticamente por la directiva de archivado global:</span><span class="sxs-lookup"><span data-stu-id="a9779-116">When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="a9779-117">Este comando quita todas las directivas de archivado aplicadas al nivel por usuario:</span><span class="sxs-lookup"><span data-stu-id="a9779-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="a9779-118">Este comando quita todas las directivas de archivado donde se deshabilitó el archivado interno:</span><span class="sxs-lookup"><span data-stu-id="a9779-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="a9779-119">Para obtener más información, vea el tema de ayuda del cmdlet [Remove-CsArchivingPolicy.](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a9779-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>