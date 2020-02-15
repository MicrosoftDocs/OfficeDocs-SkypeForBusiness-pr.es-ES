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
ms.openlocfilehash: 3496b8fe96e2bdfcbb49ec0155d66ad4eeb106fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="d0c48-102">Tabla MediaLine en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0c48-102">MediaLine table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0c48-103">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="d0c48-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="d0c48-104">Cada registro representa una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="d0c48-104">Each record represents one media line.</span></span> <span data-ttu-id="d0c48-105">(Una sesión de audio suele contener una línea de medios de audio.</span><span class="sxs-lookup"><span data-stu-id="d0c48-105">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="d0c48-106">Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión puede contener dos líneas de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="d0c48-106">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0c48-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d0c48-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d0c48-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d0c48-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d0c48-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d0c48-113">Principal</span><span class="sxs-lookup"><span data-stu-id="d0c48-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d0c48-114">Se hace referencia a ella desde la <a href="lync-server-2013-session-table.md">tabla Session en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-114">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-116">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-116">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-117">Principal</span><span class="sxs-lookup"><span data-stu-id="d0c48-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="d0c48-118">Se hace referencia a ella desde la <a href="lync-server-2013-session-table.md">tabla Session en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-118">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d0c48-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d0c48-121">Principal</span><span class="sxs-lookup"><span data-stu-id="d0c48-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="d0c48-122">0 es el audio principal, 1 es el vídeo principal y 2 es vídeo panorámico, 3 es uso compartido de aplicaciones y escritorio.</span><span class="sxs-lookup"><span data-stu-id="d0c48-122">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="d0c48-123">Esta etiqueta debe ser única en una sola sesión.</span><span class="sxs-lookup"><span data-stu-id="d0c48-123">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-124"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-124"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-125">tinyint</span><span class="sxs-lookup"><span data-stu-id="d0c48-125">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-126">Esta columna está presente pero no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c48-126">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d0c48-127">La información acerca de la conectividad usada para una línea de medios se captura en las columnas CallerConnectivityICE y CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="d0c48-127">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-128"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-128"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-129">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-130">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) que se describe en indicadores de bits.</span><span class="sxs-lookup"><span data-stu-id="d0c48-130">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="d0c48-131">Para obtener más información, consulte la <em>especificación de protocolo de servidor de supervisión de calidad de la experiencia</em>, disponible para su descarga.</span><span class="sxs-lookup"><span data-stu-id="d0c48-131">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-132"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-132"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-133">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-134">Igual que CallerIceWarningFlags, pero en el lado del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-134">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="d0c48-135">Para obtener más información, consulte la <em>especificación de protocolo de servidor de supervisión de calidad de la experiencia</em>, disponible para su descarga.</span><span class="sxs-lookup"><span data-stu-id="d0c48-135">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-136"><strong>Seguridad</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-136"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-137">tinyint</span><span class="sxs-lookup"><span data-stu-id="d0c48-137">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-138">Perfil de seguridad en uso.</span><span class="sxs-lookup"><span data-stu-id="d0c48-138">The security profile in use.</span></span> <span data-ttu-id="d0c48-139">0 es NONE, 1 es SRTP, 2 es V1.</span><span class="sxs-lookup"><span data-stu-id="d0c48-139">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-140"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-140"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-141">tinyint</span><span class="sxs-lookup"><span data-stu-id="d0c48-141">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-142">0 es UDP, 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="d0c48-142">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-143"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-143"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-144">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-144">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-145">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-146">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-146">IP Address of the caller.</span></span> <span data-ttu-id="d0c48-147">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d0c48-147">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-148"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-148"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-149">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-150">Puerto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-150">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-151"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-151"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-152">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-152">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-153"> Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-153"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-154">La subred del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-154">The subnet of the caller.</span></span> <span data-ttu-id="d0c48-155">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d0c48-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-156"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-156"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-157">bit</span><span class="sxs-lookup"><span data-stu-id="d0c48-157">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-158">El valor 1 significa que el autor de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.</span><span class="sxs-lookup"><span data-stu-id="d0c48-158">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-159"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-159"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-160">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-160">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-161">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-162">Dirección Mac del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-162">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-163"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-163"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-164">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-164">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-165">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-166">Dirección IP del servicio perimetral A/V de Lync Server que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-166">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="d0c48-167">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d0c48-167">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-168"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-168"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-169">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-170">Puerto usado en el servicio perimetral A/V por parte del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-170">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-171"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-171"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-172">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-172">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-173">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-174">Dispositivo de captura usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-174">Capture device used by the caller.</span></span> <span data-ttu-id="d0c48-175">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-175">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-176"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-176"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-177">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-177">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-178">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-178">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-179">Dispositivo de representación usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-179">Render device used by caller.</span></span> <span data-ttu-id="d0c48-180">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-180">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-181"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-181"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-182">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-182">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-183">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-184">Controlador del dispositivo de captura del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-184">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-185"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-185"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-186">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-186">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-187">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-188">Controlador del dispositivo de representación del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-188">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-189"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-189"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="d0c48-190">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d0c48-191">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-192">Indica cómo el autor de la llamada se conectó a la red.</span><span class="sxs-lookup"><span data-stu-id="d0c48-192">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="d0c48-193">Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-193">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="d0c48-194">Los valores típicos son 0 para una conexión cableada "1" para una conexión WiFi; y 3 para una conexión Ethernet.</span><span class="sxs-lookup"><span data-stu-id="d0c48-194">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-195"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-195"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-196">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-196">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-197">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-198">BSSID del autor de la llamada si se usa la tecnología inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="d0c48-198">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="d0c48-199">Referencia de la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-199">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-200"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-200"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-201">bit</span><span class="sxs-lookup"><span data-stu-id="d0c48-201">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0c48-202">Vínculo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-202">The caller's link.</span></span> <span data-ttu-id="d0c48-203">El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.</span><span class="sxs-lookup"><span data-stu-id="d0c48-203">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-204"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-204"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-205">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="d0c48-205">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0c48-206">Velocidad del vínculo de red, en bps, del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-206">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-207"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-207"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-208">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-208">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-209">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-209">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-210">Dirección IP del receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-210">IP Address of the call receiver.</span></span> <span data-ttu-id="d0c48-211">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d0c48-211">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-212"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-212"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-213">bit</span><span class="sxs-lookup"><span data-stu-id="d0c48-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0c48-214">Puerto usado por el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d0c48-214">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-215"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-215"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-216">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-216">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-217">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-218">Subred del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-218">Subnet of callee.</span></span> <span data-ttu-id="d0c48-219">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d0c48-219">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-220"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-220"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-221">bit</span><span class="sxs-lookup"><span data-stu-id="d0c48-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-222">1 significa que el receptor de la llamada se encuentra dentro de la red de la empresa, 0 significa que el receptor de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="d0c48-222">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-223"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-223"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-224">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-224">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-225">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-225">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-226">Dirección Mac del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-226">Callee Mac address.</span></span> <span data-ttu-id="d0c48-227">Se hace referencia a ella desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-227">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-228"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-228"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-229">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-229">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-230">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-230">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-231">Dirección IP del servicio perimetral A/V que usa el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d0c48-231">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="d0c48-232">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d0c48-232">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-233"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-233"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-234">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-234">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-235">Puerto usado en el servicio perimetral A/V por parte del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d0c48-235">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-236"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-236"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-237">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-237">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-238">externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-238">foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-239">Dispositivo de captura usado por el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d0c48-239">Capture device used by the call receiver.</span></span> <span data-ttu-id="d0c48-240">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-240">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-241"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-241"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-242">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-242">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-243">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-243">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-244">Dispositivo de representación usado por el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d0c48-244">Render device used by the call receiver.</span></span> <span data-ttu-id="d0c48-245">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-245">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-246"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-246"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-247">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-247">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-248">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-248">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-249">Controlador del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-249">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="d0c48-250">Referencia de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-250">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-251"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-251"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-252">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="d0c48-252">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d0c48-253">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-253">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-254">Controlador del dispositivo de representación del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d0c48-254">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="d0c48-255">Referencia de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-255">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-256"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-256"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-257">tinyint</span><span class="sxs-lookup"><span data-stu-id="d0c48-257">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d0c48-258">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-258">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-259">Indica cómo el destinatario de la llamada se conectó a la red.</span><span class="sxs-lookup"><span data-stu-id="d0c48-259">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="d0c48-260">Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-260">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="d0c48-261">Los valores típicos son 0 para una conexión cableada "1" para una conexión WiFi; y 3 para una conexión Ethernet.</span><span class="sxs-lookup"><span data-stu-id="d0c48-261">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-262"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-262"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-263">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-263">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-264">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-264">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-265">BSSID del destinatario de la llamada si se usa la tecnología inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="d0c48-265">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="d0c48-266">Referencia de la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-266">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-267"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-267"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-268">bit</span><span class="sxs-lookup"><span data-stu-id="d0c48-268">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-269">Vínculo del receptor de llamadas; 1 es una red privada virtual (VPN), 0 no es VPN.</span><span class="sxs-lookup"><span data-stu-id="d0c48-269">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-270"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-270"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-271">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="d0c48-271">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-272">Velocidad del vínculo de red, en bps, del extremo del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d0c48-272">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-273"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-273"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-274">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d0c48-274">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-275">MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="d0c48-275">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-276"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-276"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-277">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0c48-278">Este es el ancho de banda real que se aplica a la transmisión de la parte de envío determinada dadas varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.).</span><span class="sxs-lookup"><span data-stu-id="d0c48-278">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="d0c48-279">No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="d0c48-279">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="d0c48-280">Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="d0c48-280">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-281"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-281"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-282">smallint</span><span class="sxs-lookup"><span data-stu-id="d0c48-282">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0c48-283">Origen del límite de ancho de banda impuesto.</span><span class="sxs-lookup"><span data-stu-id="d0c48-283">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="d0c48-284">Describe dónde procede el límite de ancho de banda ("Policy Server", "TURN Server", "Modate", etc.).</span><span class="sxs-lookup"><span data-stu-id="d0c48-284">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="d0c48-285">Referencia de la <a href="lync-server-2013-appliedbandwidthsource-table.md">tabla AppliedBandwidthSource en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d0c48-285">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-286"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-286"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-287">bit</span><span class="sxs-lookup"><span data-stu-id="d0c48-287">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-288">Indica si se recibieron las métricas del autor de la llamada; 1 es sí, un valor NULL es no.</span><span class="sxs-lookup"><span data-stu-id="d0c48-288">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-289"><strong>Destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-289"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-290">bit</span><span class="sxs-lookup"><span data-stu-id="d0c48-290">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d0c48-291">Indica si se recibieron las métricas del receptor de llamadas; 1 es sí, un valor NULL es no.</span><span class="sxs-lookup"><span data-stu-id="d0c48-291">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-292"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-292"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-293">bit</span><span class="sxs-lookup"><span data-stu-id="d0c48-293">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0c48-294">Indica si el informe es para una parte de la sesión o para la sesión completa.</span><span class="sxs-lookup"><span data-stu-id="d0c48-294">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="d0c48-295">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c48-295">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-296"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-296"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-297">bit</span><span class="sxs-lookup"><span data-stu-id="d0c48-297">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0c48-298">Indica si una llamada se ha clasificado como una llamada deficiente (valor 1) o como una buena llamada (0).</span><span class="sxs-lookup"><span data-stu-id="d0c48-298">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="d0c48-299">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c48-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-300"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-300"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-301">tinyInt</span><span class="sxs-lookup"><span data-stu-id="d0c48-301">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0c48-302">Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</span><span class="sxs-lookup"><span data-stu-id="d0c48-302">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="d0c48-303">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c48-303">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-304"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-304"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-305">tinyint</span><span class="sxs-lookup"><span data-stu-id="d0c48-305">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d0c48-306">Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</span><span class="sxs-lookup"><span data-stu-id="d0c48-306">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="d0c48-307">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c48-307">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-308"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-308"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-309">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-309">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-310">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-310">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-311">Dirección IP reflexiva del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-311">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="d0c48-312">En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d0c48-312">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="d0c48-313">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c48-313">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-314"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-314"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-315">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-315">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-316">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-316">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-317">Descripción del dispositivo del controlador WiFi empleado por el usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-317">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="d0c48-318">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c48-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-319"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-319"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-320">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-320">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-321">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-321">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-322">Número de versión del controlador WiFi empleado por el usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-322">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="d0c48-323">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c48-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-324"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-324"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-325">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-325">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-326">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-326">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-327">Dirección IP reflexiva del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-327">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="d0c48-328">En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d0c48-328">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="d0c48-329">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c48-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0c48-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-330"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-331">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-331">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-332">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-332">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-333">Descripción del dispositivo del controlador WiFi empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-333">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="d0c48-334">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c48-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0c48-335"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d0c48-335"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d0c48-336">int</span><span class="sxs-lookup"><span data-stu-id="d0c48-336">int</span></span></p></td>
<td><p><span data-ttu-id="d0c48-337">Externa</span><span class="sxs-lookup"><span data-stu-id="d0c48-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d0c48-338">Número de versión del controlador WiFi empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="d0c48-338">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="d0c48-339">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0c48-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

