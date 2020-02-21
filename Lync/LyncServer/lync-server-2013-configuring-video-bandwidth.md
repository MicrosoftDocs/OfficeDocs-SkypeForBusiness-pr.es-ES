---
title: 'Lync Server 2013: configuración del ancho de banda de vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8995f47ff1059921c324d71cbaca26fa47c50ca0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a><span data-ttu-id="7b1c8-102">Configuración del ancho de banda de vídeo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b1c8-102">Configuring video bandwidth in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b1c8-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7b1c8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7b1c8-104">Lync Server 2013 incluye varias configuraciones para administrar el vídeo para llamadas de dos participantes y conferencias con varios participantes.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-104">Lync Server 2013 includes several settings for managing video for two-party calls and multiparty conferences.</span></span> <span data-ttu-id="7b1c8-105">Al implementar Lync Server 2013, debe evaluar si la configuración predeterminada es adecuada para su organización y modificarla según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-105">When you deploy Lync Server 2013, you should evaluate whether the default settings are appropriate for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="7b1c8-p102">Los parámetros descritos en esta sección se aplican a las llamadas entre dos entidades y a las conferencia entre varias entidades. Vea o modifique estos parámetros con uno de los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b1c8-p102">The parameters described in this section apply to both two-party calls and multiparty conferencing. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="7b1c8-108">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="7b1c8-108">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="7b1c8-109">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="7b1c8-109">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="7b1c8-110">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="7b1c8-110">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="7b1c8-111">Compruebe los siguientes parámetros en la directiva de conferencias:</span><span class="sxs-lookup"><span data-stu-id="7b1c8-111">Verify the following settings in your conferencing policy:</span></span>

  - <span data-ttu-id="7b1c8-112">**VideoBitRateKb**   esta configuración especifica la velocidad de bits de vídeo máxima en kilobits por segundo (kbps) que se usa para el vídeo enviado por un usuario.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-112">**VideoBitRateKb**   This setting specifies the maximum video bit rate in kilobits per second (kbps) used for video sent by a user.</span></span> <span data-ttu-id="7b1c8-113">El valor predeterminado es 50.000 kbps.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-113">The default value is 50000 kbps.</span></span> <span data-ttu-id="7b1c8-114">Los valores válidos son 0 a 50.000.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-114">Valid values are 0 to 50000.</span></span>
    
    <span data-ttu-id="7b1c8-115">Este parámetro se aplica por separado al vídeo principal y al vídeo panorámico.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-115">This setting applies separately to main video and panoramic video.</span></span>
    
    <span data-ttu-id="7b1c8-116">Ejemplo: Si especifica 2000 Kbps, Lync Server puede enviar 2000 Kbps para la secuencia de vídeo principal y 2000 Kbps para la secuencia de vídeo panorámico.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-116">Example: if you specify 2000 kbps, then Lync Server can send 2000 kbps for the main video stream and 2000 kbps for the panoramic video stream.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b1c8-117">El ancho de banda de red de vídeo máximo para un punto de conexión 2013 de Lync es de 8000 Kbps para el vídeo principal y 2500 Kbps para vídeo panorámico.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-117">The maximum video network bandwidth for a Lync 2013 endpoint is 8000 kbps for the main video and 2500 kbps for panoramic video.</span></span> <span data-ttu-id="7b1c8-118">Estos valores máximos solo se alcanzan si se reciben o envían varios vídeos.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-118">These maximum values are reached only if multiple videos are received or sent.</span></span> <span data-ttu-id="7b1c8-119">Para obtener más información, consulte la sección "uso de la red de tráfico de medios" en <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-119">For details, see the "Media Traffic Network Usage" section in <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Network bandwidth requirements for media traffic in Lync Server 2013</A>.</span></span> <span data-ttu-id="7b1c8-120">Esta sección muestra el ancho de banda máximo y típico para secuencias de vídeo en todas las resoluciones compatibles.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-120">This section lists the maximum and typical video stream bandwidth for all supported resolutions.</span></span>

    
    </div>

  - <span data-ttu-id="7b1c8-121">**TotalReceiveVideoBitRateKb**   esta configuración, que es nueva en Lync Server 2013, especifica la velocidad de bits máxima permitida (en kilobits por segundo) para todas las secuencias de vídeo recibidas por un cliente.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-121">**TotalReceiveVideoBitRateKb**   This setting, which is new in Lync Server 2013, specifies the maximum allowed bitrate (in kilobits per second) for all the video streams received by a client.</span></span> <span data-ttu-id="7b1c8-122">Es decir, especifica el total combinado de todas las secuencias de vídeo, excepto las secuencias de vídeo panorámico, que puede recibir un cliente.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-122">That is, it specifies the combined total for all the video streams, except for panoramic video streams, that a client can receive.</span></span> <span data-ttu-id="7b1c8-123">Por ejemplo, si especifica 1.500 kbps, un cliente puede recibir hasta 1.500 kbps de vídeo, que puede componerse de varias secuencias de vídeo o una secuencia de vídeo única.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-123">For example, if you specify 1500 kbps, then a client can receive up to 1500 kbps of video, which may consist of multiple video streams or a single video stream.</span></span> <span data-ttu-id="7b1c8-124">Esta configuración solo se aplica a clientes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-124">This setting applies only to Lync Server 2013 clients.</span></span>
    
    <span data-ttu-id="7b1c8-p106">El valor predeterminado para **TotalReceiveVideoBitRateKb** es 50.000 kbps. Si el parámetro **EnableMultiviewJoin** para Vista Galería se establece en True, **TotalReceiveVideoBitRateKb** no debe establecer por debajo de 420 kbps. Si el parámetro **EnableMultiviewJoin** para Vista Galería se establece en False, **TotalReceiveVideoBitRateKb** no debe establecerse por debajo de 100 kbps. Si **EnableMultiviewJoin** se establece en True y establece el valor por debajo de 420 kbps, los valores serán el valor del umbral de forma predeterminada. Este umbral ayuda a evitar errores accidentales que podrían resultar en una experiencia de usuario deficiente.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-p106">The default value for **TotalReceiveVideoBitRateKb** is 50000 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to True, **TotalReceiveVideoBitRateKb** must not be set below 420 kbps. If the **EnableMultiviewJoin** setting for Gallery View is set to False, **TotalReceiveVideoBitRateKb** must not be set below 100 kbps. If **EnableMultiviewJoin** is set to True and you set the value below 420 kbps, the values will default to the threshold value. This threshold helps prevent accidental misconfiguration that might result in poor user experience.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b1c8-130">Para obtener más información sobre la configuración de <STRONG>EnableMultiviewJoin</STRONG> , consulte <A href="lync-server-2013-configuring-gallery-view.md">configuración de la vista de galería en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-130">For details about the <STRONG>EnableMultiviewJoin</STRONG> setting, see <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="7b1c8-131">**MaxVideoConferencingResolution**   este parámetro ya no se usa en clientes de Lync Server 2013 en conferencias de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-131">**MaxVideoConferencingResolution**   This parameter is no longer used for Lync Server 2013 clients in Lync Server 2013 conferences.</span></span> <span data-ttu-id="7b1c8-132">Las conferencias de Lync Server 2013 usan los controles de velocidad de bits descritos anteriormente en esta sección.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-132">Lync Server 2013 conferences use the bit rate controls described earlier in this section.</span></span> <span data-ttu-id="7b1c8-133">Esta configuración se sigue usando para clientes heredados que se unan a una conferencia de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-133">This setting is still used for legacy clients joining a Lync Server 2013 conference.</span></span> <span data-ttu-id="7b1c8-134">Este parámetro determina la resolución máxima permitida para los clientes heredados en conferencias organizadas por usuarios hospedados en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-134">This parameter determines the maximum resolution allowed for legacy clients in conferences organized by users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="7b1c8-135">Es decir, los clientes heredados se tratan de la misma forma que en versiones anteriores de Lync Server u Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-135">That is, legacy clients are treated the same as they were in previous versions of Lync Server or Office Communications Server.</span></span>

