---
title: 'Lync Server 2013: vista de MediaLine'
description: 'Lync Server 2013: vista de MediaLine.'
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
ms.openlocfilehash: 4c61fcc15b46958622e6cddd66427255a6def154
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568686"
---
# <a name="medialine-view-in-lync-server-2013"></a><span data-ttu-id="54ab7-103">Vista MediaLine en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54ab7-103">MediaLine view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54ab7-104">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="54ab7-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="54ab7-105">La vista MediaLine almacena información acerca de cada línea de medios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="54ab7-105">The MediaLine View stores information about each media line in the database.</span></span> <span data-ttu-id="54ab7-106">Una sesión de audio normalmente contiene una línea de medios de audio.</span><span class="sxs-lookup"><span data-stu-id="54ab7-106">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="54ab7-107">Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión podría contener dos líneas de medios de vídeo si se usa un dispositivo de conferencias o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="54ab7-107">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span> <span data-ttu-id="54ab7-108">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54ab7-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54ab7-109">Columna</span><span class="sxs-lookup"><span data-stu-id="54ab7-109">Column</span></span></th>
<th><span data-ttu-id="54ab7-110">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="54ab7-110">Data Type</span></span></th>
<th><span data-ttu-id="54ab7-111">details</span><span class="sxs-lookup"><span data-stu-id="54ab7-111">details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-112">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="54ab7-112">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="54ab7-113">datetime</span><span class="sxs-lookup"><span data-stu-id="54ab7-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="54ab7-114">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="54ab7-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-115">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="54ab7-115">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="54ab7-116">entero</span><span class="sxs-lookup"><span data-stu-id="54ab7-116">int</span></span></p></td>
<td><p><span data-ttu-id="54ab7-117">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="54ab7-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-118">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="54ab7-118">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="54ab7-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="54ab7-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="54ab7-120">Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="54ab7-120">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-121">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="54ab7-121">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="54ab7-122">entero</span><span class="sxs-lookup"><span data-stu-id="54ab7-122">int</span></span></p></td>
<td><p><span data-ttu-id="54ab7-p102">Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="54ab7-p102">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-125">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="54ab7-125">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="54ab7-126">entero</span><span class="sxs-lookup"><span data-stu-id="54ab7-126">int</span></span></p></td>
<td><p><span data-ttu-id="54ab7-p103">Información acerca del proceso de establecimiento interactivo de conectividad (ICE), proceso descrito en indicadores de bits para el destinatario de la llamada. Para obtener detalles, consulte el protocolo de servidor de supervisión de calidad de experiencia.</span><span class="sxs-lookup"><span data-stu-id="54ab7-p103">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-129">Seguridad</span><span class="sxs-lookup"><span data-stu-id="54ab7-129">Security</span></span></p></td>
<td><p><span data-ttu-id="54ab7-130">tinyint</span><span class="sxs-lookup"><span data-stu-id="54ab7-130">tinyint</span></span></p></td>
<td><p><span data-ttu-id="54ab7-p104">Perfil de seguridad en uso. 0 es NONE, 1 es SRTP, 2 es V1.</span><span class="sxs-lookup"><span data-stu-id="54ab7-p104">Security profile in use. 0 is NONE, 1 is SRTP, 2 is V1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-133">Transport</span><span class="sxs-lookup"><span data-stu-id="54ab7-133">Transport</span></span></p></td>
<td><p><span data-ttu-id="54ab7-134">tinyint</span><span class="sxs-lookup"><span data-stu-id="54ab7-134">tinyint</span></span></p></td>
<td><p><span data-ttu-id="54ab7-p105">Tipo de transporte. 0 es UDP, 1 es TCP.</span><span class="sxs-lookup"><span data-stu-id="54ab7-p105">Transport type. 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-137">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="54ab7-137">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="54ab7-138">var (50)</span><span class="sxs-lookup"><span data-stu-id="54ab7-138">var(50)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-p106">Dirección IP del autor de la llamada. Esta puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="54ab7-p106">IP address of the caller. This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-141">CallerPort</span><span class="sxs-lookup"><span data-stu-id="54ab7-141">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="54ab7-142">entero</span><span class="sxs-lookup"><span data-stu-id="54ab7-142">int</span></span></p></td>
<td><p><span data-ttu-id="54ab7-143">Puerto del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-143">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-144">CallerInside</span><span class="sxs-lookup"><span data-stu-id="54ab7-144">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="54ab7-145">bit</span><span class="sxs-lookup"><span data-stu-id="54ab7-145">bit</span></span></p></td>
<td><p><span data-ttu-id="54ab7-p107">Indica si el autor de la llamada está o no dentro de la red la organización. 1 significa que el autor de la llamada se encuentra dentro de la red de empresa. 0 significa que el autor de la llamada se encuentra fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="54ab7-p107">Indicates whether or not the caller is inside the organization network. 1 means that the caller is inside the enterprise network. 0 means that the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-149">CallerMacAddress</span><span class="sxs-lookup"><span data-stu-id="54ab7-149">CallerMacAddress</span></span></p></td>
<td><p><span data-ttu-id="54ab7-150">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-150">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-151">Dirección MAC de la interfaz de red usada por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-151">MAC address of network interface used by caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-152">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="54ab7-152">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="54ab7-153">var (50)</span><span class="sxs-lookup"><span data-stu-id="54ab7-153">var(50)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-154">Dirección IP del servicio perimetral A/V que usa el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-154">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="54ab7-155">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="54ab7-155">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-156">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="54ab7-156">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="54ab7-157">entero</span><span class="sxs-lookup"><span data-stu-id="54ab7-157">int</span></span></p></td>
<td><p><span data-ttu-id="54ab7-158">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-158">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-159">CallerReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="54ab7-159">CallerReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="54ab7-160">var (50)</span><span class="sxs-lookup"><span data-stu-id="54ab7-160">var(50)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-161">Dirección IP del autor de llamada según la notifica el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="54ab7-161">Caller’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="54ab7-162">Esta dirección puede ser diferente de CallerIPAddr si el cliente se encuentra detrás de una NAT por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="54ab7-162">This address may be different that the CallerIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-163">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="54ab7-163">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="54ab7-164">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-164">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-165">Nombre del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-165">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-166">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="54ab7-166">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="54ab7-167">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-167">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-168">Nombre del dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-168">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-169">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="54ab7-169">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="54ab7-170">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-170">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-171">Nombre del controlador del dispositivo de captura del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-171">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-172">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="54ab7-172">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="54ab7-173">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-173">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-174">Nombre de controlador de dispositivo de presentación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-174">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-175">CallerWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="54ab7-175">CallerWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="54ab7-176">VARCHAR (256</span><span class="sxs-lookup"><span data-stu-id="54ab7-176">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="54ab7-177">Descripción del controlador Wifi del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-177">Caller’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-178">CallerWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="54ab7-178">CallerWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="54ab7-179">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-179">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-180">Versión del controlador Wifi del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-180">Caller’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-181">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="54ab7-181">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="54ab7-182">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-182">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-183">Detalles de la conexión de red del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-183">Details of caller’s network connection.</span></span> <span data-ttu-id="54ab7-184">Consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="54ab7-184">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-185">CallerBssid</span><span class="sxs-lookup"><span data-stu-id="54ab7-185">CallerBssid</span></span></p></td>
<td><p><span data-ttu-id="54ab7-186">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-186">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-187">Identificador de conjunto de servicio básico usado por conexión WiFi de autores de llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-187">Basic Service Set Identifier used by callers WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-188">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="54ab7-188">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="54ab7-189">bit</span><span class="sxs-lookup"><span data-stu-id="54ab7-189">bit</span></span></p></td>
<td><p><span data-ttu-id="54ab7-p111">Indica si el autor de llamada se conectó a través de una red privada virtual. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.</span><span class="sxs-lookup"><span data-stu-id="54ab7-p111">Indicates whether the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-192">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="54ab7-192">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="54ab7-193">var (50)</span><span class="sxs-lookup"><span data-stu-id="54ab7-193">var(50)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-194">Dirección IP del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-194">IP address of the callee.</span></span> <span data-ttu-id="54ab7-195">Esta puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="54ab7-195">This can be either an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-196">CalleePort</span><span class="sxs-lookup"><span data-stu-id="54ab7-196">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="54ab7-197">entero</span><span class="sxs-lookup"><span data-stu-id="54ab7-197">int</span></span></p></td>
<td><p><span data-ttu-id="54ab7-198">Puerto del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-198">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-199">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="54ab7-199">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="54ab7-200">bit</span><span class="sxs-lookup"><span data-stu-id="54ab7-200">bit</span></span></p></td>
<td><p><span data-ttu-id="54ab7-p113">Indica si el autor de la llamada se encuentra dentro de la red de empresa. 1 significa el destinatario de la llamada dentro de la red de empresa, 0 significa el destinatario de la llamada fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="54ab7-p113">Indicates whether the callee is inside the enterprise network. 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-203">CalleeMacAddress</span><span class="sxs-lookup"><span data-stu-id="54ab7-203">CalleeMacAddress</span></span></p></td>
<td><p><span data-ttu-id="54ab7-204">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-204">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-205">Dirección MAC de la interfaz de red usada por el destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-205">MAC address of network interface used by callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-206">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="54ab7-206">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="54ab7-207">var (50)</span><span class="sxs-lookup"><span data-stu-id="54ab7-207">var(50)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-208">Dirección IP del servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-208">IP Address of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="54ab7-209">Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="54ab7-209">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-210">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="54ab7-210">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="54ab7-211">entero</span><span class="sxs-lookup"><span data-stu-id="54ab7-211">int</span></span></p></td>
<td><p><span data-ttu-id="54ab7-212">Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-212">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-213">CalleeReflexiveIPAddr</span><span class="sxs-lookup"><span data-stu-id="54ab7-213">CalleeReflexiveIPAddr</span></span></p></td>
<td><p><span data-ttu-id="54ab7-214">var (50)</span><span class="sxs-lookup"><span data-stu-id="54ab7-214">var(50)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-215">Dirección IP del destinatario de llamada según lo notifica el servicio perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="54ab7-215">Callee’s IP address as reported by the A/V Edge service.</span></span> <span data-ttu-id="54ab7-216">Esta dirección puede ser diferente de CalleeIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="54ab7-216">This address may be different that the CalleeIPAddr if the client is located behind a NAT for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-217">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="54ab7-217">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="54ab7-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="54ab7-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-219">Nombre del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-219">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-220">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="54ab7-220">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="54ab7-221">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-221">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-222">Nombre de dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-222">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-223">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="54ab7-223">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="54ab7-224">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-224">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-225">Nombre del controlador del dispositivo de captura del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-225">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-226">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="54ab7-226">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="54ab7-227">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-227">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-228">Nombre de controlador de dispositivo de presentación del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-228">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-229">CalleeWifiDriverDeviceDesc</span><span class="sxs-lookup"><span data-stu-id="54ab7-229">CalleeWifiDriverDeviceDesc</span></span></p></td>
<td><p><span data-ttu-id="54ab7-230">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-230">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-231">Descripción del controlador Wifi del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-231">Callee’s Wifi driver description.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-232">CalleeWifiDriverVersion</span><span class="sxs-lookup"><span data-stu-id="54ab7-232">CalleeWifiDriverVersion</span></span></p></td>
<td><p><span data-ttu-id="54ab7-233">VARCHAR (256</span><span class="sxs-lookup"><span data-stu-id="54ab7-233">varchar(256</span></span></p></td>
<td><p><span data-ttu-id="54ab7-234">Versión del controlador Wifi del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-234">Callee’s Wifi driver version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-235">CalleeNetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="54ab7-235">CalleeNetworkConnectionDetail</span></span></p></td>
<td><p><span data-ttu-id="54ab7-236">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-236">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-237">Detalles de la conexión de red del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-237">Details of callee’s network connection.</span></span> <span data-ttu-id="54ab7-238">Consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="54ab7-238">See the <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-239">CalleeBssid</span><span class="sxs-lookup"><span data-stu-id="54ab7-239">CalleeBssid</span></span></p></td>
<td><p><span data-ttu-id="54ab7-240">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-240">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-241">Identificador de conjunto de servicio básico usado por la conexión WiFi del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54ab7-241">Basic Service Set Identifier used by callee’s WiFi connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-242">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="54ab7-242">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="54ab7-243">bit</span><span class="sxs-lookup"><span data-stu-id="54ab7-243">bit</span></span></p></td>
<td><p><span data-ttu-id="54ab7-p117">Indica si el destinatario de la llamada se conectó por una red privada virtual. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.</span><span class="sxs-lookup"><span data-stu-id="54ab7-p117">Indicates whether the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-246">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="54ab7-246">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="54ab7-247">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="54ab7-247">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-248">MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</span><span class="sxs-lookup"><span data-stu-id="54ab7-248">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-249">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="54ab7-249">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="54ab7-250">entero</span><span class="sxs-lookup"><span data-stu-id="54ab7-250">int</span></span></p></td>
<td><p><span data-ttu-id="54ab7-p118">Este es el ancho de banda real aplicado a la secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="54ab7-p118">This is the actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, etc.). This should not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-254">AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="54ab7-254">AppliedBandwidthSource</span></span></p></td>
<td><p><span data-ttu-id="54ab7-255">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="54ab7-255">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="54ab7-p119">Origen del límite de ancho de banda impuesto. Describe de dónde proviene el límite de ancho de banda (por ejemplo, “Servidor de directivas”, “Servidor TURN” o “Modalidad”).</span><span class="sxs-lookup"><span data-stu-id="54ab7-p119">Source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-258">Caller</span><span class="sxs-lookup"><span data-stu-id="54ab7-258">Caller</span></span></p></td>
<td><p><span data-ttu-id="54ab7-259">bit</span><span class="sxs-lookup"><span data-stu-id="54ab7-259">bit</span></span></p></td>
<td><p><span data-ttu-id="54ab7-260">Indica si se han recibido las métricas del autor de la llamada. 1 indica que sí, 0 que no.</span><span class="sxs-lookup"><span data-stu-id="54ab7-260">Indicates whether metrics from the caller were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-261">Destinatario</span><span class="sxs-lookup"><span data-stu-id="54ab7-261">Callee</span></span></p></td>
<td><p><span data-ttu-id="54ab7-262">bit</span><span class="sxs-lookup"><span data-stu-id="54ab7-262">bit</span></span></p></td>
<td><p><span data-ttu-id="54ab7-263">Indica si se han recibido las métricas del destinatario de la llamada. 1 indica que sí, 0 que no.</span><span class="sxs-lookup"><span data-stu-id="54ab7-263">Indicates whether metrics from the call receiver were received; 1 is yes, 0 is no.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-264">MidCallReport</span><span class="sxs-lookup"><span data-stu-id="54ab7-264">MidCallReport</span></span></p></td>
<td><p><span data-ttu-id="54ab7-265">bit</span><span class="sxs-lookup"><span data-stu-id="54ab7-265">bit</span></span></p></td>
<td><p><span data-ttu-id="54ab7-266">Indica si el informe es para una parte de la llamada o para la llamada completa.</span><span class="sxs-lookup"><span data-stu-id="54ab7-266">Indicates whether the report is for a portion of the call or for the complete call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-267">ClassifiedPoorCall</span><span class="sxs-lookup"><span data-stu-id="54ab7-267">ClassifiedPoorCall</span></span></p></td>
<td><p><span data-ttu-id="54ab7-268">bit</span><span class="sxs-lookup"><span data-stu-id="54ab7-268">bit</span></span></p></td>
<td><p><span data-ttu-id="54ab7-269">Indica si una llamada se clasificó como deficiente (1) o como llamada correcta (0).</span><span class="sxs-lookup"><span data-stu-id="54ab7-269">Indicates whether a call was classified as a poor call (1) or as a good call (0).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54ab7-270">CallerConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="54ab7-270">CallerConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="54ab7-271">tinyint</span><span class="sxs-lookup"><span data-stu-id="54ab7-271">tinyint</span></span></p></td>
<td><p><span data-ttu-id="54ab7-272">Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</span><span class="sxs-lookup"><span data-stu-id="54ab7-272">Indicates whether the caller connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54ab7-273">CalleeConnectivityICE</span><span class="sxs-lookup"><span data-stu-id="54ab7-273">CalleeConnectivityICE</span></span></p></td>
<td><p><span data-ttu-id="54ab7-274">tinyint</span><span class="sxs-lookup"><span data-stu-id="54ab7-274">tinyint</span></span></p></td>
<td><p><span data-ttu-id="54ab7-275">Indica si el usuario llamado se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE)</span><span class="sxs-lookup"><span data-stu-id="54ab7-275">Indicates whether the user called connected to the network using the ICE protocol (Internet Connectivity Establishment).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

