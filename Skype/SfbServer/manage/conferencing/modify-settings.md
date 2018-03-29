---
title: Modificar las opciones de configuración de reuniones en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Resumen: Conozca cómo modificar valores de configuración de Skype para Business Server 2015 de reunión.'
ms.openlocfilehash: 95f28f35859553f79fc6f74f8850f224bda54deb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="471c1-103">Modificar las opciones de configuración de reuniones en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="471c1-103">Modify meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="471c1-104">**Resumen:** Obtenga información sobre cómo modificar valores de configuración de Skype para Business Server 2015 de reunión.</span><span class="sxs-lookup"><span data-stu-id="471c1-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="471c1-105">Puede modificar valores de configuración de reunión utilizando Skype para Panel de Control de servidor empresarial o mediante Skype para el Shell de administración de servidor de Business.</span><span class="sxs-lookup"><span data-stu-id="471c1-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="471c1-106">Modificar valores de configuración de la reunión con Skype para Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="471c1-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="471c1-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="471c1-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="471c1-108">Abre Skype para Panel de Control del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="471c1-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="471c1-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="471c1-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="471c1-110">En la lista de configuraciones de la reunión, haga clic en la configuración que desee cambiar, luego, haga clic en **Editar** y, por último, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="471c1-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="471c1-111">En **Editar configuración de reunión**, modifique cualquiera de las opciones de configuración, excepto el nombre de la configuración, que no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="471c1-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="471c1-112">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="471c1-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="471c1-113">Modificar valores de configuración de la reunión con Skype para el Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="471c1-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="471c1-114">Para modificar las opciones de configuración de la reunión, use el cmdlet **Set-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="471c1-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="471c1-p101">El comando que se muestra en el siguiente ejemplo modifica las opciones de configuración de reunión asignadas al sitio Redmond (-Identity site:Redmond). En este caso, el valor de la propiedad DesignateAsPresenter es Everyone (todos):</span><span class="sxs-lookup"><span data-stu-id="471c1-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="471c1-117">Para obtener más información, incluida una lista completa de los parámetros, consulte [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="471c1-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

