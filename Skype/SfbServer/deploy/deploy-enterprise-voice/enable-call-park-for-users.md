---
title: Habilitar el estacionamiento de llamadas para los usuarios en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilitar a los usuarios para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: b93a9393a095a4860bfd8f392f95d834dad6fa71
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="enable-call-park-for-users-in-skype-for-business-2015"></a><span data-ttu-id="087b5-103">Habilitar el estacionamiento de llamadas para los usuarios en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="087b5-103">Enable Call Park for users in Skype for Business 2015</span></span>
 
<span data-ttu-id="087b5-104">Habilitar a los usuarios para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="087b5-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="087b5-105">De forma predeterminada, el estacionamiento de llamadas está deshabilitado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="087b5-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="087b5-106">Los usuarios no se pueden estacionar llamadas ni recuperar llamadas estacionadas mientras estén habilitados para estacionamiento de llamadas en la directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="087b5-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="087b5-107">Puede habilitar estacionamiento de llamadas en el ámbito global o en el ámbito de sitio o el ámbito de usuario.</span><span class="sxs-lookup"><span data-stu-id="087b5-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="087b5-108">El ámbito de usuario tiene prioridad sobre el ámbito de sitio y el ámbito de sitio tiene prioridad sobre el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="087b5-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="087b5-109">Si tiene varias directivas de voz, revise todas las directivas para habilitar estacionamiento de llamadas, no sólo la directiva global.</span><span class="sxs-lookup"><span data-stu-id="087b5-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="087b5-110">Usar Skype para el Panel de Control de servidor empresarial para habilitar estacionamiento de llamadas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="087b5-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="087b5-111">Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins** o bien como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="087b5-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="087b5-112">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="087b5-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="087b5-113">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="087b5-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="087b5-114">Haga clic en la pestaña **Directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="087b5-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="087b5-115">Haga doble clic en una directiva de voz existente para abrir el cuadro de diálogo **Editar directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="087b5-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="087b5-116">En **Características de llamada**, seleccione **Habilitar estacionamiento de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="087b5-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="087b5-117">Haga clic en **Aceptar** para guardar la directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="087b5-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="087b5-118">Para usar Cmdlets para habilitar estacionamiento de llamadas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="087b5-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="087b5-119">Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro del rol administrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="087b5-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="087b5-120">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="087b5-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="087b5-121">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="087b5-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="087b5-122">Por ejemplo, para habilitar estacionamiento de llamadas para la directiva de voz global predeterminada:</span><span class="sxs-lookup"><span data-stu-id="087b5-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="087b5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="087b5-123">See also</span></span>

#### 

[<span data-ttu-id="087b5-124">Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para profesionales de 2015</span><span class="sxs-lookup"><span data-stu-id="087b5-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)

