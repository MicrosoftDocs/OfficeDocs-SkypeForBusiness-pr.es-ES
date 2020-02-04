---
title: 'Lync Server 2013: vista MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aebd16d8bd2efaf8deeb6752deeb199411ab125
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="5b8ca-102">Vista MediaLine en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8ca-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b8ca-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5b8ca-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5b8ca-104">La vista MediaLine almacena información acerca de cada línea de medios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="5b8ca-105">Una sesión de audio normalmente contiene una línea multimedia de audio.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="5b8ca-106">Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medio de audio y una línea de medio de vídeo; sin embargo, la sesión podría contener dos líneas multimedia de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="5b8ca-107">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b8ca-108">Columna</span><span class="sxs-lookup"><span data-stu-id="5b8ca-108">Column</span></span></th>
<th><span data-ttu-id="5b8ca-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5b8ca-109">Data Type</span></span></th>
<th><span data-ttu-id="5b8ca-110">sobre</span><span class="sxs-lookup"><span data-stu-id="5b8ca-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="5b8ca-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5b8ca-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-113">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="5b8ca-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-115">int</span><span class="sxs-lookup"><span data-stu-id="5b8ca-115">int</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-116">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="5b8ca-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="5b8ca-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-119">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="5b8ca-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-121">int</span><span class="sxs-lookup"><span data-stu-id="5b8ca-121">int</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-122">Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en indicadores de bits para la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="5b8ca-123">Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="5b8ca-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-125">int</span><span class="sxs-lookup"><span data-stu-id="5b8ca-125">int</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-126">Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="5b8ca-127">Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-128">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5b8ca-128">Security</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="5b8ca-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-130">Perfil de seguridad en uso.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-130">Security profile in use.</span></span> <span data-ttu-id="5b8ca-131">0 es ninguno, 1 es SRTP, 2 es v1.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-132">Transport</span><span class="sxs-lookup"><span data-stu-id="5b8ca-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="5b8ca-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-134">Tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-134">Transport type.</span></span> <span data-ttu-id="5b8ca-135">0 es UDP, 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="5b8ca-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-138">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-138">IP address of the caller.</span></span> <span data-ttu-id="5b8ca-139">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="5b8ca-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-141">int</span><span class="sxs-lookup"><span data-stu-id="5b8ca-141">int</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-142">Puerto usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="5b8ca-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-144">bit</span><span class="sxs-lookup"><span data-stu-id="5b8ca-144">bit</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-145">Indica si el autor de la llamada está dentro de la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="5b8ca-146">1 significa que la persona que llama está dentro de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="5b8ca-147">0 significa que la persona que llama está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="5b8ca-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-149">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-150">Dirección MAC de la interfaz de red que llama.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="5b8ca-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-153">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="5b8ca-154">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5b8ca-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="5b8ca-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-156">int</span><span class="sxs-lookup"><span data-stu-id="5b8ca-156">int</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-157">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="5b8ca-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-160">Dirección IP de la persona que llama según el servicio perimetral de A/V.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="5b8ca-161">Esta dirección puede ser diferente de la CallerIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="5b8ca-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-163">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-164">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="5b8ca-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-166">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-167">Nombre del dispositivo de representación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="5b8ca-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-169">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-170">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="5b8ca-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-172">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-173">Nombre del controlador del dispositivo de representación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="5b8ca-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-175">VARCHAR (256</span><span class="sxs-lookup"><span data-stu-id="5b8ca-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-176">Descripción del controlador WIFI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="5b8ca-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-178">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-179">Versión del controlador WIFI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="5b8ca-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-181">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-182">Detalles de la conexión de red de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-182">Details of caller’s network connection.</span></span> <span data-ttu-id="5b8ca-183">Para obtener más información, consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5b8ca-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="5b8ca-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-185">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-186">Identificador del conjunto de servicios básicos usado por las personas que llaman conexión WiFi.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="5b8ca-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-188">bit</span><span class="sxs-lookup"><span data-stu-id="5b8ca-188">bit</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-189">Indica si la persona que llama se ha conectado a través de una red privada virtual.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="5b8ca-190">1 es una red privada virtual (VPN) y 0 no es una VPN.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="5b8ca-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-193">Dirección IP del destinatario.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-193">IP address of the callee.</span></span> <span data-ttu-id="5b8ca-194">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="5b8ca-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-196">int</span><span class="sxs-lookup"><span data-stu-id="5b8ca-196">int</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-197">Puerto usado por el destinatario.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="5b8ca-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-199">bit</span><span class="sxs-lookup"><span data-stu-id="5b8ca-199">bit</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-200">Indica si el destinatario de la llamada está dentro de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="5b8ca-201">1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="5b8ca-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-203">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-204">Dirección MAC de la interfaz de red que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="5b8ca-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-207">Dirección IP del servicio perimetral A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="5b8ca-208">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5b8ca-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="5b8ca-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-210">int</span><span class="sxs-lookup"><span data-stu-id="5b8ca-210">int</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-211">Puerto usado en el servicio de borde A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="5b8ca-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-214">Dirección IP del destinatario de la llamada tal y como lo indica el servicio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="5b8ca-215">Esta dirección puede ser diferente de la CalleeIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="5b8ca-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-218">Nombre del dispositivo de captura de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="5b8ca-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-220">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-221">Nombre del dispositivo de representación de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="5b8ca-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-223">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-224">Nombre del controlador del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="5b8ca-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-226">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-227">Nombre del controlador del dispositivo de representación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="5b8ca-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-229">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-230">Descripción del controlador WIFI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="5b8ca-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-232">VARCHAR (256</span><span class="sxs-lookup"><span data-stu-id="5b8ca-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-233">Versión del controlador WIFI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="5b8ca-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-235">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-236">Detalles de la conexión de red de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-236">Details of callee’s network connection.</span></span> <span data-ttu-id="5b8ca-237">Para obtener más información, consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5b8ca-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="5b8ca-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-239">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-240">Identificador del conjunto de servicios básicos usado por la conexión WiFi de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="5b8ca-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-242">bit</span><span class="sxs-lookup"><span data-stu-id="5b8ca-242">bit</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-243">Indica si el destinatario de la llamada se conecta a través de una red privada virtual.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="5b8ca-244">1 es una red privada virtual (VPN) y 0 no es una VPN.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="5b8ca-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-246">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-247">OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="5b8ca-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="5b8ca-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-249">int</span><span class="sxs-lookup"><span data-stu-id="5b8ca-249">int</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-250">Este es el ancho de banda real que se aplica a la transmisión de la parte de envío proporcionada, dadas varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.).</span><span class="sxs-lookup"><span data-stu-id="5b8ca-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="5b8ca-251">Esto no debe confundirse con el ancho de banda efectivo porque puede haber un ancho de banda más bajo en función de la estimación del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="5b8ca-252">Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="5b8ca-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-254">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-255">Origen del límite de ancho de banda que se impone.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="5b8ca-256">Describe de dónde viene el límite de ancho de banda (por ejemplo, "servidor de directivas", "convertir servidor" o "modalidad de moda").</span><span class="sxs-lookup"><span data-stu-id="5b8ca-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-257">Autor de llamada</span><span class="sxs-lookup"><span data-stu-id="5b8ca-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-258">bit</span><span class="sxs-lookup"><span data-stu-id="5b8ca-258">bit</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-259">Indica si se recibieron las métricas de la persona que llama; 1 es sí, 0 es no.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-260">Destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="5b8ca-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-261">bit</span><span class="sxs-lookup"><span data-stu-id="5b8ca-261">bit</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-262">Indica si se han recibido métricas del receptor de la llamada; 1 es sí, 0 es no.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="5b8ca-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-264">bit</span><span class="sxs-lookup"><span data-stu-id="5b8ca-264">bit</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-265">Indica si el informe es para una parte de la llamada o para la llamada completa.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="5b8ca-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-267">bit</span><span class="sxs-lookup"><span data-stu-id="5b8ca-267">bit</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-268">Indica si una llamada se ha clasificado como una llamada deficiente (1) o como una buena llamada (0).</span><span class="sxs-lookup"><span data-stu-id="5b8ca-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b8ca-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="5b8ca-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="5b8ca-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-271">Indica si la persona que llama se ha conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).</span><span class="sxs-lookup"><span data-stu-id="5b8ca-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b8ca-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="5b8ca-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="5b8ca-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5b8ca-274">Indica si el usuario ha sido llamado conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).</span><span class="sxs-lookup"><span data-stu-id="5b8ca-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