<span data-ttu-id="7b1c8-p108">Además de los parámetros de la directiva de conferencias que se aplican a los usuarios, evalúe los parámetros de configuración de los medios. Vea o modifique estos parámetros con uno de los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b1c8-p108">In addition to conferencing policy settings that apply to users, evaluate media configuration settings. View or modify these settings by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="7b1c8-138">**Get-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="7b1c8-138">**Get-CsMediaConfiguration**</span></span>

  - <span data-ttu-id="7b1c8-139">**Set-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="7b1c8-139">**Set- CsMediaConfiguration**</span></span>

  - <span data-ttu-id="7b1c8-140">**New-CsMediaConfiguration**</span><span class="sxs-lookup"><span data-stu-id="7b1c8-140">**New- CsMediaConfiguration**</span></span>

<span data-ttu-id="7b1c8-141">Compruebe la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="7b1c8-141">Verify the following setting:</span></span>

  - <span data-ttu-id="7b1c8-142">**MaxVideoRateAllowed**   esta configuración por grupo especifica la velocidad máxima a la que se transferirán las señales de vídeo en los extremos de cliente.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-142">**MaxVideoRateAllowed**   This per-pool setting specifies the maximum rate at which video signals will be transferred at the client endpoints.</span></span> <span data-ttu-id="7b1c8-143">Solo se aplica a las versiones anteriores de clientes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-143">It applies only to previous versions of Lync Server clients.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b1c8-144">Los clientes de Lync Server 2013 ignoran esta configuración y usan el valor TotalReceiveVideoBitRateKb en la Directiva de conferencia en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-144">Lync Server 2013 clients ignore this setting and use the TotalReceiveVideoBitRateKb setting in conferencing policy instead.</span></span>

    
    </div>
    
    <span data-ttu-id="7b1c8-p110">El valor predeterminado es HD720P. Los valores válidos son HD720p15M, VGA600K y CIF250K.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-p110">The default value is HD720P. Valid values are HD720p15M, VGA600K, and CIF250K.</span></span>
    
    <span data-ttu-id="7b1c8-147">Por ejemplo: si especifica 1.500 kbps, todos los clientes heredados del grupo pueden recibir hasta 1.500 kbps de vídeo en conferencias entre dos o entre varias entidades.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-147">Example: If you specify 1500 kbps, then all the legacy clients in the pool can receive up to 1500 kbps of video in two-party or multiparty conferences.</span></span>

<span data-ttu-id="7b1c8-148">Los siguientes procedimientos son ejemplos del uso del shell de administración de Lync Server para modificar la configuración que se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-148">The following procedures are examples of using Lync Server Management Shell to modify the settings described in this section.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a><span data-ttu-id="7b1c8-149">Para modificar la directiva de conferencias para la configuración de vídeo</span><span class="sxs-lookup"><span data-stu-id="7b1c8-149">To modify conferencing policy for video settings</span></span>

1.  <span data-ttu-id="7b1c8-150">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-150">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7b1c8-151">En la línea de comandos, ejecute el cmdlet siguiente para cambiar la directiva de conferencia:</span><span class="sxs-lookup"><span data-stu-id="7b1c8-151">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a><span data-ttu-id="7b1c8-152">Para modificar la configuración de medios para los clientes heredados</span><span class="sxs-lookup"><span data-stu-id="7b1c8-152">To modify media configuration for legacy clients</span></span>

1.  <span data-ttu-id="7b1c8-153">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7b1c8-154">En la línea de comandos, ejecute el cmdlet siguiente para cambiar la configuración de medios:</span><span class="sxs-lookup"><span data-stu-id="7b1c8-154">At the command line, run the following cmdlet to edit the media configuration:</span></span>
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

