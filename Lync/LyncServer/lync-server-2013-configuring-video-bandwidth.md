---
title: 'Lync Server 2013: configuración del ancho de banda de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ee374be85bc9427135ff89f3eb75acefd1cf5a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="9ca9f-102">Configuración del ancho de banda de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ca9f-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ca9f-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9ca9f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9ca9f-104">Lync Server 2013 incluye varias opciones de configuración para administrar el vídeo para las conferencias de dos participantes y las de varias partes.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="9ca9f-105">Al implementar Lync Server 2013, debe evaluar si la configuración predeterminada es adecuada para su organización y modificarla según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="9ca9f-106">Los parámetros descritos en esta sección se aplican tanto a llamadas de terceros como a conferencias de varias partes.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-106">The parameters described in this section apply to both two-party calls and multiparty conferencing.</span></span> <span data-ttu-id="9ca9f-107">Para ver o modificar esta configuración, use uno de los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="9ca9f-107">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="9ca9f-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="9ca9f-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="9ca9f-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="9ca9f-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="9ca9f-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="9ca9f-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="9ca9f-111">Compruebe la configuración siguiente en su Directiva de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="9ca9f-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="9ca9f-112">**VideoBitRateKb**   esta configuración especifica la tasa de bits de vídeo máxima en kilobits por segundo (kbps) usada para el vídeo enviado por un usuario.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="9ca9f-113">El valor predeterminado es 50000 kbps.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="9ca9f-114">Los valores válidos son de 0 a 50000.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="9ca9f-115">Esta configuración se aplica por separado al vídeo principal y al vídeo panorámico.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="9ca9f-116">Ejemplo: Si especifica 2000 Kbps, Lync Server puede enviar 2000 Kbps para la secuencia de vídeo principal y 2000 Kbps para la secuencia de vídeo panorámica.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9ca9f-117">El ancho de banda máximo de la red de vídeo para un extremo de Lync 2013 es de 8000 Kbps para el vídeo principal y 2500 Kbps para el vídeo panorámico.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="9ca9f-118">Estos valores máximos solo se alcanzan si se reciben o envían varios vídeos.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="9ca9f-119">Para obtener más información, vea la sección "uso de la red de tráfico de multimedia" en <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="9ca9f-120">Esta sección muestra el ancho de banda de vídeo máximo y típico de la secuencia de vídeo para todas las resoluciones compatibles.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="9ca9f-121">**TotalReceiveVideoBitRateKb**   esta configuración, que es nueva en Lync Server 2013, especifica la velocidad de bits máxima permitida (en kilobits por segundo) para todas las transmisiones de vídeo recibidas por un cliente.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="9ca9f-122">Es decir, especifica el total combinado de todas las transmisiones de vídeo, excepto las secuencias panorámicas de vídeo, que un cliente puede recibir.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="9ca9f-123">Por ejemplo, si especifica 1500 kbps, un cliente puede recibir hasta 1500 kbps de video, que puede constar de varias secuencias de vídeo o una única secuencia de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="9ca9f-124">Esta configuración se aplica solo a los clientes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="9ca9f-125">El valor predeterminado de **TotalReceiveVideoBitRateKb** es 50000 kbps.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-125">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps.</span></span> <span data-ttu-id="9ca9f-126">Si la configuración de **EnableMultiviewJoin** para la vista de galería se establece en verdadero, **TotalReceiveVideoBitRateKb** no debe ser inferior a 420 kbps.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-126">If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps.</span></span> <span data-ttu-id="9ca9f-127">Si la configuración de **EnableMultiviewJoin** para la vista de galería se establece en falso, **TotalReceiveVideoBitRateKb** no debe ser inferior a 100 kbps.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-127">If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps.</span></span> <span data-ttu-id="9ca9f-128">Si **EnableMultiviewJoin** se establece en true y establece el valor debajo de 420 Kbps, los valores se establecerán de forma predeterminada en el valor de umbral.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-128">If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value.</span></span> <span data-ttu-id="9ca9f-129">Este límite impide la configuración accidental accidental que podría dar lugar a una mala experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-129">This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9ca9f-130">Para obtener más información sobre la configuración de <STRONG>EnableMultiviewJoin</STRONG> , consulte <A href="lync-server-2013-configuring-gallery-view.md">configuración de la vista de galería en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="9ca9f-131">**MaxVideoConferencingResolution**   este parámetro ya no se usa para los clientes de Lync Server 2013 en conferencias de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="9ca9f-132">Las conferencias de Lync Server 2013 usan los controles de velocidad de bits descritos anteriormente en esta sección.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="9ca9f-133">Esta configuración se sigue usando para clientes heredados que se unan a una conferencia de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="9ca9f-134">Este parámetro determina la resolución máxima permitida para clientes heredados en conferencias organizadas por usuarios alojados en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="9ca9f-135">Es decir, los clientes heredados se tratan de la misma manera que en versiones anteriores de Lync Server u Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="9ca9f-136">Además de la configuración de directiva de conferencia que se aplica a los usuarios, evalúe la configuración de los medios.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-136">In addition to conferencing policy settings that apply to users, evaluate media configuration settings.</span></span> <span data-ttu-id="9ca9f-137">Para ver o modificar esta configuración, use uno de los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="9ca9f-137">View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="9ca9f-138">**Get-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="9ca9f-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="9ca9f-139">**Set-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="9ca9f-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="9ca9f-140">**Nuevo: CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="9ca9f-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="9ca9f-141">Compruebe la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ca9f-141">Verify the following setting:</span></span>

  - <span data-ttu-id="9ca9f-142">**MaxVideoRateAllowed**   esta configuración por agrupación especifica la tasa máxima a la que se transfieren las señales de video en los puntos de conexión de cliente.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="9ca9f-143">Solo se aplica a las versiones anteriores de clientes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9ca9f-144">Los clientes de Lync Server 2013 ignoran esta configuración y usan en su lugar la configuración TotalReceiveVideoBitRateKb en la Directiva de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="9ca9f-145">El valor predeterminado es HD720P.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-145">The default value is HD720P.</span></span> <span data-ttu-id="9ca9f-146">Los valores válidos son HD720p15M, VGA600K y CIF250K.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-146">Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="9ca9f-147">Ejemplo: Si especifica 1500 kbps, todos los clientes heredados del grupo pueden recibir hasta 1500 kbps de video en conferencias de dos o varias partes.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="9ca9f-148">Los procedimientos siguientes son ejemplos de uso del shell de administración de Lync Server para modificar la configuración que se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="9ca9f-149">Para modificar la Directiva de conferencia para la configuración de vídeo</span><span class="sxs-lookup"><span data-stu-id="9ca9f-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="9ca9f-150">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9ca9f-151">En la línea de comandos, ejecute el cmdlet siguiente para editar la Directiva de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="9ca9f-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="9ca9f-152">Para modificar la configuración de medios de clientes heredados</span><span class="sxs-lookup"><span data-stu-id="9ca9f-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="9ca9f-153">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9ca9f-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9ca9f-154">En la línea de comandos, ejecute el cmdlet siguiente para editar la configuración de multimedia:</span><span class="sxs-lookup"><span data-stu-id="9ca9f-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

