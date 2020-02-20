---
title: 'Lync Server 2013: tabla MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf0e216d90af0d32a0e700661a653a13028e01a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="060f7-102">Tabla MediaLine en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="060f7-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="060f7-103">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="060f7-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="060f7-104">Cada registro representa una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="060f7-104">Each record represents one media line.</span></span> <span data-ttu-id="060f7-105">(Una sesión de audio suele contener una línea de medios de audio.</span><span class="sxs-lookup"><span data-stu-id="060f7-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="060f7-106">Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión puede contener dos líneas de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="060f7-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="060f7-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="060f7-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="060f7-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="060f7-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="060f7-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="060f7-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="060f7-113">Principal</span><span class="sxs-lookup"><span data-stu-id="060f7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="060f7-114">Se hace referencia a ella desde la <a href="lync-server-2013-session-table.md">tabla Session en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-116">int</span><span class="sxs-lookup"><span data-stu-id="060f7-116">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-117">Principal</span><span class="sxs-lookup"><span data-stu-id="060f7-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="060f7-118">Se hace referencia a ella desde la <a href="lync-server-2013-session-table.md">tabla Session en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="060f7-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="060f7-121">Principal</span><span class="sxs-lookup"><span data-stu-id="060f7-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="060f7-122">0 es el audio principal, 1 es el vídeo principal y 2 es vídeo panorámico, 3 es uso compartido de aplicaciones y escritorio.</span><span class="sxs-lookup"><span data-stu-id="060f7-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="060f7-123">Esta etiqueta debe ser única en una sola sesión.</span><span class="sxs-lookup"><span data-stu-id="060f7-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="060f7-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-126">Esta columna está presente pero no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="060f7-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="060f7-127">La información acerca de la conectividad usada para una línea de medios se captura en las columnas CallerConnectivityICE y CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="060f7-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-129">int</span><span class="sxs-lookup"><span data-stu-id="060f7-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-130">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) que se describe en indicadores de bits.</span><span class="sxs-lookup"><span data-stu-id="060f7-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="060f7-131">Para obtener más información, consulte la <em>especificación de protocolo de servidor de supervisión de calidad de la experiencia</em>, disponible para su descarga.</span><span class="sxs-lookup"><span data-stu-id="060f7-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-133">int</span><span class="sxs-lookup"><span data-stu-id="060f7-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-134">Igual que CallerIceWarningFlags, pero en el lado del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="060f7-135">Para obtener más información, consulte la <em>especificación de protocolo de servidor de supervisión de calidad de la experiencia</em>, disponible para su descarga.</span><span class="sxs-lookup"><span data-stu-id="060f7-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-136"><strong>Seguridad</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="060f7-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-138">Perfil de seguridad en uso.</span><span class="sxs-lookup"><span data-stu-id="060f7-138">The security profile in use.</span></span> <span data-ttu-id="060f7-139">0 es NONE, 1 es SRTP, 2 es V1.</span><span class="sxs-lookup"><span data-stu-id="060f7-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="060f7-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-142">0 es UDP, 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="060f7-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-144">int</span><span class="sxs-lookup"><span data-stu-id="060f7-144">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-145">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-146">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-146">IP Address of the caller.</span></span> <span data-ttu-id="060f7-147">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="060f7-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-149">int</span><span class="sxs-lookup"><span data-stu-id="060f7-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-150">Puerto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-152">int</span><span class="sxs-lookup"><span data-stu-id="060f7-152">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-153"> Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-154">La subred del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-154">The subnet of the caller.</span></span> <span data-ttu-id="060f7-155">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="060f7-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-157">bit</span><span class="sxs-lookup"><span data-stu-id="060f7-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-158">El valor 1 significa que el autor de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.</span><span class="sxs-lookup"><span data-stu-id="060f7-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-160">int</span><span class="sxs-lookup"><span data-stu-id="060f7-160">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-161">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-162">Dirección Mac del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-164">int</span><span class="sxs-lookup"><span data-stu-id="060f7-164">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-165">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-166">Dirección IP del servicio perimetral A/V de Lync Server que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="060f7-167">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="060f7-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-169">int</span><span class="sxs-lookup"><span data-stu-id="060f7-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-170">Puerto usado en el servicio perimetral A/V por parte del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-172">int</span><span class="sxs-lookup"><span data-stu-id="060f7-172">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-173">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-174">Dispositivo de captura usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-174">Capture device used by the caller.</span></span> <span data-ttu-id="060f7-175">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-177">int</span><span class="sxs-lookup"><span data-stu-id="060f7-177">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-178">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-179">Dispositivo de representación usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-179">Render device used by caller.</span></span> <span data-ttu-id="060f7-180">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-182">int</span><span class="sxs-lookup"><span data-stu-id="060f7-182">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-183">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-184">Controlador del dispositivo de captura del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-186">int</span><span class="sxs-lookup"><span data-stu-id="060f7-186">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-187">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-188">Controlador del dispositivo de representación del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="060f7-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="060f7-191">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-192">Indica cómo el autor de la llamada se conectó a la red.</span><span class="sxs-lookup"><span data-stu-id="060f7-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="060f7-193">Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="060f7-194">Los valores típicos son 0 para una conexión cableada "1" para una conexión WiFi; y 3 para una conexión Ethernet.</span><span class="sxs-lookup"><span data-stu-id="060f7-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-196">int</span><span class="sxs-lookup"><span data-stu-id="060f7-196">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-197">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-198">BSSID del autor de la llamada si se usa la tecnología inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="060f7-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="060f7-199">Referencia de la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-201">bit</span><span class="sxs-lookup"><span data-stu-id="060f7-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="060f7-202">Vínculo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-202">The caller's link.</span></span> <span data-ttu-id="060f7-203">El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.</span><span class="sxs-lookup"><span data-stu-id="060f7-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-205">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="060f7-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="060f7-206">Velocidad del vínculo de red, en bps, del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-208">int</span><span class="sxs-lookup"><span data-stu-id="060f7-208">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-209">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-210">Dirección IP del receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-210">IP Address of the call receiver.</span></span> <span data-ttu-id="060f7-211">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="060f7-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-213">bit</span><span class="sxs-lookup"><span data-stu-id="060f7-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="060f7-214">Puerto usado por el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="060f7-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-216">int</span><span class="sxs-lookup"><span data-stu-id="060f7-216">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-217">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-218">Subred del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-218">Subnet of callee.</span></span> <span data-ttu-id="060f7-219">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="060f7-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-221">bit</span><span class="sxs-lookup"><span data-stu-id="060f7-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-222">1 significa que el receptor de la llamada se encuentra dentro de la red de la empresa, 0 significa que el receptor de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="060f7-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-224">int</span><span class="sxs-lookup"><span data-stu-id="060f7-224">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-225">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-226">Dirección Mac del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-226">Callee Mac address.</span></span> <span data-ttu-id="060f7-227">Se hace referencia a ella desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-229">int</span><span class="sxs-lookup"><span data-stu-id="060f7-229">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-230">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-231">Dirección IP del servicio perimetral A/V que usa el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="060f7-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="060f7-232">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="060f7-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-234">int</span><span class="sxs-lookup"><span data-stu-id="060f7-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-235">Puerto usado en el servicio perimetral A/V por parte del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="060f7-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-237">int</span><span class="sxs-lookup"><span data-stu-id="060f7-237">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-238">externa</span><span class="sxs-lookup"><span data-stu-id="060f7-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-239">Dispositivo de captura usado por el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="060f7-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="060f7-240">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-242">int</span><span class="sxs-lookup"><span data-stu-id="060f7-242">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-243">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-244">Dispositivo de representación usado por el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="060f7-244">Render device used by the call receiver.</span></span> <span data-ttu-id="060f7-245">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-247">int</span><span class="sxs-lookup"><span data-stu-id="060f7-247">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-248">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-249">Controlador del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="060f7-250">Referencia de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-252">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="060f7-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="060f7-253">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-254">Controlador del dispositivo de representación del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="060f7-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="060f7-255">Referencia de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="060f7-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="060f7-258">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-259">Indica cómo el destinatario de la llamada se conectó a la red.</span><span class="sxs-lookup"><span data-stu-id="060f7-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="060f7-260">Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="060f7-261">Los valores típicos son 0 para una conexión cableada "1" para una conexión WiFi; y 3 para una conexión Ethernet.</span><span class="sxs-lookup"><span data-stu-id="060f7-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-263">int</span><span class="sxs-lookup"><span data-stu-id="060f7-263">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-264">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-265">BSSID del destinatario de la llamada si se usa la tecnología inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="060f7-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="060f7-266">Referencia de la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-268">bit</span><span class="sxs-lookup"><span data-stu-id="060f7-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-269">Vínculo del receptor de llamadas; 1 es una red privada virtual (VPN), 0 no es VPN.</span><span class="sxs-lookup"><span data-stu-id="060f7-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-271">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="060f7-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-272">Velocidad del vínculo de red, en bps, del extremo del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="060f7-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-274">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="060f7-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-275">MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="060f7-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-277">int</span><span class="sxs-lookup"><span data-stu-id="060f7-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="060f7-278">Este es el ancho de banda real que se aplica a la transmisión de la parte de envío determinada dadas varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.).</span><span class="sxs-lookup"><span data-stu-id="060f7-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="060f7-279">No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="060f7-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="060f7-280">Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="060f7-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-282">smallint</span><span class="sxs-lookup"><span data-stu-id="060f7-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="060f7-283">Origen del límite de ancho de banda impuesto.</span><span class="sxs-lookup"><span data-stu-id="060f7-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="060f7-284">Describe dónde procede el límite de ancho de banda ("Policy Server", "TURN Server", "Modate", etc.).</span><span class="sxs-lookup"><span data-stu-id="060f7-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="060f7-285">Referencia de la <a href="lync-server-2013-appliedbandwidthsource-table.md">tabla AppliedBandwidthSource en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="060f7-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-286"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-287">bit</span><span class="sxs-lookup"><span data-stu-id="060f7-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-288">Indica si se recibieron las métricas del autor de la llamada; 1 es sí, un valor NULL es no.</span><span class="sxs-lookup"><span data-stu-id="060f7-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-289"><strong>Destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-290">bit</span><span class="sxs-lookup"><span data-stu-id="060f7-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="060f7-291">Indica si se recibieron las métricas del receptor de llamadas; 1 es sí, un valor NULL es no.</span><span class="sxs-lookup"><span data-stu-id="060f7-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-293">bit</span><span class="sxs-lookup"><span data-stu-id="060f7-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="060f7-294">Indica si el informe es para una parte de la sesión o para la sesión completa.</span><span class="sxs-lookup"><span data-stu-id="060f7-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="060f7-295">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="060f7-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-297">bit</span><span class="sxs-lookup"><span data-stu-id="060f7-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="060f7-298">Indica si una llamada se ha clasificado como una llamada deficiente (valor 1) o como una buena llamada (0).</span><span class="sxs-lookup"><span data-stu-id="060f7-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="060f7-299">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="060f7-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="060f7-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="060f7-302">Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</span><span class="sxs-lookup"><span data-stu-id="060f7-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="060f7-303">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="060f7-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="060f7-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="060f7-306">Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</span><span class="sxs-lookup"><span data-stu-id="060f7-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="060f7-307">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="060f7-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-309">int</span><span class="sxs-lookup"><span data-stu-id="060f7-309">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-310">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-311">Dirección IP reflexiva del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="060f7-312">En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="060f7-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="060f7-313">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="060f7-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-315">int</span><span class="sxs-lookup"><span data-stu-id="060f7-315">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-316">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-317">Descripción del dispositivo del controlador WiFi empleado por el usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="060f7-318">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="060f7-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-320">int</span><span class="sxs-lookup"><span data-stu-id="060f7-320">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-321">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-322">Número de versión del controlador WiFi empleado por el usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="060f7-323">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="060f7-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-325">int</span><span class="sxs-lookup"><span data-stu-id="060f7-325">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-326">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-327">Dirección IP reflexiva del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="060f7-328">En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="060f7-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="060f7-329">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="060f7-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060f7-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-331">int</span><span class="sxs-lookup"><span data-stu-id="060f7-331">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-332">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-333">Descripción del dispositivo del controlador WiFi empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="060f7-334">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="060f7-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060f7-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="060f7-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="060f7-336">int</span><span class="sxs-lookup"><span data-stu-id="060f7-336">int</span></span></p></td>
<td><p><span data-ttu-id="060f7-337">Externa</span><span class="sxs-lookup"><span data-stu-id="060f7-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="060f7-338">Número de versión del controlador WiFi empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="060f7-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="060f7-339">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="060f7-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

