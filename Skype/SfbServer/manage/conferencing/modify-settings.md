---
title: Modificar la configuración de la reunión en Skype empresarial Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumen: Aprenda a modificar la configuración de la reunión en Skype empresarial Server.'
ms.openlocfilehash: 893e3fb8c9c441f8dc515eaf3a8a4aaa1ff04620
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818501"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="1fc95-103">Modificar la configuración de la reunión en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1fc95-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="1fc95-104">**Resumen:** Aprenda a modificar la configuración de la reunión en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1fc95-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="1fc95-105">Puede modificar la configuración de la reunión mediante el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1fc95-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1fc95-106">Modificar la configuración de la reunión con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1fc95-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1fc95-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1fc95-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="1fc95-108">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1fc95-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1fc95-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="1fc95-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="1fc95-110">En la lista de configuraciones de la reunión, haga clic en la configuración que desee cambiar, luego, haga clic en **Editar** y, por último, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="1fc95-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1fc95-111">En **Editar configuración de reunión**, modifique cualquiera de las opciones de configuración, excepto el nombre de la configuración, que no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="1fc95-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="1fc95-112">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1fc95-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1fc95-113">Modificar la configuración de la reunión mediante el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1fc95-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1fc95-114">Para modificar las opciones de configuración de la reunión, use el cmdlet **Set-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1fc95-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="1fc95-p101">El comando que se muestra en el siguiente ejemplo modifica las opciones de configuración de reunión asignadas al sitio Redmond (-Identity site:Redmond). En este caso, el valor de la propiedad DesignateAsPresenter es Everyone (todos):</span><span class="sxs-lookup"><span data-stu-id="1fc95-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="1fc95-117">Para obtener más información, incluida una lista completa de parámetros, consulte [set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1fc95-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

