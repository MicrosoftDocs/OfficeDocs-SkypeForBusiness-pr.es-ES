---
title: Crear perfiles de directivas de ancho de banda en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Crear o modificar directivas de ancho de banda, que se usan por el control de admisión de llamadas de Enterprise Voice en Skype para Business Server.
ms.openlocfilehash: 51516e07a75cc4239d89310c9d33194a225b3a02
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500593"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server-2015"></a><span data-ttu-id="06977-103">Crear perfiles de directivas de ancho de banda en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="06977-103">Create bandwidth policy profiles in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="06977-104">Crear o modificar directivas de ancho de banda, que se usan por el control de admisión de llamadas de Enterprise Voice en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="06977-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="06977-105">Las directivas de ancho de banda definen las limitaciones de uso de ancho de banda para modalidades de vídeo y de audio en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="06977-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="06977-106">Las directivas de ancho de banda son perfiles de directiva aplicada tobandwidth, que se pueden aplicar a varios sitios de red para el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="06977-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="06977-107">Para obtener instrucciones sobre los límites de ancho de banda de qué se debe definir en su implementación de CAC, consulte [Plan para el control de admisión de llamadas en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="06977-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="06977-p102">Las directivas de ejemplo creadas en el procedimiento siguiente definen límites para el tráfico de audio global, sesiones de audio individuales, el tráfico de vídeo global y sesiones de vídeo individuales. Por ejemplo, el perfil de directiva de ancho de banda 5Mb_Link define los límites siguientes:</span><span class="sxs-lookup"><span data-stu-id="06977-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="06977-110">Límite de audio: 2.000 kbps</span><span class="sxs-lookup"><span data-stu-id="06977-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="06977-111">Límite de sesión de audio: 200 kbps</span><span class="sxs-lookup"><span data-stu-id="06977-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="06977-112">Límite de vídeo: 1.400 kbps</span><span class="sxs-lookup"><span data-stu-id="06977-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="06977-113">Límite de sesión de vídeo: 700 kbps</span><span class="sxs-lookup"><span data-stu-id="06977-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="06977-p103">El valor de Límite de sesión de audio es 40 kbps. El valor de Límite de sesión de vídeo es 100 kbps.</span><span class="sxs-lookup"><span data-stu-id="06977-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="06977-116">Para crear perfiles de directiva de ancho de banda mediante Skype de consola de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="06977-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="06977-117">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="06977-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="06977-p104">Para cada perfil de directiva de ancho de banda que quiera crear, ejecute el cmdlet New-CsNetworkBandwidthPolicyProfile. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="06977-p104">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet. For example, run:</span></span>
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="06977-120">Para crear perfiles de directiva de ancho de banda mediante Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="06977-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="06977-121">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="06977-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="06977-122">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="06977-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="06977-123">Haga clic en el botón de navegación **Perfil de directiva**.</span><span class="sxs-lookup"><span data-stu-id="06977-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="06977-124">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="06977-124">Click **New**.</span></span>
    
5. <span data-ttu-id="06977-125">En la página **Nuevo perfil de directiva**, haga clic en **Nombre** y escriba un nombre para el perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="06977-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="06977-126">Haga clic en **Límite de audio** y escriba el número máximo de kbps que se deben permitir para todas las sesiones de audio combinadas.</span><span class="sxs-lookup"><span data-stu-id="06977-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="06977-127">Haga clic en **Límite de sesión de audio** y escriba el número máximo de kbps que se deben permitir para cada sesión de audio.</span><span class="sxs-lookup"><span data-stu-id="06977-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="06977-128">Haga clic en **Límite de vídeo** y escriba el número máximo de kbps que se deben permitir para todas las sesiones de vídeo combinadas.</span><span class="sxs-lookup"><span data-stu-id="06977-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="06977-129">Haga clic en **Límite de sesión de vídeo** y escriba el número máximo de kbps que se deben permitir para cada sesión de vídeo.</span><span class="sxs-lookup"><span data-stu-id="06977-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="06977-130">Si lo desea, haga clic en **Descripción** y escriba información adicional para describir este perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="06977-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="06977-131">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="06977-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="06977-132">Para terminar de crear perfiles de directiva de ancho de banda para su topología, repita los pasos del 4 al 11 con la configuración para otros perfiles de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="06977-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="06977-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="06977-133">See also</span></span>

[<span data-ttu-id="06977-134">Nueva CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="06977-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="06977-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="06977-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="06977-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="06977-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="06977-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="06977-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)