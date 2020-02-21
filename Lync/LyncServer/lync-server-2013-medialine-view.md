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
ms.openlocfilehash: 21fa89b5afe53937ee515dac45053dbd84ae12ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="2f954-102">Vista MediaLine en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f954-102">MediaLine view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f954-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="2f954-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="2f954-104">La vista MediaLine almacena información acerca de cada línea de medios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f954-104">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="2f954-105">Una sesión de audio normalmente contiene una línea de medios de audio.</span><span class="sxs-lookup"><span data-stu-id="2f954-105">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="2f954-106">Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión podría contener dos líneas de medios de vídeo si se usa un dispositivo de conferencias o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="2f954-106">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="2f954-107">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f954-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f954-108">Columna</span><span class="sxs-lookup"><span data-stu-id="2f954-108">Column</span></span></th>
<th><span data-ttu-id="2f954-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2f954-109">Data Type</span></span></th>
<th><span data-ttu-id="2f954-110">detalles</span><span class="sxs-lookup"><span data-stu-id="2f954-110">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f954-111">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="2f954-111">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="2f954-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2f954-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="2f954-113">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2f954-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-114">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="2f954-114">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="2f954-115">int</span><span class="sxs-lookup"><span data-stu-id="2f954-115">int</span></span></p></td>
<td><p><span data-ttu-id="2f954-116">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2f954-116">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-117">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="2f954-117">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="2f954-118">tinyint</span><span class="sxs-lookup"><span data-stu-id="2f954-118">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2f954-119">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2f954-119">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-120">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="2f954-120">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="2f954-121">int</span><span class="sxs-lookup"><span data-stu-id="2f954-121">int</span></span></p></td>
<td><p><span data-ttu-id="2f954-p102">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="2f954-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-124">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="2f954-124">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="2f954-125">int</span><span class="sxs-lookup"><span data-stu-id="2f954-125">int</span></span></p></td>
<td><p><span data-ttu-id="2f954-p103">Información acerca del proceso de establecimiento interactivo de conectividad (ICE), proceso descrito en indicadores de bits para el destinatario de la llamada. Para obtener detalles, consulte el protocolo de servidor de supervisión de calidad de experiencia.</span><span class="sxs-lookup"><span data-stu-id="2f954-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-128">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2f954-128">Security</span></span></p></td>
<td><p><span data-ttu-id="2f954-129">tinyint</span><span class="sxs-lookup"><span data-stu-id="2f954-129">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2f954-p104">Perfil de seguridad en uso. 0 es NONE, 1 es SRTP, 2 es V1.</span><span class="sxs-lookup"><span data-stu-id="2f954-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-132">Transport</span><span class="sxs-lookup"><span data-stu-id="2f954-132">Transport</span></span></p></td>
<td><p><span data-ttu-id="2f954-133">tinyint</span><span class="sxs-lookup"><span data-stu-id="2f954-133">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2f954-p105">Tipo de transporte. 0 es UDP, 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="2f954-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-136">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="2f954-136">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="2f954-137">var (50)</span><span class="sxs-lookup"><span data-stu-id="2f954-137">var(50)</span></span></p></td>
<td><p><span data-ttu-id="2f954-p106">Dirección IP del autor de la llamada. Esta puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="2f954-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-140">CallerPort</span><span class="sxs-lookup"><span data-stu-id="2f954-140">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="2f954-141">int</span><span class="sxs-lookup"><span data-stu-id="2f954-141">int</span></span></p></td>
<td><p><span data-ttu-id="2f954-142">Puerto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-142">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-143">CallerInside</span><span class="sxs-lookup"><span data-stu-id="2f954-143">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="2f954-144">bit</span><span class="sxs-lookup"><span data-stu-id="2f954-144">bit</span></span></p></td>
<td><p><span data-ttu-id="2f954-p107">Indica si el autor de la llamada está o no dentro de la red la organización. 1 significa que el autor de la llamada se encuentra dentro de la red de empresa. 0 significa que el autor de la llamada se encuentra fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="2f954-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-148">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="2f954-148">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="2f954-149">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-149">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-150">Dirección MAC de la interfaz de red usada por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-150">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-151">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="2f954-151">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="2f954-152">var (50)</span><span class="sxs-lookup"><span data-stu-id="2f954-152">var(50)</span></span></p></td>
<td><p><span data-ttu-id="2f954-153">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-153">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="2f954-154">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f954-154">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-155">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="2f954-155">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="2f954-156">int</span><span class="sxs-lookup"><span data-stu-id="2f954-156">int</span></span></p></td>
<td><p><span data-ttu-id="2f954-157">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-157">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-158">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="2f954-158">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="2f954-159">var (50)</span><span class="sxs-lookup"><span data-stu-id="2f954-159">var(50)</span></span></p></td>
<td><p><span data-ttu-id="2f954-160">Dirección IP del autor de llamada según la notifica el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="2f954-160">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="2f954-161">Esta dirección puede ser diferente de CallerIPAddr si el cliente se encuentra detrás de una NAT por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2f954-161">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-162">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="2f954-162">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="2f954-163">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-163">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-164">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-164">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-165">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="2f954-165">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="2f954-166">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-166">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-167">Nombre del dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-167">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-168">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="2f954-168">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="2f954-169">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-169">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-170">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-170">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-171">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="2f954-171">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="2f954-172">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-172">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-173">Nombre de controlador de dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-173">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-174">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="2f954-174">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="2f954-175">VARCHAR (256</span><span class="sxs-lookup"><span data-stu-id="2f954-175">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="2f954-176">Descripción del controlador Wifi del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-176">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-177">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="2f954-177">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="2f954-178">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-178">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-179">Versión del controlador Wifi del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-179">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-180">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="2f954-180">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="2f954-181">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-181">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-182">Detalles de la conexión de red del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-182">Details of caller’s network connection.</span></span> <span data-ttu-id="2f954-183">Consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f954-183">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-184">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="2f954-184">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="2f954-185">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-185">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-186">Identificador de conjunto de servicio básico usado por conexión WiFi de autores de llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-186">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-187">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="2f954-187">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="2f954-188">bit</span><span class="sxs-lookup"><span data-stu-id="2f954-188">bit</span></span></p></td>
<td><p><span data-ttu-id="2f954-p111">Indica si el autor de llamada se conectó a través de una red privada virtual. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.</span><span class="sxs-lookup"><span data-stu-id="2f954-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-191">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="2f954-191">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="2f954-192">var (50)</span><span class="sxs-lookup"><span data-stu-id="2f954-192">var(50)</span></span></p></td>
<td><p><span data-ttu-id="2f954-193">Dirección IP del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-193">IP address of the callee.</span></span> <span data-ttu-id="2f954-194">Esta puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="2f954-194">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-195">CalleePort</span><span class="sxs-lookup"><span data-stu-id="2f954-195">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="2f954-196">int</span><span class="sxs-lookup"><span data-stu-id="2f954-196">int</span></span></p></td>
<td><p><span data-ttu-id="2f954-197">Puerto del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-197">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-198">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="2f954-198">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="2f954-199">bit</span><span class="sxs-lookup"><span data-stu-id="2f954-199">bit</span></span></p></td>
<td><p><span data-ttu-id="2f954-p113">Indica si el autor de la llamada se encuentra dentro de la red de empresa. 1 significa el destinatario de la llamada dentro de la red de empresa, 0 significa el destinatario de la llamada fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="2f954-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-202">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="2f954-202">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="2f954-203">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-203">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-204">Dirección MAC de la interfaz de red usada por el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-204">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-205">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="2f954-205">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="2f954-206">var (50)</span><span class="sxs-lookup"><span data-stu-id="2f954-206">var(50)</span></span></p></td>
<td><p><span data-ttu-id="2f954-207">Dirección IP del servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-207">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="2f954-208">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f954-208">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-209">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="2f954-209">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="2f954-210">int</span><span class="sxs-lookup"><span data-stu-id="2f954-210">int</span></span></p></td>
<td><p><span data-ttu-id="2f954-211">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-211">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-212">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="2f954-212">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="2f954-213">var (50)</span><span class="sxs-lookup"><span data-stu-id="2f954-213">var(50)</span></span></p></td>
<td><p><span data-ttu-id="2f954-214">Dirección IP del destinatario de llamada según lo notifica el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="2f954-214">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="2f954-215">Esta dirección puede ser diferente de CalleeIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2f954-215">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-216">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="2f954-216">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="2f954-217">var (50)</span><span class="sxs-lookup"><span data-stu-id="2f954-217">var(50)</span></span></p></td>
<td><p><span data-ttu-id="2f954-218">Nombre del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-218">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-219">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="2f954-219">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="2f954-220">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-220">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-221">Nombre de dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-221">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-222">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="2f954-222">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="2f954-223">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-223">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-224">Nombre del controlador del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-224">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-225">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="2f954-225">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="2f954-226">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-226">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-227">Nombre de controlador de dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-227">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-228">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="2f954-228">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="2f954-229">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-229">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-230">Descripción del controlador Wifi del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-230">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-231">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="2f954-231">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="2f954-232">VARCHAR (256</span><span class="sxs-lookup"><span data-stu-id="2f954-232">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="2f954-233">Versión del controlador Wifi del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-233">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-234">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="2f954-234">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="2f954-235">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-235">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-236">Detalles de la conexión de red del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-236">Details of callee’s network connection.</span></span> <span data-ttu-id="2f954-237">Consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f954-237">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-238">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="2f954-238">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="2f954-239">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-239">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-240">Identificador de conjunto de servicio básico usado por la conexión WiFi del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2f954-240">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-241">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="2f954-241">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="2f954-242">bit</span><span class="sxs-lookup"><span data-stu-id="2f954-242">bit</span></span></p></td>
<td><p><span data-ttu-id="2f954-p117">Indica si el destinatario de la llamada se conectó por una red privada virtual. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.</span><span class="sxs-lookup"><span data-stu-id="2f954-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-245">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="2f954-245">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="2f954-246">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="2f954-246">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="2f954-247">MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="2f954-247">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-248">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="2f954-248">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="2f954-249">int</span><span class="sxs-lookup"><span data-stu-id="2f954-249">int</span></span></p></td>
<td><p><span data-ttu-id="2f954-p118">Este es el ancho de banda real aplicado a la secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="2f954-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-253">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="2f954-253">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="2f954-254">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="2f954-254">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2f954-p119">Origen del límite de ancho de banda impuesto. Describe de dónde proviene el límite de ancho de banda (por ejemplo, “Servidor de directivas”, “Servidor TURN” o “Modalidad”).</span><span class="sxs-lookup"><span data-stu-id="2f954-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-257">Caller</span><span class="sxs-lookup"><span data-stu-id="2f954-257">Caller</span></span></p></td>
<td><p><span data-ttu-id="2f954-258">bit</span><span class="sxs-lookup"><span data-stu-id="2f954-258">bit</span></span></p></td>
<td><p><span data-ttu-id="2f954-259">Indica si se han recibido las métricas del autor de la llamada. 1 indica que sí, 0 que no.</span><span class="sxs-lookup"><span data-stu-id="2f954-259">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-260">Destinatario</span><span class="sxs-lookup"><span data-stu-id="2f954-260">Callee</span></span></p></td>
<td><p><span data-ttu-id="2f954-261">bit</span><span class="sxs-lookup"><span data-stu-id="2f954-261">bit</span></span></p></td>
<td><p><span data-ttu-id="2f954-262">Indica si se han recibido las métricas del destinatario de la llamada. 1 indica que sí, 0 que no.</span><span class="sxs-lookup"><span data-stu-id="2f954-262">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-263">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="2f954-263">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="2f954-264">bit</span><span class="sxs-lookup"><span data-stu-id="2f954-264">bit</span></span></p></td>
<td><p><span data-ttu-id="2f954-265">Indica si el informe es para una parte de la llamada o para la llamada completa.</span><span class="sxs-lookup"><span data-stu-id="2f954-265">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-266">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="2f954-266">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="2f954-267">bit</span><span class="sxs-lookup"><span data-stu-id="2f954-267">bit</span></span></p></td>
<td><p><span data-ttu-id="2f954-268">Indica si una llamada se clasificó como deficiente (1) o como llamada correcta (0).</span><span class="sxs-lookup"><span data-stu-id="2f954-268">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f954-269">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="2f954-269">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="2f954-270">tinyint</span><span class="sxs-lookup"><span data-stu-id="2f954-270">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2f954-271">Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</span><span class="sxs-lookup"><span data-stu-id="2f954-271">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f954-272">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="2f954-272">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="2f954-273">tinyint</span><span class="sxs-lookup"><span data-stu-id="2f954-273">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2f954-274">Indica si el usuario llamado se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE)</span><span class="sxs-lookup"><span data-stu-id="2f954-274">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

