---
title: 'Lync Server 2013: tabla MediaLine'
description: 'Lync Server 2013: tabla MediaLine.'
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
ms.openlocfilehash: 2acea8e14ba0608d9ebf72a48f888bfc4501fae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572116"
---
# <a name="medialine-table-in-lync-server-2013"></a><span data-ttu-id="afce3-103">Tabla MediaLine en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afce3-103">MediaLine table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afce3-104">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="afce3-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="afce3-105">Cada registro representa una línea de medios.</span><span class="sxs-lookup"><span data-stu-id="afce3-105">Each record represents one media line.</span></span> <span data-ttu-id="afce3-106">(Una sesión de audio suele contener una línea de medios de audio.</span><span class="sxs-lookup"><span data-stu-id="afce3-106">(One audio session usually contains one audio media line.</span></span> <span data-ttu-id="afce3-107">Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión puede contener dos líneas de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="afce3-107">One audio and video (A/V) session usually contains one audio media line and one video media line, although the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afce3-108"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="afce3-109"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="afce3-110"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="afce3-111"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afce3-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-113">datetime</span><span class="sxs-lookup"><span data-stu-id="afce3-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="afce3-114">Principal</span><span class="sxs-lookup"><span data-stu-id="afce3-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="afce3-115">Se hace referencia a ella desde la <a href="lync-server-2013-session-table.md">tabla Session en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-115">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-117">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-117">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-118">Principal</span><span class="sxs-lookup"><span data-stu-id="afce3-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="afce3-119">Se hace referencia a ella desde la <a href="lync-server-2013-session-table.md">tabla Session en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-119">Referenced from the <a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-120"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-120"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-121">tinyint</span><span class="sxs-lookup"><span data-stu-id="afce3-121">tinyint</span></span></p></td>
<td><p><span data-ttu-id="afce3-122">Principal</span><span class="sxs-lookup"><span data-stu-id="afce3-122">Primary</span></span></p></td>
<td><p><span data-ttu-id="afce3-123">0 es el audio principal, 1 es el vídeo principal y 2 es vídeo panorámico, 3 es uso compartido de aplicaciones y escritorio.</span><span class="sxs-lookup"><span data-stu-id="afce3-123">0 is main audio, 1 is main video, and 2 is panoramic video, 3 is Application/Desktop Sharing.</span></span> <span data-ttu-id="afce3-124">Esta etiqueta debe ser única en una sola sesión.</span><span class="sxs-lookup"><span data-stu-id="afce3-124">This label must be unique within a single session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-125"><strong>ConnectivityIce</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-125"><strong>ConnectivityIce</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-126">tinyint</span><span class="sxs-lookup"><span data-stu-id="afce3-126">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-127">Esta columna está presente pero no se usa en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afce3-127">This column is present but not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="afce3-128">La información acerca de la conectividad usada para una línea de medios se captura en las columnas CallerConnectivityICE y CalleeConnectivityICE.</span><span class="sxs-lookup"><span data-stu-id="afce3-128">Information about the connectivity used for a media line is captured in the CallerConnectivityICE and CalleeConnectivityICE columns.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-129"><strong>CallerIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-129"><strong>CallerIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-130">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-131">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) que se describe en indicadores de bits.</span><span class="sxs-lookup"><span data-stu-id="afce3-131">Information about Interactive Connectivity Establishment (ICE) process described in bits flags.</span></span> <span data-ttu-id="afce3-132">Para obtener más información, consulte la <em>especificación de protocolo de servidor de supervisión de calidad de la experiencia</em>, disponible para su descarga.</span><span class="sxs-lookup"><span data-stu-id="afce3-132">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-133"><strong>CalleeIceWarningFlags</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-133"><strong>CalleeIceWarningFlags</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-134">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-135">Igual que CallerIceWarningFlags, pero en el lado del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-135">Same as CallerIceWarningFlags, but on the callee side.</span></span> <span data-ttu-id="afce3-136">Para obtener más información, consulte la <em>especificación de protocolo de servidor de supervisión de calidad de la experiencia</em>, disponible para su descarga.</span><span class="sxs-lookup"><span data-stu-id="afce3-136">For details, refer to the <em>Quality of Experience Monitoring Server Protocol Specification</em>, available for download.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-137"><strong>Seguridad</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-137"><strong>Security</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-138">tinyint</span><span class="sxs-lookup"><span data-stu-id="afce3-138">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-139">Perfil de seguridad en uso.</span><span class="sxs-lookup"><span data-stu-id="afce3-139">The security profile in use.</span></span> <span data-ttu-id="afce3-140">0 es NONE, 1 es SRTP, 2 es V1.</span><span class="sxs-lookup"><span data-stu-id="afce3-140">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-141"><strong>Transport</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-141"><strong>Transport</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-142">tinyint</span><span class="sxs-lookup"><span data-stu-id="afce3-142">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-143">0 es UDP, 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="afce3-143">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-144"><strong>CallerIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-144"><strong>CallerIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-145">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-145">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-146">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-147">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-147">IP Address of the caller.</span></span> <span data-ttu-id="afce3-148">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="afce3-148">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-149"><strong>CallerPort</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-149"><strong>CallerPort</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-150">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-151">Puerto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-151">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-152"><strong>CallerSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-152"><strong>CallerSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-153">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-153">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-154"> Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-154"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-155">La subred del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-155">The subnet of the caller.</span></span> <span data-ttu-id="afce3-156">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="afce3-156">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-157"><strong>CallerInside</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-157"><strong>CallerInside</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-158">bit</span><span class="sxs-lookup"><span data-stu-id="afce3-158">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-159">El valor 1 significa que el autor de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.</span><span class="sxs-lookup"><span data-stu-id="afce3-159">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-160"><strong>CallerMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-160"><strong>CallerMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-161">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-161">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-162">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-163">Dirección Mac del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-163">Caller’s mac address, referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-164"><strong>CallerRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-164"><strong>CallerRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-165">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-165">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-166">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-167">Dirección IP del servicio perimetral A/V de Lync Server que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-167">IP Address of the Lync Server A/V Edge service used by the caller.</span></span> <span data-ttu-id="afce3-168">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="afce3-168">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-169"><strong>CallerRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-169"><strong>CallerRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-170">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-171">Puerto usado en el servicio perimetral A/V por parte del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-171">Port used on the A/V Edge service by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-172"><strong>CallerCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-172"><strong>CallerCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-173">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-173">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-174">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-175">Dispositivo de captura usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-175">Capture device used by the caller.</span></span> <span data-ttu-id="afce3-176">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-176">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-177"><strong>CallerRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-177"><strong>CallerRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-178">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-178">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-179">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-179">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-180">Dispositivo de representación usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-180">Render device used by caller.</span></span> <span data-ttu-id="afce3-181">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-181">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-182"><strong>CallerCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-182"><strong>CallerCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-183">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-183">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-184">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-185">Controlador del dispositivo de captura del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-185">Driver for the caller’s capture device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-186"><strong>CallerRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-186"><strong>CallerRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-187">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-187">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-188">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-189">Controlador del dispositivo de representación del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-189">Driver for the caller’s render device, referenced from the <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-190"><strong>CallerNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-190"><strong>CallerNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="afce3-191">tinyint</span></span></p></td>
<td><p><span data-ttu-id="afce3-192">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-193">Indica cómo el autor de la llamada se conectó a la red.</span><span class="sxs-lookup"><span data-stu-id="afce3-193">Indicates how the caller connected to the network.</span></span> <span data-ttu-id="afce3-194">Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-194">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="afce3-195">Los valores típicos son 0 para una conexión cableada "1" para una conexión WiFi; y 3 para una conexión Ethernet.</span><span class="sxs-lookup"><span data-stu-id="afce3-195">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-196"><strong>CallerBssid</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-196"><strong>CallerBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-197">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-197">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-198">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-199">BSSID del autor de la llamada si se usa la tecnología inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="afce3-199">Caller’s BSSID if wireless is used.</span></span> <span data-ttu-id="afce3-200">Referencia de la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-200">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-201"><strong>CallerVPN</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-201"><strong>CallerVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-202">bit</span><span class="sxs-lookup"><span data-stu-id="afce3-202">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afce3-203">Vínculo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-203">The caller's link.</span></span> <span data-ttu-id="afce3-204">El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.</span><span class="sxs-lookup"><span data-stu-id="afce3-204">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-205"><strong>CallerLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-205"><strong>CallerLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-206">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="afce3-206">decimal(18,0)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afce3-207">Velocidad del vínculo de red, en bps, del extremo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-207">The network link speed, in bps, for the caller's endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-208"><strong>CalleeIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-208"><strong>CalleeIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-209">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-209">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-210">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-210">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-211">Dirección IP del receptor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-211">IP Address of the call receiver.</span></span> <span data-ttu-id="afce3-212">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="afce3-212">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-213"><strong>CalleePort</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-213"><strong>CalleePort</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-214">bit</span><span class="sxs-lookup"><span data-stu-id="afce3-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afce3-215">Puerto usado por el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="afce3-215">Port used by the call receiver.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-216"><strong>CalleeSubnet</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-216"><strong>CalleeSubnet</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-217">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-217">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-218">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-219">Subred del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-219">Subnet of callee.</span></span> <span data-ttu-id="afce3-220">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="afce3-220">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-221"><strong>CalleeInside</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-221"><strong>CalleeInside</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-222">bit</span><span class="sxs-lookup"><span data-stu-id="afce3-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-223">1 significa que el receptor de la llamada se encuentra dentro de la red de la empresa, 0 significa que el receptor de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="afce3-223">1 means call receiver is inside the enterprise network, 0 means the call receiver is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-224"><strong>CalleeMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-224"><strong>CalleeMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-225">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-225">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-226">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-226">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-227">Dirección Mac del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-227">Callee Mac address.</span></span> <span data-ttu-id="afce3-228">Se hace referencia a ella desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-228">Referenced from the <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-229"><strong>CalleeRelayIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-229"><strong>CalleeRelayIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-230">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-230">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-231">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-231">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-232">Dirección IP del servicio perimetral A/V que usa el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="afce3-232">IP Address of the A/V Edge service used by the call receiver.</span></span> <span data-ttu-id="afce3-233">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="afce3-233">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-234"><strong>CalleeRelayPort</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-234"><strong>CalleeRelayPort</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-235">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-235">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-236">Puerto usado en el servicio perimetral A/V por parte del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="afce3-236">Port used on the A/V Edge Service by the call receiver.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-237"><strong>CalleeCaptureDev</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-237"><strong>CalleeCaptureDev</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-238">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-238">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-239">externa</span><span class="sxs-lookup"><span data-stu-id="afce3-239">foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-240">Dispositivo de captura usado por el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="afce3-240">Capture device used by the call receiver.</span></span> <span data-ttu-id="afce3-241">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-241">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-242"><strong>CalleeRenderDev</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-242"><strong>CalleeRenderDev</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-243">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-243">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-244">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-244">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-245">Dispositivo de representación usado por el receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="afce3-245">Render device used by the call receiver.</span></span> <span data-ttu-id="afce3-246">Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-246">Referenced from the <a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-247"><strong>CalleeCaptureDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-247"><strong>CalleeCaptureDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-248">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-248">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-249">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-249">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-250">Controlador del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-250">Driver for the call receiver’s capture device.</span></span> <span data-ttu-id="afce3-251">Referencia de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-251">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-252"><strong>CalleeRenderDevDriver</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-252"><strong>CalleeRenderDevDriver</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-253">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="afce3-253">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="afce3-254">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-254">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-255">Controlador del dispositivo de representación del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="afce3-255">Driver for the call receiver’s render device.</span></span> <span data-ttu-id="afce3-256">Referencia de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-256">Referenced from <a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-257"><strong>CalleeNetworkConnectionType</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-257"><strong>CalleeNetworkConnectionType</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-258">tinyint</span><span class="sxs-lookup"><span data-stu-id="afce3-258">tinyint</span></span></p></td>
<td><p><span data-ttu-id="afce3-259">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-259">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-260">Indica cómo el destinatario de la llamada se conectó a la red.</span><span class="sxs-lookup"><span data-stu-id="afce3-260">Indicates how the callee connected to the network.</span></span> <span data-ttu-id="afce3-261">Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-261">Values are obtained from the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a>.</span></span> <span data-ttu-id="afce3-262">Los valores típicos son 0 para una conexión cableada "1" para una conexión WiFi; y 3 para una conexión Ethernet.</span><span class="sxs-lookup"><span data-stu-id="afce3-262">Typical values are 0 for a wired connection’ 1 for a WiFi connection; and 3 for an Ethernet connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-263"><strong>CalleeBssid</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-263"><strong>CalleeBssid</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-264">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-264">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-265">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-265">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-266">BSSID del destinatario de la llamada si se usa la tecnología inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="afce3-266">Callee’s BSSID if wireless is used.</span></span> <span data-ttu-id="afce3-267">Referencia de la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-267">Referenced from <a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-268"><strong>CalleeVPN</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-268"><strong>CalleeVPN</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-269">bit</span><span class="sxs-lookup"><span data-stu-id="afce3-269">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-270">Vínculo del receptor de llamadas; 1 es una red privada virtual (VPN), 0 no es VPN.</span><span class="sxs-lookup"><span data-stu-id="afce3-270">The call receiver’s link; 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-271"><strong>CalleeLinkSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-271"><strong>CalleeLinkSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-272">decimal (18; 0)</span><span class="sxs-lookup"><span data-stu-id="afce3-272">decimal(18,0)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-273">Velocidad del vínculo de red, en bps, del extremo del receptor de llamadas.</span><span class="sxs-lookup"><span data-stu-id="afce3-273">The network link speed, in bps, for the call receiver’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-274"><strong>ConversationalMOS</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-274"><strong>ConversationalMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-275">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="afce3-275">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-276">MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="afce3-276">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-277"><strong>AppliedBandwidthLimit</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-277"><strong>AppliedBandwidthLimit</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-278">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-278">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afce3-279">Este es el ancho de banda real que se aplica a la transmisión de la parte de envío determinada dadas varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.).</span><span class="sxs-lookup"><span data-stu-id="afce3-279">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="afce3-280">No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="afce3-280">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="afce3-281">Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="afce3-281">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-282"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-282"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-283">smallint</span><span class="sxs-lookup"><span data-stu-id="afce3-283">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afce3-284">Origen del límite de ancho de banda impuesto.</span><span class="sxs-lookup"><span data-stu-id="afce3-284">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="afce3-285">Describe dónde procede el límite de ancho de banda ("Policy Server", "TURN Server", "Modate", etc.).</span><span class="sxs-lookup"><span data-stu-id="afce3-285">It describes where the bandwidth limit is coming from (“Policy Server”, “TURN Server”, “Modality”, and so on).</span></span> <span data-ttu-id="afce3-286">Referencia de la <a href="lync-server-2013-appliedbandwidthsource-table.md">tabla AppliedBandwidthSource en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="afce3-286">Referenced from the <a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-287"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-287"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-288">bit</span><span class="sxs-lookup"><span data-stu-id="afce3-288">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-289">Indica si se recibieron las métricas del autor de la llamada; 1 es sí, un valor NULL es no.</span><span class="sxs-lookup"><span data-stu-id="afce3-289">Indicates whether metrics from the caller were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-290"><strong>Destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-290"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-291">bit</span><span class="sxs-lookup"><span data-stu-id="afce3-291">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="afce3-292">Indica si se recibieron las métricas del receptor de llamadas; 1 es sí, un valor NULL es no.</span><span class="sxs-lookup"><span data-stu-id="afce3-292">Indicates whether metrics from the call receiver were received; 1 is yes, a null value is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-293"><strong>MidCallReport</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-293"><strong>MidCallReport</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-294">bit</span><span class="sxs-lookup"><span data-stu-id="afce3-294">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afce3-295">Indica si el informe es para una parte de la sesión o para la sesión completa.</span><span class="sxs-lookup"><span data-stu-id="afce3-295">Indicates whether the report is for a portion of the session or for the complete session.</span></span></p>
<p><span data-ttu-id="afce3-296">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afce3-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-297"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-297"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-298">bit</span><span class="sxs-lookup"><span data-stu-id="afce3-298">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afce3-299">Indica si una llamada se ha clasificado como una llamada deficiente (valor 1) o como una buena llamada (0).</span><span class="sxs-lookup"><span data-stu-id="afce3-299">Indicates whether a call was classified as a poor call (value of 1) or as a good call (0).</span></span></p>
<p><span data-ttu-id="afce3-300">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afce3-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-301"><strong>CallerConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-301"><strong>CallerConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-302">tinyInt</span><span class="sxs-lookup"><span data-stu-id="afce3-302">tinyInt</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afce3-303">Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</span><span class="sxs-lookup"><span data-stu-id="afce3-303">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="afce3-304">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afce3-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-305"><strong>CalleeConnectivityICE</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-305"><strong>CalleeConnectivityICE</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-306">tinyint</span><span class="sxs-lookup"><span data-stu-id="afce3-306">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afce3-307">Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</span><span class="sxs-lookup"><span data-stu-id="afce3-307">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p>
<p><span data-ttu-id="afce3-308">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afce3-308">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-309"><strong>CallerReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-309"><strong>CallerReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-310">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-310">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-311">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-311">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-312">Dirección IP reflexiva del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-312">Reflexive IP address of the user who placed the call.</span></span> <span data-ttu-id="afce3-313">En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="afce3-313">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="afce3-314">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afce3-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-315"><strong>CallerWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-315"><strong>CallerWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-316">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-316">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-317">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-317">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-318">Descripción del dispositivo del controlador WiFi empleado por el usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-318">Device description for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="afce3-319">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afce3-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-320"><strong>CallerWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-320"><strong>CallerWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-321">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-321">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-322">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-322">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-323">Número de versión del controlador WiFi empleado por el usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-323">Version number for the WiFi driver employed by the user who placed the call.</span></span></p>
<p><span data-ttu-id="afce3-324">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afce3-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-325"><strong>CalleReflexiveLocalIPAddr</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-325"><strong>CalleReflexiveLocalIPAddr</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-326">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-326">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-327">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-327">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-328">Dirección IP reflexiva del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-328">Reflexive IP address of the user who received the call.</span></span> <span data-ttu-id="afce3-329">En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="afce3-329">In organizations that use NAT (network address translation), the reflexive IP address is the IP address of the proxy server.</span></span></p>
<p><span data-ttu-id="afce3-330">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afce3-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afce3-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-331"><strong>CalleeWiFiDriverDevicesDesc</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-332">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-332">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-333">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-333">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-334">Descripción del dispositivo del controlador WiFi empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-334">Device description for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="afce3-335">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afce3-335">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afce3-336"><strong>CalleeWiFiDriverVersion</strong></span><span class="sxs-lookup"><span data-stu-id="afce3-336"><strong>CalleeWiFiDriverVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="afce3-337">entero</span><span class="sxs-lookup"><span data-stu-id="afce3-337">int</span></span></p></td>
<td><p><span data-ttu-id="afce3-338">Externa</span><span class="sxs-lookup"><span data-stu-id="afce3-338">Foreign</span></span></p></td>
<td><p><span data-ttu-id="afce3-339">Número de versión del controlador WiFi empleado por el usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="afce3-339">Version number for the WiFi driver employed by the user who received the call.</span></span></p>
<p><span data-ttu-id="afce3-340">Esta columna se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afce3-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

