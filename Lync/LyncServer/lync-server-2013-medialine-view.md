---
title: 'Lync Server 2013: vista de MediaLine'
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
ms.openlocfilehash: f1b8cac172b4973f86916269585d2d9b02cdc728
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505737"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="b91ad-102">Vista MediaLine en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b91ad-102">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b91ad-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b91ad-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b91ad-104">La vista MediaLine almacena información acerca de cada línea de medios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b91ad-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="b91ad-105">Una sesión de audio normalmente contiene una línea de medios de audio.</span><span class="sxs-lookup"><span data-stu-id="b91ad-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="b91ad-106">Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión podría contener dos líneas de medios de vídeo si se usa un dispositivo de conferencias o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="b91ad-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="b91ad-107">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b91ad-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b91ad-108">Columna</span><span class="sxs-lookup"><span data-stu-id="b91ad-108">Column</span></span></th>
<th><span data-ttu-id="b91ad-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="b91ad-109">Data Type</span></span></th>
<th><span data-ttu-id="b91ad-110">details</span><span class="sxs-lookup"><span data-stu-id="b91ad-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="b91ad-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="b91ad-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b91ad-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b91ad-113">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b91ad-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="b91ad-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="b91ad-115">entero</span><span class="sxs-lookup"><span data-stu-id="b91ad-115">int</span></span></p></td>
<td><p><span data-ttu-id="b91ad-116">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b91ad-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="b91ad-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="b91ad-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="b91ad-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b91ad-119">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b91ad-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="b91ad-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="b91ad-121">entero</span><span class="sxs-lookup"><span data-stu-id="b91ad-121">int</span></span></p></td>
<td><p><span data-ttu-id="b91ad-p102">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="b91ad-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="b91ad-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="b91ad-125">entero</span><span class="sxs-lookup"><span data-stu-id="b91ad-125">int</span></span></p></td>
<td><p><span data-ttu-id="b91ad-p103">Información acerca del proceso de establecimiento interactivo de conectividad (ICE), proceso descrito en indicadores de bits para el destinatario de la llamada. Para obtener detalles, consulte el protocolo de servidor de supervisión de calidad de experiencia.</span><span class="sxs-lookup"><span data-stu-id="b91ad-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-128">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b91ad-128">Security</span></span></p></td>
<td><p><span data-ttu-id="b91ad-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="b91ad-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b91ad-p104">Perfil de seguridad en uso. 0 es NONE, 1 es SRTP, 2 es V1.</span><span class="sxs-lookup"><span data-stu-id="b91ad-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-132">Transport</span><span class="sxs-lookup"><span data-stu-id="b91ad-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="b91ad-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="b91ad-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b91ad-p105">Tipo de transporte. 0 es UDP, 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="b91ad-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="b91ad-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b91ad-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="b91ad-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-p106">Dirección IP del autor de la llamada. Esta puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="b91ad-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="b91ad-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="b91ad-141">entero</span><span class="sxs-lookup"><span data-stu-id="b91ad-141">int</span></span></p></td>
<td><p><span data-ttu-id="b91ad-142">Puerto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="b91ad-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="b91ad-144">bit</span><span class="sxs-lookup"><span data-stu-id="b91ad-144">bit</span></span></p></td>
<td><p><span data-ttu-id="b91ad-p107">Indica si el autor de la llamada está o no dentro de la red la organización. 1 significa que el autor de la llamada se encuentra dentro de la red de empresa. 0 significa que el autor de la llamada se encuentra fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="b91ad-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="b91ad-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="b91ad-149">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-150">Dirección MAC de la interfaz de red usada por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="b91ad-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b91ad-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="b91ad-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-153">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="b91ad-154">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b91ad-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="b91ad-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="b91ad-156">entero</span><span class="sxs-lookup"><span data-stu-id="b91ad-156">int</span></span></p></td>
<td><p><span data-ttu-id="b91ad-157">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="b91ad-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b91ad-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="b91ad-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-160">Dirección IP del autor de llamada según la notifica el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="b91ad-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="b91ad-161">Esta dirección puede ser diferente de CallerIPAddr si el cliente se encuentra detrás de una NAT por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b91ad-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="b91ad-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="b91ad-163">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-164">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="b91ad-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="b91ad-166">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-167">Nombre del dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="b91ad-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="b91ad-169">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-170">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="b91ad-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="b91ad-172">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-173">Nombre de controlador de dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="b91ad-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="b91ad-175">VARCHAR (256</span><span class="sxs-lookup"><span data-stu-id="b91ad-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="b91ad-176">Descripción del controlador Wifi del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="b91ad-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="b91ad-178">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-179">Versión del controlador Wifi del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="b91ad-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="b91ad-181">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-182">Detalles de la conexión de red del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-182">Details of caller’s network connection.</span></span> <span data-ttu-id="b91ad-183">Consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b91ad-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="b91ad-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="b91ad-185">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-186">Identificador de conjunto de servicio básico usado por conexión WiFi de autores de llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="b91ad-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="b91ad-188">bit</span><span class="sxs-lookup"><span data-stu-id="b91ad-188">bit</span></span></p></td>
<td><p><span data-ttu-id="b91ad-p111">Indica si el autor de llamada se conectó a través de una red privada virtual. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.</span><span class="sxs-lookup"><span data-stu-id="b91ad-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="b91ad-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b91ad-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="b91ad-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-193">Dirección IP del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-193">IP address of the callee.</span></span> <span data-ttu-id="b91ad-194">Esta puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="b91ad-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="b91ad-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="b91ad-196">entero</span><span class="sxs-lookup"><span data-stu-id="b91ad-196">int</span></span></p></td>
<td><p><span data-ttu-id="b91ad-197">Puerto del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="b91ad-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="b91ad-199">bit</span><span class="sxs-lookup"><span data-stu-id="b91ad-199">bit</span></span></p></td>
<td><p><span data-ttu-id="b91ad-p113">Indica si el autor de la llamada se encuentra dentro de la red de empresa. 1 significa el destinatario de la llamada dentro de la red de empresa, 0 significa el destinatario de la llamada fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="b91ad-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="b91ad-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="b91ad-203">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-204">Dirección MAC de la interfaz de red usada por el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="b91ad-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b91ad-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="b91ad-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-207">Dirección IP del servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="b91ad-208">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b91ad-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="b91ad-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="b91ad-210">entero</span><span class="sxs-lookup"><span data-stu-id="b91ad-210">int</span></span></p></td>
<td><p><span data-ttu-id="b91ad-211">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="b91ad-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="b91ad-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="b91ad-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-214">Dirección IP del destinatario de llamada según lo notifica el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="b91ad-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="b91ad-215">Esta dirección puede ser diferente de CalleeIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b91ad-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="b91ad-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="b91ad-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="b91ad-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-218">Nombre del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="b91ad-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="b91ad-220">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-221">Nombre de dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="b91ad-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="b91ad-223">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-224">Nombre del controlador del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="b91ad-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="b91ad-226">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-227">Nombre de controlador de dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="b91ad-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="b91ad-229">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-230">Descripción del controlador Wifi del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="b91ad-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="b91ad-232">VARCHAR (256</span><span class="sxs-lookup"><span data-stu-id="b91ad-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="b91ad-233">Versión del controlador Wifi del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="b91ad-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="b91ad-235">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-236">Detalles de la conexión de red del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-236">Details of callee’s network connection.</span></span> <span data-ttu-id="b91ad-237">Consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b91ad-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="b91ad-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="b91ad-239">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-240">Identificador de conjunto de servicio básico usado por la conexión WiFi del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b91ad-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="b91ad-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="b91ad-242">bit</span><span class="sxs-lookup"><span data-stu-id="b91ad-242">bit</span></span></p></td>
<td><p><span data-ttu-id="b91ad-p117">Indica si el destinatario de la llamada se conectó por una red privada virtual. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.</span><span class="sxs-lookup"><span data-stu-id="b91ad-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="b91ad-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="b91ad-246">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="b91ad-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-247">MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="b91ad-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="b91ad-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="b91ad-249">entero</span><span class="sxs-lookup"><span data-stu-id="b91ad-249">int</span></span></p></td>
<td><p><span data-ttu-id="b91ad-p118">Este es el ancho de banda real aplicado a la secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="b91ad-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="b91ad-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="b91ad-254">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="b91ad-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b91ad-p119">Origen del límite de ancho de banda impuesto. Describe de dónde proviene el límite de ancho de banda (por ejemplo, “Servidor de directivas”, “Servidor TURN” o “Modalidad”).</span><span class="sxs-lookup"><span data-stu-id="b91ad-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-257">Caller</span><span class="sxs-lookup"><span data-stu-id="b91ad-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="b91ad-258">bit</span><span class="sxs-lookup"><span data-stu-id="b91ad-258">bit</span></span></p></td>
<td><p><span data-ttu-id="b91ad-259">Indica si se han recibido las métricas del autor de la llamada. 1 indica que sí, 0 que no.</span><span class="sxs-lookup"><span data-stu-id="b91ad-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-260">Destinatario</span><span class="sxs-lookup"><span data-stu-id="b91ad-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="b91ad-261">bit</span><span class="sxs-lookup"><span data-stu-id="b91ad-261">bit</span></span></p></td>
<td><p><span data-ttu-id="b91ad-262">Indica si se han recibido las métricas del destinatario de la llamada. 1 indica que sí, 0 que no.</span><span class="sxs-lookup"><span data-stu-id="b91ad-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="b91ad-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="b91ad-264">bit</span><span class="sxs-lookup"><span data-stu-id="b91ad-264">bit</span></span></p></td>
<td><p><span data-ttu-id="b91ad-265">Indica si el informe es para una parte de la llamada o para la llamada completa.</span><span class="sxs-lookup"><span data-stu-id="b91ad-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="b91ad-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="b91ad-267">bit</span><span class="sxs-lookup"><span data-stu-id="b91ad-267">bit</span></span></p></td>
<td><p><span data-ttu-id="b91ad-268">Indica si una llamada se clasificó como deficiente (1) o como llamada correcta (0).</span><span class="sxs-lookup"><span data-stu-id="b91ad-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b91ad-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="b91ad-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="b91ad-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="b91ad-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b91ad-271">Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</span><span class="sxs-lookup"><span data-stu-id="b91ad-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b91ad-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="b91ad-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="b91ad-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="b91ad-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b91ad-274">Indica si el usuario llamado se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE)</span><span class="sxs-lookup"><span data-stu-id="b91ad-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

