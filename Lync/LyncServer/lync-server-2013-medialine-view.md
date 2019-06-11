---
title: 'Lync Server 2013: vista MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d930f3beeeddb5c5582f41c44f1c68ff7f21f18d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="04710-102">Vista MediaLine en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04710-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04710-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="04710-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="04710-104">La vista MediaLine almacena información acerca de cada línea de medios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="04710-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="04710-105">Una sesión de audio normalmente contiene una línea multimedia de audio.</span><span class="sxs-lookup"><span data-stu-id="04710-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="04710-106">Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medio de audio y una línea de medio de vídeo; sin embargo, la sesión podría contener dos líneas multimedia de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="04710-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="04710-107">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="04710-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04710-108">Columna</span><span class="sxs-lookup"><span data-stu-id="04710-108">Column</span></span></th>
<th><span data-ttu-id="04710-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="04710-109">Data Type</span></span></th>
<th><span data-ttu-id="04710-110">sobre</span><span class="sxs-lookup"><span data-stu-id="04710-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04710-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="04710-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="04710-112">datetime</span><span class="sxs-lookup"><span data-stu-id="04710-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="04710-113">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="04710-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="04710-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="04710-115">int</span><span class="sxs-lookup"><span data-stu-id="04710-115">int</span></span></p></td>
<td><p><span data-ttu-id="04710-116">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="04710-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="04710-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="04710-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="04710-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="04710-119">Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="04710-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="04710-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="04710-121">int</span><span class="sxs-lookup"><span data-stu-id="04710-121">int</span></span></p></td>
<td><p><span data-ttu-id="04710-122">Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en indicadores de bits para la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="04710-122">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="04710-123">Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="04710-123">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="04710-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="04710-125">int</span><span class="sxs-lookup"><span data-stu-id="04710-125">int</span></span></p></td>
<td><p><span data-ttu-id="04710-126">Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits para el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-126">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="04710-127">Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="04710-127">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-128">Seguridad</span><span class="sxs-lookup"><span data-stu-id="04710-128">Security</span></span></p></td>
<td><p><span data-ttu-id="04710-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="04710-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="04710-130">Perfil de seguridad en uso.</span><span class="sxs-lookup"><span data-stu-id="04710-130">Security profile in use.</span></span> <span data-ttu-id="04710-131">0 es ninguno, 1 es SRTP, 2 es v1.</span><span class="sxs-lookup"><span data-stu-id="04710-131">0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-132">Transport</span><span class="sxs-lookup"><span data-stu-id="04710-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="04710-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="04710-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="04710-134">Tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="04710-134">Transport type.</span></span> <span data-ttu-id="04710-135">0 es UDP, 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="04710-135">0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="04710-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="04710-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="04710-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="04710-138">Dirección IP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-138">IP address of the caller.</span></span> <span data-ttu-id="04710-139">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="04710-139">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="04710-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="04710-141">int</span><span class="sxs-lookup"><span data-stu-id="04710-141">int</span></span></p></td>
<td><p><span data-ttu-id="04710-142">Puerto usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="04710-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="04710-144">bit</span><span class="sxs-lookup"><span data-stu-id="04710-144">bit</span></span></p></td>
<td><p><span data-ttu-id="04710-145">Indica si el autor de la llamada está dentro de la red de la organización.</span><span class="sxs-lookup"><span data-stu-id="04710-145">Indicates whether or not the caller is inside the organization network.</span></span> <span data-ttu-id="04710-146">1 significa que la persona que llama está dentro de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="04710-146">1 means that the caller is inside the enterprise network.</span></span> <span data-ttu-id="04710-147">0 significa que la persona que llama está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="04710-147">0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="04710-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="04710-149">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-150">Dirección MAC de la interfaz de red que llama.</span><span class="sxs-lookup"><span data-stu-id="04710-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="04710-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="04710-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="04710-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="04710-153">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="04710-154">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="04710-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="04710-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="04710-156">int</span><span class="sxs-lookup"><span data-stu-id="04710-156">int</span></span></p></td>
<td><p><span data-ttu-id="04710-157">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="04710-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="04710-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="04710-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="04710-160">Dirección IP de la persona que llama según el servicio perimetral de A/V.</span><span class="sxs-lookup"><span data-stu-id="04710-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="04710-161">Esta dirección puede ser diferente de la CallerIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="04710-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="04710-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="04710-163">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-164">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="04710-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="04710-166">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-167">Nombre del dispositivo de representación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="04710-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="04710-169">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-170">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="04710-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="04710-172">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-173">Nombre del controlador del dispositivo de representación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="04710-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="04710-175">VARCHAR (256</span><span class="sxs-lookup"><span data-stu-id="04710-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="04710-176">Descripción del controlador WIFI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="04710-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="04710-178">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-179">Versión del controlador WIFI del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="04710-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="04710-181">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-182">Detalles de la conexión de red de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="04710-182">Details of caller’s network connection.</span></span> <span data-ttu-id="04710-183">Para obtener más información, consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="04710-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="04710-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="04710-185">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-186">Identificador del conjunto de servicios básicos usado por las personas que llaman conexión WiFi.</span><span class="sxs-lookup"><span data-stu-id="04710-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="04710-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="04710-188">bit</span><span class="sxs-lookup"><span data-stu-id="04710-188">bit</span></span></p></td>
<td><p><span data-ttu-id="04710-189">Indica si la persona que llama se ha conectado a través de una red privada virtual.</span><span class="sxs-lookup"><span data-stu-id="04710-189">Indicates whether the caller connected over a virtual private network.</span></span> <span data-ttu-id="04710-190">1 es una red privada virtual (VPN) y 0 no es una VPN.</span><span class="sxs-lookup"><span data-stu-id="04710-190">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="04710-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="04710-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="04710-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="04710-193">Dirección IP del destinatario.</span><span class="sxs-lookup"><span data-stu-id="04710-193">IP address of the callee.</span></span> <span data-ttu-id="04710-194">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="04710-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="04710-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="04710-196">int</span><span class="sxs-lookup"><span data-stu-id="04710-196">int</span></span></p></td>
<td><p><span data-ttu-id="04710-197">Puerto usado por el destinatario.</span><span class="sxs-lookup"><span data-stu-id="04710-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="04710-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="04710-199">bit</span><span class="sxs-lookup"><span data-stu-id="04710-199">bit</span></span></p></td>
<td><p><span data-ttu-id="04710-200">Indica si el destinatario de la llamada está dentro de la red empresarial.</span><span class="sxs-lookup"><span data-stu-id="04710-200">Indicates whether the callee is inside the enterprise network.</span></span> <span data-ttu-id="04710-201">1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="04710-201">1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="04710-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="04710-203">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-204">Dirección MAC de la interfaz de red que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="04710-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="04710-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="04710-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="04710-207">Dirección IP del servicio perimetral A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="04710-208">Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="04710-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="04710-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="04710-210">int</span><span class="sxs-lookup"><span data-stu-id="04710-210">int</span></span></p></td>
<td><p><span data-ttu-id="04710-211">Puerto usado en el servicio de borde A/V que usa el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="04710-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="04710-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="04710-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="04710-214">Dirección IP del destinatario de la llamada tal y como lo indica el servicio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="04710-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="04710-215">Esta dirección puede ser diferente de la CalleeIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="04710-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="04710-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="04710-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="04710-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="04710-218">Nombre del dispositivo de captura de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="04710-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="04710-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="04710-220">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-221">Nombre del dispositivo de representación de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="04710-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="04710-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="04710-223">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-224">Nombre del controlador del dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="04710-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="04710-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="04710-226">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-227">Nombre del controlador del dispositivo de representación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04710-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="04710-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="04710-229">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-230">Descripción del controlador WIFI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="04710-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="04710-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="04710-232">VARCHAR (256</span><span class="sxs-lookup"><span data-stu-id="04710-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="04710-233">Versión del controlador WIFI de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="04710-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="04710-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="04710-235">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-236">Detalles de la conexión de red de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="04710-236">Details of callee’s network connection.</span></span> <span data-ttu-id="04710-237">Para obtener más información, consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="04710-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="04710-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="04710-239">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-240">Identificador del conjunto de servicios básicos usado por la conexión WiFi de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="04710-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="04710-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="04710-242">bit</span><span class="sxs-lookup"><span data-stu-id="04710-242">bit</span></span></p></td>
<td><p><span data-ttu-id="04710-243">Indica si el destinatario de la llamada se conecta a través de una red privada virtual.</span><span class="sxs-lookup"><span data-stu-id="04710-243">Indicates whether the callee connected over a virtual private network.</span></span> <span data-ttu-id="04710-244">1 es una red privada virtual (VPN) y 0 no es una VPN.</span><span class="sxs-lookup"><span data-stu-id="04710-244">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="04710-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="04710-246">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="04710-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="04710-247">OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="04710-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="04710-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="04710-249">int</span><span class="sxs-lookup"><span data-stu-id="04710-249">int</span></span></p></td>
<td><p><span data-ttu-id="04710-250">Este es el ancho de banda real que se aplica a la transmisión de la parte de envío proporcionada, dadas varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.).</span><span class="sxs-lookup"><span data-stu-id="04710-250">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.).</span></span> <span data-ttu-id="04710-251">Esto no debe confundirse con el ancho de banda efectivo porque puede haber un ancho de banda más bajo en función de la estimación del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="04710-251">This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="04710-252">Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="04710-252">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="04710-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="04710-254">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="04710-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="04710-255">Origen del límite de ancho de banda que se impone.</span><span class="sxs-lookup"><span data-stu-id="04710-255">Source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="04710-256">Describe de dónde viene el límite de ancho de banda (por ejemplo, "servidor de directivas", "convertir servidor" o "modalidad de moda").</span><span class="sxs-lookup"><span data-stu-id="04710-256">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-257">Autor de llamada</span><span class="sxs-lookup"><span data-stu-id="04710-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="04710-258">bit</span><span class="sxs-lookup"><span data-stu-id="04710-258">bit</span></span></p></td>
<td><p><span data-ttu-id="04710-259">Indica si se recibieron las métricas de la persona que llama; 1 es sí, 0 es no.</span><span class="sxs-lookup"><span data-stu-id="04710-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-260">Destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="04710-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="04710-261">bit</span><span class="sxs-lookup"><span data-stu-id="04710-261">bit</span></span></p></td>
<td><p><span data-ttu-id="04710-262">Indica si se han recibido métricas del receptor de la llamada; 1 es sí, 0 es no.</span><span class="sxs-lookup"><span data-stu-id="04710-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="04710-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="04710-264">bit</span><span class="sxs-lookup"><span data-stu-id="04710-264">bit</span></span></p></td>
<td><p><span data-ttu-id="04710-265">Indica si el informe es para una parte de la llamada o para la llamada completa.</span><span class="sxs-lookup"><span data-stu-id="04710-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="04710-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="04710-267">bit</span><span class="sxs-lookup"><span data-stu-id="04710-267">bit</span></span></p></td>
<td><p><span data-ttu-id="04710-268">Indica si una llamada se ha clasificado como una llamada deficiente (1) o como una buena llamada (0).</span><span class="sxs-lookup"><span data-stu-id="04710-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04710-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="04710-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="04710-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="04710-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="04710-271">Indica si la persona que llama se ha conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).</span><span class="sxs-lookup"><span data-stu-id="04710-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04710-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="04710-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="04710-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="04710-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="04710-274">Indica si el usuario ha sido llamado conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).</span><span class="sxs-lookup"><span data-stu-id="04710-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

