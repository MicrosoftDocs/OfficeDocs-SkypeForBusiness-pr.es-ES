---
title: 'Lync Server 2013: Lista de tablas de QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c82c38a995fd9e847057fedbbce1422085332b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a><span data-ttu-id="87096-102">Lista de tablas de QoE en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87096-102">List of QoE tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87096-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="87096-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="87096-104">El esquema de la base de datos consta de las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="87096-104">The database schema consists of the following tables.</span></span>

<span data-ttu-id="87096-105">**Tablas de soporte técnico**</span><span class="sxs-lookup"><span data-stu-id="87096-105">**Supporting Tables**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87096-106"><strong>Tabla</strong></span><span class="sxs-lookup"><span data-stu-id="87096-106"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="87096-107"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="87096-107"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87096-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabla AppSharingMetricsThreshold en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-108"><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-109">Almacena valores óptimos y aceptables para las métricas de la calidad de la experiencia que se usan con el uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="87096-109">Stores optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-110"><a href="lync-server-2013-codecdescription-table.md">Tabla CodecDescription en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-110"><a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-111">Asigna identificadores de códec únicos a su códec correspondiente.</span><span class="sxs-lookup"><span data-stu-id="87096-111">Maps unique codec identifiers to their corresponding codec.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-112"><a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-112"><a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-113">Asigna direcciones IP a los identificadores de dirección IP única que se usan en otras partes de la base de datos de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="87096-113">Maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-114"><a href="lync-server-2013-networkconnectiondetail-table.md">Tabla NetworkConnectionDetail en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-114"><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-115">Mapas tipos de conexión de red a los identificadores de conexión de red usados en otras partes de la base de datos de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="87096-115">Maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-116"><a href="lync-server-2013-purgesettings-table-qoe.md">Tabla PurgeSettings (QoE) en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-116"><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-117">Almacena información que especifica si (y cuándo) la calidad de los registros de experiencia se eliminará automáticamente de la base de datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="87096-117">Stores information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-118"><a href="lync-server-2013-traceroute-table.md">Tabla TraceRoute en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-118"><a href="lync-server-2013-traceroute-table.md">TraceRoute table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-119">Almacena la información de enrutamiento de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="87096-119">Stores routing information for calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-120"><a href="lync-server-2013-useragentdef-table-qoe.md">Tabla UserAgentDef (QoE) en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-120"><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-121">Asigna identificadores de agente de usuario a los nombres descriptivos del agente.</span><span class="sxs-lookup"><span data-stu-id="87096-121">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-122"><a href="lync-server-2013-videometricsthreshold-table.md">Tabla VideoMetricsThreshold en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-122"><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-123">Almacena valores óptimos y aceptables para las métricas de la calidad de la experiencia que se usan con las videollamadas.</span><span class="sxs-lookup"><span data-stu-id="87096-123">Stores optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-124"><a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-124"><a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-125">Almacena las cadenas y los tipos de UA del agente de usuario del Protocolo de inicio de sesión (SIP) que se usan en sesiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-125">Stores Session Initiation Protocol (SIP) User Agent (UA) strings and UA types used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-126"><a href="lync-server-2013-user-table.md">Tabla User en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-126"><a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-127">Almacena los URI de usuario, Conferencia y teléfono que se usan en las sesiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-127">Stores user, conference, and phone URIs used in audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-128"><a href="lync-server-2013-endpoint-table.md">Tabla Endpoint en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-128"><a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-129">Almacena FQDN de los nombres de los equipos de puntos de conexión que participan en sesiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-129">Stores FQDN computer names of endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-130"><a href="lync-server-2013-pool-table.md">Tabla Pool en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-130"><a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-131">Almacena los nombres de los grupos a los que pertenecen los datos de métrica.</span><span class="sxs-lookup"><span data-stu-id="87096-131">Stores the names of pools to which metrics data belongs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-132"><a href="lync-server-2013-device-table.md">Tabla Device en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-132"><a href="lync-server-2013-device-table.md">Device table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-133">Almacena dispositivos de captura y dispositivos de representación que se usan en una llamada de audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-133">Stores capture devices and render devices which are used in an audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-134"><a href="lync-server-2013-devicedriver-table.md">Tabla DeviceDriver en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-134"><a href="lync-server-2013-devicedriver-table.md">DeviceDriver table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-135">Almacena el controlador para el dispositivo de captura y el dispositivo de representación que se usan en las llamadas de audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-135">Stores driver for the capture device and the render device which are used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-136"><a href="lync-server-2013-conference-table.md">Tabla Conference en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-136"><a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-137">Almacena los URI de conferencia para escenarios de conferencia o DialogID para otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="87096-137">Stores Conference URIs for conference scenarios or DialogID for other scenarios.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-138"><a href="lync-server-2013-sessioncorrelation-table.md">Tabla SessionCorrelation en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-138"><a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-139">Almacena CorrelationID para llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="87096-139">Stores CorrelationID for PSTN calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-140"><a href="lync-server-2013-payloaddescription-table.md">Tabla PayloadDescription en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-140"><a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-141">Almacena el códec usado en las llamadas de audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-141">Stores the Codec used in audio/video calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabla AppliedBandwidthSource en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-142"><a href="lync-server-2013-appliedbandwidthsource-table.md">AppliedBandwidthSource table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-143">Almacena la fuente de ancho de banda que se usa en las llamadas de audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-143">Stores the bandwidth source used in audio/video calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-144"><a href="lync-server-2013-macaddress-table.md">Tabla MacAddress en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-144"><a href="lync-server-2013-macaddress-table.md">MacAddress table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-145">Almacena la dirección MAC de los puntos de conexión que participan en sesiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-145">Stores the MAC address of the endpoints participating in audio and video sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-146"><a href="lync-server-2013-dialog-table.md">Tabla Dialog en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-146"><a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-147">Almacena el identificador de cuadro de diálogo de las sesiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-147">Stores the Dialog ID of audio and video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-148"><a href="lync-server-2013-region-table.md">Tabla Region en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-148"><a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-149">Almacena la región de red definida en NC.</span><span class="sxs-lookup"><span data-stu-id="87096-149">Stores the network region defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-150"><a href="lync-server-2013-usersite-table.md">Tabla UserSite en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-150"><a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-151">Almacena el sitio de red definido en NC Settings.</span><span class="sxs-lookup"><span data-stu-id="87096-151">Stores the network site defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-152"><a href="lync-server-2013-subnet-table.md">Tabla Subnet en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-152"><a href="lync-server-2013-subnet-table.md">Subnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-153">Almacena la subred definida en la configuración de NC.</span><span class="sxs-lookup"><span data-stu-id="87096-153">Stores the subnet defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-154"><a href="lync-server-2013-monitoredregionlink-table.md">Tabla MonitoredRegionLink en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-154"><a href="lync-server-2013-monitoredregionlink-table.md">MonitoredRegionLink table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-155">Almacena el vínculo región definido en NC.</span><span class="sxs-lookup"><span data-stu-id="87096-155">Stores the region link defined in NCS setting.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-156"><a href="monitoredusersitelink-table.md">Tabla MonitoredUserSiteLink</a></span><span class="sxs-lookup"><span data-stu-id="87096-156"><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink table</a></span></span></p></td>
<td><p><span data-ttu-id="87096-157">Almacena los vínculos de sitio de red definidos en NC.</span><span class="sxs-lookup"><span data-stu-id="87096-157">Stores the network site links defined in NCS setting.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-158"><a href="lync-server-2013-endpointsubnet-table.md">Tabla EndpointSubnet en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-158"><a href="lync-server-2013-endpointsubnet-table.md">EndpointSubnet table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-159">Almacena la subred del punto final que participa en una sesión de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-159">Stores the subnet of the endpoint participating in an audio and video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-160"><a href="lync-server-2013-server-table.md">Tabla Server en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-160"><a href="lync-server-2013-server-table.md">Server table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-161">Almacena el FQDN o la dirección IP del servidor en el que se recorren los medios.</span><span class="sxs-lookup"><span data-stu-id="87096-161">Stores the FQDN or IP address of the server the media goes through.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87096-162">**Tablas para datos de métricas**</span><span class="sxs-lookup"><span data-stu-id="87096-162">**Tables for metrics data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87096-163"><strong>Tabla</strong></span><span class="sxs-lookup"><span data-stu-id="87096-163"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="87096-164"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="87096-164"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87096-165"><a href="lync-server-2013-appsharingstream-table.md">Tabla AppSharingStream en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-165"><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-166">Almacena métricas de experiencia de evaluación de la calidad de las secuencias de red usadas para compartir aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="87096-166">Stores Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="87096-167">Métricas de la calidad de la experiencia de las secuencias de red que se usan para compartir aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="87096-167">Quality of Experience metrics for the network streams used for application sharing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-168"><a href="lync-server-2013-session-table.md">Tabla Session en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-168"><a href="lync-server-2013-session-table.md">Session table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-169">Almacena información general sobre una sesión de audio o vídeo o audio.</span><span class="sxs-lookup"><span data-stu-id="87096-169">Stores overall information about an audio or audio/video session.</span></span> <span data-ttu-id="87096-170">Una sesión se define como un cuadro de diálogo SIP de audio o vídeo entre dos puntos finales.</span><span class="sxs-lookup"><span data-stu-id="87096-170">A session is defined as an audio or video SIP dialog between two endpoints.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-171"><a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-171"><a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-172">Almacena información sobre cada línea multimedia de una sesión.</span><span class="sxs-lookup"><span data-stu-id="87096-172">Stores information about each media line in a session.</span></span> <span data-ttu-id="87096-173">Una línea de medios es una colección de una o más secuencias de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-173">A media line is a collection of one or more audio and video streams.</span></span> <span data-ttu-id="87096-174">Normalmente, una única línea multimedia tendrá dos secuencias, ya sea audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="87096-174">Typically, a single media line will have two streams, either audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-175"><a href="lync-server-2013-audiostream-table.md">Tabla AudioStream en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-175"><a href="lync-server-2013-audiostream-table.md">AudioStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-176">Almacena las métricas de calidad de audio multimedia de audio de cada flujo de audio de la línea de medios.</span><span class="sxs-lookup"><span data-stu-id="87096-176">Stores audio media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-177"><a href="lync-server-2013-audiosignal-table.md">Tabla AudioSignal en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-177"><a href="lync-server-2013-audiosignal-table.md">AudioSignal table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-178">Almacena las métricas de calidad de audio multimedia en la línea media.</span><span class="sxs-lookup"><span data-stu-id="87096-178">Stores audio media quality metrics in the media line.</span></span> <span data-ttu-id="87096-179">Esto incluye la métrica de cancelación de eco acústico (AEC) y las métricas de control automático de ganancia (AGC).</span><span class="sxs-lookup"><span data-stu-id="87096-179">This includes acoustic echo cancellation (AEC) and automatic gain control (AGC) metrics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-180"><a href="lync-server-2013-videostream-table.md">Tabla VideoStream en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-180"><a href="lync-server-2013-videostream-table.md">VideoStream table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-181">Almacena métricas de calidad de medios de vídeo para cada flujo de audio de la línea de medios.</span><span class="sxs-lookup"><span data-stu-id="87096-181">Stores video media quality metrics for each audio stream in the media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-182"><a href="lync-server-2013-audioclientevent-table.md">Tabla AudioClientEvent en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-182"><a href="lync-server-2013-audioclientevent-table.md">AudioClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-183">Almacena las métricas de calidad de audio multimedia recopiladas del evento de cliente.</span><span class="sxs-lookup"><span data-stu-id="87096-183">Stores audio media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-184"><a href="lync-server-2013-videoclientevent-table.md">Tabla VideoClientEvent en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="87096-184"><a href="lync-server-2013-videoclientevent-table.md">VideoClientEvent table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="87096-185">Almacena las métricas de calidad de medios de vídeo recopiladas desde el evento de cliente.</span><span class="sxs-lookup"><span data-stu-id="87096-185">Stores video media quality metrics collected from the client event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-186"><strong>Tabla DiagnosticData</strong></span><span class="sxs-lookup"><span data-stu-id="87096-186"><strong>DiagnosticData Table</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-187">Almacena datos de diagnóstico que solo son para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-187">Stores diagnostic data which is for internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87096-188">**Tablas de datos de Resumen**</span><span class="sxs-lookup"><span data-stu-id="87096-188">**Tables for summary data**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87096-189"><strong>Tabla</strong></span><span class="sxs-lookup"><span data-stu-id="87096-189"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="87096-190"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="87096-190"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87096-191"><strong>Tabla ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="87096-191"><strong>ServerSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-192">Almacena los datos de Resumen de los servidores, estos datos se usan únicamente para los informes de calidad de la experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="87096-192">Stores summary data for the servers, these data is used for Quality of Experience (QoE) reporting only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-193"><strong>Tabla UserSummary</strong></span><span class="sxs-lookup"><span data-stu-id="87096-193"><strong>UserSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-194">Almacena los datos de Resumen de los usuarios, estos datos se usan solo para informes de QoE.</span><span class="sxs-lookup"><span data-stu-id="87096-194">Stores summary data for users, these data is used for QoE reporting only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-195"><strong>Tabla CallTypeSummary</strong></span><span class="sxs-lookup"><span data-stu-id="87096-195"><strong>CallTypeSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-196">Almacenar datos de Resumen de tipos de llamadas: estos datos se usan para informes de QoE únicamente.</span><span class="sxs-lookup"><span data-stu-id="87096-196">Store summary data for call types, these data is used for QoE reporting only.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="87096-197">**Tablas para uso interno mediante el servidor de supervisión**</span><span class="sxs-lookup"><span data-stu-id="87096-197">**Tables for Internal Use by Monitoring Server**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87096-198"><strong>Tabla</strong></span><span class="sxs-lookup"><span data-stu-id="87096-198"><strong>Table</strong></span></span></th>
<th><span data-ttu-id="87096-199"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="87096-199"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87096-200"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="87096-200"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-201">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-201">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-202"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="87096-202"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-203">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-203">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-204"><strong>Tabla de FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="87096-204"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-205">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-205">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-206"><strong>Tabla de tareas</strong></span><span class="sxs-lookup"><span data-stu-id="87096-206"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-207">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-207">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-208"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="87096-208"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-209">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-209">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-210"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="87096-210"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-211">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-211">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-212"><strong>MetricsThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="87096-212"><strong>MetricsThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-213">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-213">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-214"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="87096-214"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-215">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-215">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-216"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="87096-216"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-217">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-217">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-218"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="87096-218"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-219">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-219">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-220"><strong>Tabla CallSummary</strong></span><span class="sxs-lookup"><span data-stu-id="87096-220"><strong>CallSummary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-221">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-221">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-222"><strong>Tabla DeviceCallSumary</strong></span><span class="sxs-lookup"><span data-stu-id="87096-222"><strong>DeviceCallSumary Table</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-223">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-223">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-224"><strong>Tabla de inquilinos</strong></span><span class="sxs-lookup"><span data-stu-id="87096-224"><strong>Tenant Table</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-225">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-225">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87096-226"><strong>VideoCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="87096-226"><strong>VideoCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-227">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-227">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87096-228"><strong>ASCallSummaryTable</strong></span><span class="sxs-lookup"><span data-stu-id="87096-228"><strong>ASCallSummaryTable</strong></span></span></p></td>
<td><p><span data-ttu-id="87096-229">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="87096-229">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

