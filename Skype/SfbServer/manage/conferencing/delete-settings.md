---
title: Eliminar las opciones de configuración de reunión en Skype Empresarial Server
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Summary: Learn how to delete meeting configuration settings in Skype for Business Server.'
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119499"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="ac8ad-103">Eliminar las opciones de configuración de reunión en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ac8ad-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="ac8ad-104">**Resumen:** Obtenga información sobre cómo eliminar las opciones de configuración de reuniones en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ac8ad-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="ac8ad-105">Puede eliminar las opciones de configuración de reuniones mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ac8ad-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="ac8ad-106">Puede eliminar un sitio o una configuración de usuario, pero no puede eliminar la configuración global.</span><span class="sxs-lookup"><span data-stu-id="ac8ad-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="ac8ad-107">Si intenta eliminar la configuración global, se restablece automáticamente a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="ac8ad-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ac8ad-108">Eliminar las opciones de configuración de reunión mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ac8ad-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ac8ad-109">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ac8ad-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ac8ad-110">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ac8ad-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ac8ad-111">En la barra de navegación izquierda, haga clic **en Conferencia y,** a continuación, haga clic en **Configuración de reunión.**</span><span class="sxs-lookup"><span data-stu-id="ac8ad-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="ac8ad-112">En la lista de configuraciones de reunión, haga clic en la configuración del sitio o grupo de servidores que desea eliminar, haga clic en **Editar** y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ac8ad-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ac8ad-113">Eliminar las opciones de configuración de reuniones mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ac8ad-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ac8ad-114">Para eliminar la configuración de reunión, use el cmdlet **Remove-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="ac8ad-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="ac8ad-115">El siguiente comando quita las opciones de configuración de reunión aplicadas al sitio redmond:</span><span class="sxs-lookup"><span data-stu-id="ac8ad-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="ac8ad-116">El siguiente comando quita todas las opciones de configuración de reunión aplicadas al ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="ac8ad-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="ac8ad-117">Para obtener más información, incluida una lista completa de parámetros, vea [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ac8ad-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
