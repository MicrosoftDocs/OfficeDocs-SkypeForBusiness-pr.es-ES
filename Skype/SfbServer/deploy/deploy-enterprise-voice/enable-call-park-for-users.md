---
title: Habilitar el estacionamiento de llamadas para los usuarios de Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilite a los usuarios para el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830960"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="80862-103">Habilitar el estacionamiento de llamadas para los usuarios de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="80862-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="80862-104">Habilite a los usuarios para el estacionamiento de llamadas en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="80862-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="80862-105">De forma predeterminada, el estacionamiento de llamadas está deshabilitado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="80862-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="80862-106">Los usuarios no pueden estacionar llamadas ni recuperar llamadas estacionadas hasta que estén habilitados para el estacionamiento de llamadas en la directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="80862-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="80862-107">Puede habilitar el estacionamiento de llamadas en el ámbito global, en el ámbito de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="80862-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="80862-108">El ámbito de usuario tiene prioridad sobre el ámbito de sitio y el ámbito de sitio tiene prioridad sobre el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="80862-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="80862-109">Si tiene varias directivas de voz, revise todas las directivas para habilitar el estacionamiento de llamadas, no solo la directiva global.</span><span class="sxs-lookup"><span data-stu-id="80862-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="80862-110">Para usar el Panel de control de Skype Empresarial Server para habilitar el estacionamiento de llamadas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="80862-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="80862-111">Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins**, o bien como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="80862-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="80862-112">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="80862-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="80862-113">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="80862-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="80862-114">Haga clic en la pestaña **Directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="80862-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="80862-115">Haga doble clic en una directiva de voz existente para abrir el cuadro de diálogo **Editar directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="80862-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="80862-116">En **Características de llamada**, seleccione **Habilitar Estacionamiento de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="80862-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="80862-117">Haga clic en **Aceptar** para guardar la directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="80862-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="80862-118">Para usar cmdlets para habilitar el estacionamiento de llamadas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="80862-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="80862-119">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol administrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="80862-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="80862-120">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="80862-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="80862-121">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="80862-121">Run:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="80862-122">Por ejemplo, para habilitar el estacionamiento de llamadas para la directiva de voz global predeterminada:</span><span class="sxs-lookup"><span data-stu-id="80862-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="80862-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="80862-123">See also</span></span>



[<span data-ttu-id="80862-124">Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="80862-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

