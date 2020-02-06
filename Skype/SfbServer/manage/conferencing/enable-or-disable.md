---
title: Habilitar o deshabilitar las conferencias de acceso telefónico local en Skype empresarial Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Resumen: Aprenda a usar el panel de control o el shell de administración para habilitar o deshabilitar las conferencias de acceso telefónico local en Skype empresarial Server.'
ms.openlocfilehash: 8ce0fcfb4f785397075aa9d7b89b94eacb096167
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818561"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="2bef1-103">Habilitar o deshabilitar las conferencias de acceso telefónico local en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2bef1-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="2bef1-104">**Resumen:** Aprenda a usar el panel de control o el shell de administración para habilitar o deshabilitar las conferencias de acceso telefónico local en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2bef1-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="2bef1-105">Puede habilitar las conferencias de acceso telefónico local con el panel de control de Skype empresarial Server o mediante el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2bef1-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2bef1-106">Habilitar o deshabilitar las conferencias de acceso telefónico local con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2bef1-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2bef1-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="2bef1-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="2bef1-108">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="2bef1-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2bef1-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="2bef1-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="2bef1-110">En la lista de directivas de conferencia, seleccione la directiva para la que desea habilitar la conferencia de acceso telefónico local, haga clic en **Editar** y luego en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="2bef1-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="2bef1-p101">Para permitir que los usuarios se unan a la reunión con acceso telefónico local, active la casilla **Habilitar conferencia de acceso telefónico local por RTC**. De forma predeterminada, los usuarios pueden acceder telefónicamente a las reuniones con la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="2bef1-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="2bef1-113">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2bef1-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2bef1-114">Habilitar o deshabilitar las conferencias de acceso telefónico local con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="2bef1-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="2bef1-115">Para habilitar o deshabilitar las conferencias de acceso telefónico local, use el cmdlet **Set-CsConferencingPolicy** con el parámetro EnableDialInConferencing como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="2bef1-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="2bef1-116">Para obtener más información, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2bef1-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

