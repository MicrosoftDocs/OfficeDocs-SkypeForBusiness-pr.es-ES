---
title: Habilitar o deshabilitar conferencias de acceso telefónico local en Skype Empresarial Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Summary: Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.'
ms.openlocfilehash: ade7753f480856d68535daadda40eac6296a5d6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119469"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="ae923-103">Habilitar o deshabilitar conferencias de acceso telefónico local en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ae923-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="ae923-104">**Resumen:** Obtenga información sobre cómo usar el Panel de control o el Shell de administración para habilitar o deshabilitar las conferencias de acceso telefónico local en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae923-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="ae923-105">Puede habilitar las conferencias de acceso telefónico local mediante el Panel de control de Skype Empresarial Server o mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae923-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ae923-106">Habilitar o deshabilitar conferencias de acceso telefónico local mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ae923-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ae923-107">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ae923-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ae923-108">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae923-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ae923-109">En la barra de navegación izquierda, haga clic **en Conferencia** y, a continuación, haga clic en Directiva **de conferencia.**</span><span class="sxs-lookup"><span data-stu-id="ae923-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="ae923-110">En la lista de directivas de conferencia, seleccione la directiva para la que desea habilitar la conferencia con acceso telefónico, haga clic en **Editar** y luego en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="ae923-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="ae923-p101">Para permitir que los usuarios se unan a la reunión con acceso telefónico, active la casilla **Habilitar conferencia de acceso telefónico local por RTC**. De forma predeterminada, los usuarios pueden acceder telefónicamente a las reuniones mediante la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="ae923-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="ae923-113">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ae923-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ae923-114">Habilitar o deshabilitar conferencias de acceso telefónico local mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ae923-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ae923-115">Para habilitar o deshabilitar las conferencias de acceso telefónico local, use el cmdlet **Set-CsConferencingPolicy** con el parámetro EnableDialInConferencing de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ae923-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="ae923-116">Para obtener más información, [vea Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ae923-116">For more information, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
