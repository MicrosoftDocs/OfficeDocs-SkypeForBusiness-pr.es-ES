---
title: 'Lync Server 2013: crear perfiles de directiva de ancho de banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3eef3ea6dfb349f0f712c1127adb8310d90c27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="98443-102">Crear perfiles de directiva de ancho de banda en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98443-102">Create bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98443-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="98443-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="98443-p101">Las *directivas de ancho de banda* definen limitaciones en el uso de ancho de banda para las modalidades de audio y vídeo en tiempo real. Las directivas de ancho de banda se aplican a los *perfiles de directiva de ancho de banda*, que pueden aplicarse a varios sitios de red para el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="98443-p101">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities. Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="98443-106">Para obtener instrucciones sobre qué límites de ancho de banda debe establecer en su implementación CAC, consulte [definir los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="98443-106">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="98443-107">Para obtener más información sobre cómo trabajar con directivas de ancho de banda y perfiles de Directiva, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="98443-107">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="98443-108">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="98443-108">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="98443-109">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="98443-109">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="98443-110">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="98443-110">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="98443-111">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="98443-111">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="98443-112">Las directivas de ejemplo creadas en el procedimiento siguiente definen límites para el tráfico de audio global, sesiones de audio individuales, el tráfico de vídeo global y sesiones de vídeo individuales.</span><span class="sxs-lookup"><span data-stu-id="98443-112">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="98443-113">Por ejemplo, el perfil\_de directiva de ancho de banda del vínculo de 5 MB establece los siguientes límites:</span><span class="sxs-lookup"><span data-stu-id="98443-113">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="98443-114">Límite de audio: 2.000 kbps</span><span class="sxs-lookup"><span data-stu-id="98443-114">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="98443-115">Límite de sesión de audio: 200 kbps</span><span class="sxs-lookup"><span data-stu-id="98443-115">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="98443-116">Límite de vídeo: 1.400 kbps</span><span class="sxs-lookup"><span data-stu-id="98443-116">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="98443-117">Límite de sesión de vídeo: 700 kbps</span><span class="sxs-lookup"><span data-stu-id="98443-117">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="98443-p103">El valor de Límite de sesión de audio es 40 kbps. El valor de Límite de sesión de vídeo es 100 kbps.</span><span class="sxs-lookup"><span data-stu-id="98443-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="98443-120">Para crear perfiles de directiva de ancho de banda mediante el shell de administración</span><span class="sxs-lookup"><span data-stu-id="98443-120">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="98443-121">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="98443-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="98443-122">Para cada perfil de directiva de ancho de banda que quiera crear, ejecute el cmdlet New-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="98443-122">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="98443-123">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="98443-123">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="98443-124">Para crear perfiles de directiva de ancho de banda mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="98443-124">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="98443-125">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98443-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="98443-126">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="98443-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="98443-127">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="98443-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="98443-128">Haga clic en el botón de navegación **Perfil de directiva**.</span><span class="sxs-lookup"><span data-stu-id="98443-128">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="98443-129">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="98443-129">Click **New**.</span></span>

5.  <span data-ttu-id="98443-130">En la página **Nuevo perfil de directiva**, haga clic en **Nombre** y escriba un nombre para el perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="98443-130">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="98443-131">Haga clic en **Límite de audio** y escriba el número máximo de kbps que se deben permitir para todas las sesiones de audio combinadas.</span><span class="sxs-lookup"><span data-stu-id="98443-131">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="98443-132">Haga clic en **Límite de sesión de audio** y escriba el número máximo de kbps que se deben permitir para cada sesión de audio.</span><span class="sxs-lookup"><span data-stu-id="98443-132">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="98443-133">Haga clic en **Límite de vídeo** y escriba el número máximo de kbps que se deben permitir para todas las sesiones de vídeo combinadas.</span><span class="sxs-lookup"><span data-stu-id="98443-133">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="98443-134">Haga clic en **Límite de sesión de vídeo** y escriba el número máximo de kbps que se deben permitir para cada sesión de vídeo.</span><span class="sxs-lookup"><span data-stu-id="98443-134">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="98443-135">Si lo desea, haga clic en **Descripción** y escriba información adicional para describir este perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="98443-135">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="98443-136">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="98443-136">Click **Commit**.</span></span>

12. <span data-ttu-id="98443-137">Para terminar de crear perfiles de directiva de ancho de banda para su topología, repita los pasos del 4 al 11 con la configuración para otros perfiles de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="98443-137">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

