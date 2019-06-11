---
title: 'Lync Server 2013: Tabla MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="f5079-102">Tabla MediaLine en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5079-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5079-103">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="f5079-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="f5079-104">Cada registro representa una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="f5079-104">Each record represents one media line.</span></span> <span data-ttu-id="f5079-105">(Una sesión de audio normalmente contiene una línea multimedia de audio.</span><span class="sxs-lookup"><span data-stu-id="f5079-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="f5079-106">Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medio de audio y una línea de medio de vídeo, aunque la sesión podría contener dos líneas de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="f5079-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5079-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f5079-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f5079-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f5079-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5079-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f5079-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f5079-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f5079-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5079-114">Se hace referencia a ellos desde la <a href="lync-server-2013-session-table.md">tabla sesión en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-116">int</span><span class="sxs-lookup"><span data-stu-id="f5079-116">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-117">Primary</span><span class="sxs-lookup"><span data-stu-id="f5079-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5079-118">Se hace referencia a ellos desde la <a href="lync-server-2013-session-table.md">tabla sesión en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5079-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f5079-121">Primary</span><span class="sxs-lookup"><span data-stu-id="f5079-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5079-122">0 es el audio principal, 1 es el vídeo principal y 2 es vídeo panorámico, 3 es uso compartido de aplicaciones y escritorio.</span><span class="sxs-lookup"><span data-stu-id="f5079-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="f5079-123">Esta etiqueta debe ser única dentro de una sola sesión.</span><span class="sxs-lookup"><span data-stu-id="f5079-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5079-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-126">Esta columna está presente pero no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5079-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f5079-127">La información sobre la conectividad usada para una línea de medios se captura en las columnas CallerConnectivityICE y CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="f5079-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-129">int</span><span class="sxs-lookup"><span data-stu-id="f5079-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-130">Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits.</span><span class="sxs-lookup"><span data-stu-id="f5079-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="f5079-131">Para obtener más información, consulte la <em>especificación de protocolo de servidor calidad de la supervisión</em>, disponible para descargar.</span><span class="sxs-lookup"><span data-stu-id="f5079-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-133">int</span><span class="sxs-lookup"><span data-stu-id="f5079-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-134">Igual que CallerIceWarningFlags, pero en el lado del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="f5079-135">Para obtener más información, consulte la <em>especificación de protocolo de servidor calidad de la supervisión</em>, disponible para descargar.</span><span class="sxs-lookup"><span data-stu-id="f5079-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-136"><strong>Seguridad</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5079-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-138">Perfil de seguridad en uso.</span><span class="sxs-lookup"><span data-stu-id="f5079-138">The security profile in use.</span></span> <span data-ttu-id="f5079-139">0 es ninguno, 1 es SRTP, 2 es v1.</span><span class="sxs-lookup"><span data-stu-id="f5079-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5079-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-142">0 es UDP, 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="f5079-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-144">int</span><span class="sxs-lookup"><span data-stu-id="f5079-144">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-145">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-146">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-146">IP Address of the caller.</span></span> <span data-ttu-id="f5079-147">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5079-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-149">int</span><span class="sxs-lookup"><span data-stu-id="f5079-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-150">Puerto usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-152">int</span><span class="sxs-lookup"><span data-stu-id="f5079-152">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-153"> Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-154">La subred de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="f5079-154">The subnet of the caller.</span></span> <span data-ttu-id="f5079-155">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5079-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-157">bit</span><span class="sxs-lookup"><span data-stu-id="f5079-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-158">1 significa que la persona que llama está dentro de la red de la empresa, 0 significa que la persona que llama está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="f5079-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-160">int</span><span class="sxs-lookup"><span data-stu-id="f5079-160">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-161">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-162">Dirección Mac de la persona que llama, a la que se hace referencia desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-164">int</span><span class="sxs-lookup"><span data-stu-id="f5079-164">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-165">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-166">Dirección IP del servicio perimetral de Lync Server A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="f5079-167">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5079-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-169">int</span><span class="sxs-lookup"><span data-stu-id="f5079-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-170">Puerto usado en el servicio de borde de A/V por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-172">int</span><span class="sxs-lookup"><span data-stu-id="f5079-172">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-173">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-174">Dispositivo de captura usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-174">Capture device used by the caller.</span></span> <span data-ttu-id="f5079-175">Se hace referencia a ellos desde la <a href="lync-server-2013-device-table.md">tabla de dispositivos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-177">int</span><span class="sxs-lookup"><span data-stu-id="f5079-177">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-178">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-179">Dispositivo de representación usado por la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="f5079-179">Render device used by caller.</span></span> <span data-ttu-id="f5079-180">Se hace referencia a ellos desde la <a href="lync-server-2013-device-table.md">tabla de dispositivos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-182">int</span><span class="sxs-lookup"><span data-stu-id="f5079-182">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-183">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-184">Controlador para el dispositivo de captura de la persona que llama, al que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-186">int</span><span class="sxs-lookup"><span data-stu-id="f5079-186">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-187">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-188">Controlador del dispositivo de representación de la persona que llama, al que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5079-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f5079-191">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-192">Indica cómo se conectó a la red.</span><span class="sxs-lookup"><span data-stu-id="f5079-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="f5079-193">Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="f5079-194">Los valores típicos son 0 para una conexión cableada ' 1 para una conexión WiFi; y 3 para una conexión Ethernet.</span><span class="sxs-lookup"><span data-stu-id="f5079-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-196">int</span><span class="sxs-lookup"><span data-stu-id="f5079-196">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-197">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-198">BSSID del autor de la llamada si se usa una conexión inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="f5079-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="f5079-199">Se hace referencia desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-201">bit</span><span class="sxs-lookup"><span data-stu-id="f5079-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5079-202">Vínculo de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="f5079-202">The caller's link.</span></span> <span data-ttu-id="f5079-203">1 es una red privada virtual (VPN) y 0 no es una VPN.</span><span class="sxs-lookup"><span data-stu-id="f5079-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-205">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="f5079-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5079-206">La velocidad del vínculo de red, en bps, para el punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-208">int</span><span class="sxs-lookup"><span data-stu-id="f5079-208">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-209">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-210">Dirección IP del receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-210">IP Address of the call receiver.</span></span> <span data-ttu-id="f5079-211">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5079-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-213">bit</span><span class="sxs-lookup"><span data-stu-id="f5079-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5079-214">Puerto usado por el receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-216">int</span><span class="sxs-lookup"><span data-stu-id="f5079-216">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-217">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-218">Subred del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-218">Subnet of callee.</span></span> <span data-ttu-id="f5079-219">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5079-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-221">bit</span><span class="sxs-lookup"><span data-stu-id="f5079-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-222">1 significa que el receptor de llamadas está dentro de la red empresarial, 0 significa que el receptor de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="f5079-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-224">int</span><span class="sxs-lookup"><span data-stu-id="f5079-224">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-225">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-226">Dirección Mac de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-226">Callee Mac address.</span></span> <span data-ttu-id="f5079-227">Se hace referencia a ellos desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-229">int</span><span class="sxs-lookup"><span data-stu-id="f5079-229">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-230">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-231">Dirección IP del servicio perimetral A/V que usa el receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="f5079-232">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f5079-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-234">int</span><span class="sxs-lookup"><span data-stu-id="f5079-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-235">Puerto usado en el servicio de borde A/V por el receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-237">int</span><span class="sxs-lookup"><span data-stu-id="f5079-237">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-238">extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-239">Dispositivo de captura usado por el receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="f5079-240">Se hace referencia a ellos desde la <a href="lync-server-2013-device-table.md">tabla de dispositivos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-242">int</span><span class="sxs-lookup"><span data-stu-id="f5079-242">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-243">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-244">Dispositivo de representación usado por el receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-244">Render device used by the call receiver.</span></span> <span data-ttu-id="f5079-245">Se hace referencia a ellos desde la <a href="lync-server-2013-device-table.md">tabla de dispositivos en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-247">int</span><span class="sxs-lookup"><span data-stu-id="f5079-247">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-248">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-249">Controlador para el dispositivo de captura del receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="f5079-250">Se hace referencia a partir de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-252">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="f5079-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f5079-253">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-254">Controlador del dispositivo de representación del receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="f5079-255">Se hace referencia a partir de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5079-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f5079-258">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-259">Indica cómo el destinatario de la llamada está conectado a la red.</span><span class="sxs-lookup"><span data-stu-id="f5079-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="f5079-260">Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="f5079-261">Los valores típicos son 0 para una conexión cableada ' 1 para una conexión WiFi; y 3 para una conexión Ethernet.</span><span class="sxs-lookup"><span data-stu-id="f5079-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-263">int</span><span class="sxs-lookup"><span data-stu-id="f5079-263">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-264">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-265">BSSID del destinatario de la llamada si se usa la tecnología inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="f5079-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="f5079-266">Se hace referencia desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-268">bit</span><span class="sxs-lookup"><span data-stu-id="f5079-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-269">Vínculo del receptor de la llamada; 1 es una red privada virtual (VPN) y 0 no es una VPN.</span><span class="sxs-lookup"><span data-stu-id="f5079-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-271">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="f5079-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-272">La velocidad del vínculo de red, en bps, para el extremo del receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-274">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f5079-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-275">OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="f5079-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-277">int</span><span class="sxs-lookup"><span data-stu-id="f5079-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5079-278">Este es el ancho de banda real aplicado a la transmisión de la parte de envío proporcionada, que proporciona varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.).</span><span class="sxs-lookup"><span data-stu-id="f5079-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="f5079-279">Esto no se debe confundir con el ancho de banda efectivo porque puede haber un ancho de banda más bajo según el cálculo de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="f5079-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="f5079-280">Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="f5079-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-282">smallint</span><span class="sxs-lookup"><span data-stu-id="f5079-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5079-283">Este es el origen del límite de ancho de banda que se impone.</span><span class="sxs-lookup"><span data-stu-id="f5079-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="f5079-284">Describe dónde viene el límite de ancho de banda ("servidor de directivas", "TURN Server", "Modación", etc.).</span><span class="sxs-lookup"><span data-stu-id="f5079-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="f5079-285">Se hace referencia a ellos desde la <a href="lync-server-2013-appliedbandwidthsource-table.md">tabla AppliedBandwidthSource en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5079-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-286"><strong>Autor de llamada</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-287">bit</span><span class="sxs-lookup"><span data-stu-id="f5079-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-288">Indica si se recibieron las métricas de la persona que llama; 1 es sí, un valor nulo es no.</span><span class="sxs-lookup"><span data-stu-id="f5079-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-289"><strong>Destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-290">bit</span><span class="sxs-lookup"><span data-stu-id="f5079-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5079-291">Indica si se han recibido métricas del receptor de la llamada; 1 es sí, un valor nulo es no.</span><span class="sxs-lookup"><span data-stu-id="f5079-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-293">bit</span><span class="sxs-lookup"><span data-stu-id="f5079-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5079-294">Indica si el informe es para una parte de la sesión o para la sesión completa.</span><span class="sxs-lookup"><span data-stu-id="f5079-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="f5079-295">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5079-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-297">bit</span><span class="sxs-lookup"><span data-stu-id="f5079-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5079-298">Indica si una llamada se ha clasificado como una llamada deficiente (valor de 1) o como una buena llamada (0).</span><span class="sxs-lookup"><span data-stu-id="f5079-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="f5079-299">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5079-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="f5079-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5079-302">Indica si la persona que llama se ha conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).</span><span class="sxs-lookup"><span data-stu-id="f5079-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="f5079-303">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5079-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5079-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5079-306">Indica si la persona que llama se ha conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).</span><span class="sxs-lookup"><span data-stu-id="f5079-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="f5079-307">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5079-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-309">int</span><span class="sxs-lookup"><span data-stu-id="f5079-309">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-310">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-311">Dirección IP reflexiva del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="f5079-312">En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="f5079-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="f5079-313">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5079-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-315">int</span><span class="sxs-lookup"><span data-stu-id="f5079-315">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-316">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-317">Descripción del dispositivo para el controlador WiFi empleado por el usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="f5079-318">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5079-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-320">int</span><span class="sxs-lookup"><span data-stu-id="f5079-320">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-321">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-322">Número de versión del controlador WiFi empleado por el usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="f5079-323">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5079-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-325">int</span><span class="sxs-lookup"><span data-stu-id="f5079-325">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-326">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-327">Dirección IP reflexiva del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="f5079-328">En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="f5079-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="f5079-329">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5079-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5079-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-331">int</span><span class="sxs-lookup"><span data-stu-id="f5079-331">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-332">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-333">Descripción del dispositivo para el controlador WiFi empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="f5079-334">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5079-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5079-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f5079-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f5079-336">int</span><span class="sxs-lookup"><span data-stu-id="f5079-336">int</span></span></p></td>
<td><p><span data-ttu-id="f5079-337">Extranjero</span><span class="sxs-lookup"><span data-stu-id="f5079-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f5079-338">Número de versión del controlador WiFi empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5079-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="f5079-339">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5079-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

