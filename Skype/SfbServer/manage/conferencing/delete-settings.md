---
title: Eliminar una configuración de Skype para Business Server de reunión
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Resumen: Obtenga información sobre cómo eliminar una configuración de Skype para Business Server de reunión.'
ms.openlocfilehash: 2fbb278745eba392016b163be8f59a3abb07b47d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919384"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="6380b-103">Eliminar una configuración de Skype para Business Server de reunión</span><span class="sxs-lookup"><span data-stu-id="6380b-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="6380b-104">**Resumen:** Obtenga información sobre cómo eliminar una configuración de Skype para Business Server de reunión.</span><span class="sxs-lookup"><span data-stu-id="6380b-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="6380b-105">Puede eliminar una configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="6380b-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="6380b-p101">Puede eliminar una configuración de sitio o de usuario, pero no puede eliminar la configuración global. Si intenta eliminar la configuración global, esta se restablece automáticamente a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="6380b-p101">You can delete a site or user configuration, but you cannot delete the global configuration. If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6380b-108">Eliminar una configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="6380b-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6380b-109">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="6380b-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="6380b-110">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="6380b-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6380b-111">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="6380b-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="6380b-112">En la lista de configuraciones de reunión, haga clic en la configuración de sitio o de grupo que desea eliminar, haga clic en **Editar** y después en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="6380b-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6380b-113">Eliminar una configuración de reunión mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="6380b-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6380b-114">Para eliminar la configuración de la reunión, use el cmdlet **Remove-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6380b-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="6380b-115">El siguiente comando elimina las opciones de configuración de reunión aplicadas al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="6380b-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="6380b-116">El siguiente comando quita todas las opciones de configuración de reunión que se aplican al ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="6380b-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="6380b-117">Para obtener más información, incluida una lista completa de los parámetros, consulte [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6380b-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

