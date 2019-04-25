---
title: Habilitar o deshabilitar conferencias en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Resumen: Obtenga información sobre cómo usar el Panel de Control o el Shell de administración para habilitar o deshabilitar conferencias en Skype para Business Server.'
ms.openlocfilehash: 216973e8d3a887dcae308fc5efa6d67b2415493b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222831"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="150b3-103">Habilitar o deshabilitar conferencias en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="150b3-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="150b3-104">**Resumen:** Obtenga información sobre cómo usar el Panel de Control o el Shell de administración para habilitar o deshabilitar conferencias en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="150b3-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="150b3-105">Puede habilitar la conferencia de acceso telefónico mediante el uso de Skype para el Panel de Control de servidor empresarial o mediante el uso de Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="150b3-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="150b3-106">Habilitar o deshabilitar la conferencia de acceso telefónico mediante el uso de Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="150b3-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="150b3-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="150b3-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="150b3-108">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="150b3-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="150b3-109">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Directiva de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="150b3-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="150b3-110">En la lista de directivas de conferencia, seleccione la directiva para la que desea habilitar la conferencia de acceso telefónico local, haga clic en **Editar** y luego en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="150b3-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="150b3-p101">Para permitir que los usuarios se unan a la reunión con acceso telefónico local, active la casilla **Habilitar conferencia de acceso telefónico local por RTC**. De forma predeterminada, los usuarios pueden acceder telefónicamente a las reuniones con la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="150b3-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="150b3-113">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="150b3-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="150b3-114">Habilitar o deshabilitar la conferencia de acceso telefónico mediante el uso de Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="150b3-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="150b3-115">Para habilitar o deshabilitar las conferencias de acceso telefónico local, use el cmdlet **Set-CsConferencingPolicy** con el parámetro EnableDialInConferencing como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="150b3-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="150b3-116">Para obtener más información, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="150b3-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

