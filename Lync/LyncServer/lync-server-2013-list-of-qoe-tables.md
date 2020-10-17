---
title: 'Lync Server 2013: lista de tablas de QoE'
description: 'Lync Server 2013: lista de tablas de QoE.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871babf246f616d306a03f84f9134605dd595999
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550046"
---
# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="39831-103">Lista de tablas de QoE en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39831-103">List of QoE tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39831-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="39831-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="39831-105">El esquema de la base de datos incluye las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="39831-105">The database schema consists of the following tables.</span></span>

<span data-ttu-id="39831-106">**Tablas auxiliares**</span><span class="sxs-lookup"><span data-stu-id="39831-106">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39831-107"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="39831-107"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="39831-108"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="39831-108"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39831-109"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabla AppSharingMetricsThreshold en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-109"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-110">Almacena los valores aceptables y óptimos para la métrica Calidad de la experiencia que se usa al compartir aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="39831-110">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-111"><a href="lync-server-2013-codecdescription-table.md">Tabla CodecDescription en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-111"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-112">Asigna identificadores de códecs únicos al códec correspondiente.</span><span class="sxs-lookup"><span data-stu-id="39831-112">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-113"><a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-113"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-114">Asigna direcciones IP a los identificadores de dirección IP únicos que se usan en la base de datos de Calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="39831-114">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-115"><a href="lync-server-2013-networkconnectiondetail-table.md">Tabla NetworkConnectionDetail en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-115"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-116">Asigna tipos de conexión de red a los identificadores de conexión de red que se usan en la base de datos de Calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="39831-116">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-117"><a href="lync-server-2013-purgesettings-table-qoe.md">Tabla PurgeSettings (QoE) en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-117"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-118">Almacena información que especifica si los registros de Calidad de la experiencia no actualizados se eliminarán automáticamente de la base de datos de QoE (así como cuándo se eliminarán).</span><span class="sxs-lookup"><span data-stu-id="39831-118">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-119"><a href="lync-server-2013-traceroute-table.md">TraceRoute tabla en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-119"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-120">Almacena la información de enrutamiento de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="39831-120">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-121"><a href="lync-server-2013-useragentdef-table-qoe.md">Tabla UserAgentDef (QoE) en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-121"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-122">Asigna los identificadores de agente de usuario a los nombres descriptivos del agente.</span><span class="sxs-lookup"><span data-stu-id="39831-122">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-123"><a href="lync-server-2013-videometricsthreshold-table.md">Tabla VideoMetricsThreshold en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-123"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-124">Almacena los valores aceptables y óptimos para la métrica Calidad de la experiencia que se usa con las llamadas de vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-124">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-125"><a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-125"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-126">Almacena las cadenas del agente de usuario del Protocolo de inicio de sesión (SIP) y los tipos de agentes de usuario utilizados en las sesiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-126">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-127"><a href="lync-server-2013-user-table.md">Tabla user en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-127"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-128">Almacena los URI de teléfono, usuario y conferencia utilizados en las sesiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-128">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-129"><a href="lync-server-2013-endpoint-table.md">Tabla Endpoint en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-129"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-130">Almacena los nombres de equipo FQDN de los extremos que participan en las sesiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-130">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-131"><a href="lync-server-2013-pool-table.md">Tabla de grupo en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-131"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-132">Almacena los nombres de los grupos de servidores a los que pertenecen los datos de métricas.</span><span class="sxs-lookup"><span data-stu-id="39831-132">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-133"><a href="lync-server-2013-device-table.md">Tabla Device en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-133"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-134">Almacena los dispositivos de captura y presentación utilizados en las llamadas de audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-134">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-135"><a href="lync-server-2013-devicedriver-table.md">Tabla DeviceDriver en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-135"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-136">Almacena el controlador de los dispositivos de captura y presentación utilizados en las llamadas de audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-136">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-137"><a href="lync-server-2013-conference-table.md">Tabla de conferencia en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-137"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-138">Almacena los URI de conferencia para los escenarios de conferencia o el identificador de diálogo para otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="39831-138">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-139"><a href="lync-server-2013-sessioncorrelation-table.md">Tabla SessionCorrelation en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-139"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-140">Almacena el identificador de correlación de las llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="39831-140">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-141"><a href="lync-server-2013-payloaddescription-table.md">Tabla PayloadDescription en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-141"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-142">Almacena el códec utilizado en las llamadas de audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-142">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-143"><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabla AppliedBandwidthSource en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-143"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-144">Almacena el origen de ancho de banda utilizado en las llamadas de audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-144">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-145"><a href="lync-server-2013-macaddress-table.md">Tabla MacAddress en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-145"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-146">Almacena la dirección MAC de los extremos que participan en las sesiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-146">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-147"><a href="lync-server-2013-dialog-table.md">Tabla de cuadro de diálogo en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-147"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-148">Almacena el identificador de diálogo de las sesiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-148">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-149"><a href="lync-server-2013-region-table.md">Tabla region en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-149"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-150">Almacena la región de red definida en la configuración NCS.</span><span class="sxs-lookup"><span data-stu-id="39831-150">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-151"><a href="lync-server-2013-usersite-table.md">Tabla UserSite en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-151"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-152">Almacena el sitio de red definido en la configuración NCS.</span><span class="sxs-lookup"><span data-stu-id="39831-152">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-153"><a href="lync-server-2013-subnet-table.md">Tabla de subred en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-153"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-154">Almacena la subred definida en la configuración NCS.</span><span class="sxs-lookup"><span data-stu-id="39831-154">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-155"><a href="lync-server-2013-monitoredregionlink-table.md">Tabla MonitoredRegionLink en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-155"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-156">Almacena el vínculo de región definido en la configuración NCS.</span><span class="sxs-lookup"><span data-stu-id="39831-156">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-157"><a href="monitoredusersitelink-table.md">Tabla MonitoredUserSiteLink</a></span><span class="sxs-lookup"><span data-stu-id="39831-157"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="39831-158">Almacena los vínculos de sitios de red definidos en la configuración NCS.</span><span class="sxs-lookup"><span data-stu-id="39831-158">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-159"><a href="lync-server-2013-endpointsubnet-table.md">Tabla EndpointSubnet en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-159"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-160">Almacena la subred del extremo que participa en las sesiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-160">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-161"><a href="lync-server-2013-server-table.md">Tabla Server en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-161"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-162">Almacena el FQDN o la dirección IP del servidor que utilizan los medios.</span><span class="sxs-lookup"><span data-stu-id="39831-162">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="39831-163">**Tablas para datos de métricas**</span><span class="sxs-lookup"><span data-stu-id="39831-163">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39831-164"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="39831-164"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="39831-165"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="39831-165"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39831-166"><a href="lync-server-2013-appsharingstream-table.md">Tabla AppSharingStream en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-166"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-p101">Almacena las métricas de Calidad de la experiencia para los flujos de red usados al compartir aplicaciones. Las métricas de calidad de la experiencia se usan al compartir aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="39831-p101">Stores Quality of Experience metrics for the network streams used for application sharing. Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-169"><a href="lync-server-2013-session-table.md">Tabla Session en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-169"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-170">Almacena información general acerca de una sesión de audio o de audio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-170">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="39831-171">Una sesión se define como un diálogo SIP de audio o vídeo entre dos extremos.</span><span class="sxs-lookup"><span data-stu-id="39831-171">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-172"><a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-172"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-p103">Almacena información acerca de cada línea de medios de una sesión. Una línea de medios es una recopilación de una o varias secuencias de audio y vídeo. Por lo general, una única línea de medios tendrá dos secuencias, de audio o de vídeo.</span><span class="sxs-lookup"><span data-stu-id="39831-p103">Stores information about each media line in a session. A media line is a collection of one or more audio and video streams. Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-176"><a href="lync-server-2013-audiostream-table.md">Tabla AudioStream en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-176"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-177">Almacena métricas de calidad de medios de audio para cada secuencia de audio de la línea de medios.</span><span class="sxs-lookup"><span data-stu-id="39831-177">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-178"><a href="lync-server-2013-audiosignal-table.md">Tabla AudioSignal en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-178"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-179">Almacena métricas de calidad de medios de audio de la línea de medios.</span><span class="sxs-lookup"><span data-stu-id="39831-179">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="39831-180">Esto incluye las métricas de cancelación del eco acústico (AEC) y el control de ganancia automático (AGC).</span><span class="sxs-lookup"><span data-stu-id="39831-180">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-181"><a href="lync-server-2013-videostream-table.md">Tabla Videostream en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-181"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-182">Almacena métricas de calidad de medios de vídeo para cada secuencia de vídeo de la línea de medios.</span><span class="sxs-lookup"><span data-stu-id="39831-182">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-183"><a href="lync-server-2013-audioclientevent-table.md">Tabla AudioClientEvent en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-183"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-184">Almacena métricas de calidad de medios de audio recopiladas desde el evento del cliente.</span><span class="sxs-lookup"><span data-stu-id="39831-184">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-185"><a href="lync-server-2013-videoclientevent-table.md">Tabla VideoClientEvent en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="39831-185"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="39831-186">Almacena métricas de calidad de medios de vídeo recopiladas desde el evento del cliente.</span><span class="sxs-lookup"><span data-stu-id="39831-186">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-187"><strong>Tabla DiagnosticData</strong></span><span class="sxs-lookup"><span data-stu-id="39831-187"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-188">Almacena datos de diagnóstico para uso interno únicamente.</span><span class="sxs-lookup"><span data-stu-id="39831-188">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="39831-189">**Tablas para datos de resumen**</span><span class="sxs-lookup"><span data-stu-id="39831-189">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39831-190"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="39831-190"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="39831-191"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="39831-191"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39831-192"><strong>Tabla ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="39831-192"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-193">Almacena datos de resumen para los servidores; estos datos se usan para los informes QoE (Calidad de la experiencia) únicamente.</span><span class="sxs-lookup"><span data-stu-id="39831-193">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-194"><strong>Tabla UserSummary</strong></span><span class="sxs-lookup"><span data-stu-id="39831-194"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-195">Almacena datos de resumen para los usuarios; estos datos se usan para los informes QoE (Calidad de la experiencia) únicamente.</span><span class="sxs-lookup"><span data-stu-id="39831-195">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-196"><strong>Tabla CallTypeSummary</strong></span><span class="sxs-lookup"><span data-stu-id="39831-196"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-197">Almacena datos de resumen para los tipos de llamada; estos datos se usan para los informes QoE (Calidad de la experiencia) únicamente.</span><span class="sxs-lookup"><span data-stu-id="39831-197">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="39831-198">**Tablas para uso interno del servidor de supervisión**</span><span class="sxs-lookup"><span data-stu-id="39831-198">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39831-199"><strong>Table</strong></span><span class="sxs-lookup"><span data-stu-id="39831-199"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="39831-200"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="39831-200"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39831-201"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="39831-201"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-202">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-202">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-203"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="39831-203"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-204">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-204">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-205"><strong>Tabla FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="39831-205"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-206">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-206">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-207"><strong>Tabla Task</strong></span><span class="sxs-lookup"><span data-stu-id="39831-207"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-208">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-208">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-209"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="39831-209"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-210">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-210">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-211"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="39831-211"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-212">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-212">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-213"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="39831-213"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-214">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-214">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-215"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="39831-215"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-216">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-216">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-217"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="39831-217"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-218">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-218">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-219"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="39831-219"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-220">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-220">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-221"><strong>Tabla CallSummary</strong></span><span class="sxs-lookup"><span data-stu-id="39831-221"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-222">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-222">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-223"><strong>Tabla DeviceCallSumary</strong></span><span class="sxs-lookup"><span data-stu-id="39831-223"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-224">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-224">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-225"><strong>Tabla Tenant</strong></span><span class="sxs-lookup"><span data-stu-id="39831-225"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-226">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39831-227"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="39831-227"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-228">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39831-229"><strong>ASCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="39831-229"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="39831-230">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39831-230">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

