---
title: Eliminar la configuración de la reunión en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Resumen: Aprenda a eliminar la configuración de la reunión en Skype empresarial Server.'
ms.openlocfilehash: dd07d3239b212f09391e9bc8c66f29bca62b2c3f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818591"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d73bc-103">Eliminar la configuración de la reunión en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d73bc-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d73bc-104">**Resumen:** Aprenda a eliminar la configuración de la reunión en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d73bc-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="d73bc-105">Puede eliminar la configuración de la reunión con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d73bc-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="d73bc-p101">Puede eliminar una configuración de sitio o de usuario, pero no puede eliminar la configuración global. Si intenta eliminar la configuración global, esta se restablece automáticamente a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="d73bc-p101">You can delete a site or user configuration, but you cannot delete the global configuration. If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d73bc-108">Eliminar la configuración de la reunión con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d73bc-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d73bc-109">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d73bc-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d73bc-110">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d73bc-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d73bc-111">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="d73bc-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="d73bc-112">En la lista de configuraciones de reunión, haga clic en la configuración de sitio o de grupo que desea eliminar, haga clic en **Editar** y después en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d73bc-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d73bc-113">Eliminar la configuración de la reunión mediante el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d73bc-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d73bc-114">Para eliminar la configuración de la reunión, use el cmdlet **Remove-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="d73bc-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="d73bc-115">El siguiente comando elimina las opciones de configuración de reunión aplicadas al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="d73bc-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="d73bc-116">El siguiente comando quita todas las opciones de configuración de reunión que se aplican al ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="d73bc-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="d73bc-117">Para obtener más información, incluida una lista completa de parámetros, consulte [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d73bc-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

