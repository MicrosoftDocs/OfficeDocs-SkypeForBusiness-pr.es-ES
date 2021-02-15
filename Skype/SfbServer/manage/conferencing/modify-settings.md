---
title: Modificar las opciones de configuración de reuniones en Skype Empresarial Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumen: obtenga información sobre cómo modificar las opciones de configuración de reuniones en Skype Empresarial Server.'
ms.openlocfilehash: 80ba12266ebc45fdae3256f5238ecf18415734c8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828000"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="eb1fa-103">Modificar las opciones de configuración de reuniones en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="eb1fa-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="eb1fa-104">**Resumen:** Obtenga información sobre cómo modificar las opciones de configuración de reuniones en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eb1fa-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="eb1fa-105">Puede modificar las opciones de configuración de reuniones con el Panel de control de Skype Empresarial Server o con el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eb1fa-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="eb1fa-106">Modificar las opciones de configuración de reuniones mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="eb1fa-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="eb1fa-107">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="eb1fa-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="eb1fa-108">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eb1fa-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="eb1fa-109">En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Configuración **de reunión.**</span><span class="sxs-lookup"><span data-stu-id="eb1fa-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="eb1fa-110">En la lista de configuraciones de reunión, haga clic en la configuración que desea cambiar, haga clic en Editar **y,** a continuación, haga clic **en Mostrar detalles.**</span><span class="sxs-lookup"><span data-stu-id="eb1fa-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="eb1fa-111">En **Editar configuración de reunión**, modifique cualquiera de las configuraciones de participación en reuniones, excepto el nombre, que no se puede modificar.
</span><span class="sxs-lookup"><span data-stu-id="eb1fa-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="eb1fa-112">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="eb1fa-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="eb1fa-113">Modificar las opciones de configuración de reuniones mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="eb1fa-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="eb1fa-114">Para modificar las opciones de configuración de reuniones, use el cmdlet **Set-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="eb1fa-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="eb1fa-115">El comando que se muestra en el siguiente ejemplo modifica las opciones de configuración de reunión asignadas al sitio redmond (-Identity site:Redmond).</span><span class="sxs-lookup"><span data-stu-id="eb1fa-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="eb1fa-116">En este caso, el valor de la propiedad DesignateAsPresenter se establece en Todos:</span><span class="sxs-lookup"><span data-stu-id="eb1fa-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="eb1fa-117">Para obtener más información, incluida una lista completa de parámetros, vea [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="eb1fa-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

