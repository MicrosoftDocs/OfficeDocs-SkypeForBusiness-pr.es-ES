---
title: Modificar valores de configuración de Skype para Business Server de la reunión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumen: Obtenga información sobre cómo modificar los valores de configuración de Skype para Business Server de la reunión.'
ms.openlocfilehash: 73127bfce04c8c124ce8036222d755de6bc37058
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199958"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="02f40-103">Modificar valores de configuración de Skype para Business Server de la reunión</span><span class="sxs-lookup"><span data-stu-id="02f40-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="02f40-104">**Resumen:** Obtenga información sobre cómo modificar los valores de configuración de Skype para Business Server de la reunión.</span><span class="sxs-lookup"><span data-stu-id="02f40-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="02f40-105">Puede modificar una configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="02f40-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="02f40-106">Modificar una configuración de reunión mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="02f40-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="02f40-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="02f40-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="02f40-108">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="02f40-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="02f40-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="02f40-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="02f40-110">En la lista de configuraciones de la reunión, haga clic en la configuración que desee cambiar, luego, haga clic en **Editar** y, por último, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="02f40-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="02f40-111">En **Editar configuración de reunión**, modifique cualquiera de las opciones de configuración, excepto el nombre de la configuración, que no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="02f40-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="02f40-112">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="02f40-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="02f40-113">Modificar una configuración de reunión mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="02f40-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="02f40-114">Para modificar las opciones de configuración de la reunión, use el cmdlet **Set-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="02f40-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="02f40-p101">El comando que se muestra en el siguiente ejemplo modifica las opciones de configuración de reunión asignadas al sitio Redmond (-Identity site:Redmond). En este caso, el valor de la propiedad DesignateAsPresenter es Everyone (todos):</span><span class="sxs-lookup"><span data-stu-id="02f40-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="02f40-117">Para obtener más información, incluida una lista completa de los parámetros, consulte [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="02f40-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

