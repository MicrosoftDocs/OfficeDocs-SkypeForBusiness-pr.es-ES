---
title: Habilitar estacionamiento de llamadas para los usuarios de Skype para la empresa
ms.author: kenwith
author: kenwith
manager: serdars
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
ms.openlocfilehash: 44e72cab776b08cbd0290bb15010d36d370d86b3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968226"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="e1dcc-103">Habilitar estacionamiento de llamadas para los usuarios de Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="e1dcc-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="e1dcc-104">Habilitar a los usuarios para el estacionamiento de llamadas en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="e1dcc-105">De forma predeterminada, el estacionamiento de llamadas está deshabilitado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="e1dcc-106">Los usuarios no se pueden estacionar llamadas ni recuperar llamadas estacionadas mientras estén habilitados para estacionamiento de llamadas en la directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="e1dcc-107">Puede habilitar estacionamiento de llamadas en el ámbito global o en el ámbito de sitio o el ámbito de usuario.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="e1dcc-108">El ámbito de usuario tiene prioridad sobre el ámbito de sitio y el ámbito de sitio tiene prioridad sobre el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="e1dcc-109">Si tiene varias directivas de voz, revise todas las directivas para habilitar estacionamiento de llamadas, no sólo la directiva global.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="e1dcc-110">Usar Skype para el Panel de Control de servidor empresarial para habilitar estacionamiento de llamadas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="e1dcc-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="e1dcc-111">Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins** o bien como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="e1dcc-112">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e1dcc-113">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="e1dcc-114">Haga clic en la pestaña **Directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="e1dcc-115">Haga doble clic en una directiva de voz existente para abrir el cuadro de diálogo **Editar directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="e1dcc-116">En **Características de llamada**, seleccione **Habilitar estacionamiento de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="e1dcc-117">Haga clic en **Aceptar** para guardar la directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="e1dcc-118">Para usar Cmdlets para habilitar estacionamiento de llamadas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="e1dcc-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="e1dcc-119">Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro del rol administrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="e1dcc-120">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="e1dcc-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e1dcc-121">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="e1dcc-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="e1dcc-122">Por ejemplo, para habilitar estacionamiento de llamadas para la directiva de voz global predeterminada:</span><span class="sxs-lookup"><span data-stu-id="e1dcc-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="e1dcc-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1dcc-123">See also</span></span>



[<span data-ttu-id="e1dcc-124">Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para la empresa</span><span class="sxs-lookup"><span data-stu-id="e1dcc-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

