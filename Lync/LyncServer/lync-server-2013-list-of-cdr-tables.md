---
title: 'Lync Server 2013: lista de tablas de CDR'
description: 'Lync Server 2013: lista de tablas de CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558706"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="48d00-103">Lista de tablas de CDR en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48d00-103">List of CDR tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48d00-104">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="48d00-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="48d00-105">El esquema de la base de datos del registro detallado de llamadas (CDR) incluye las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="48d00-105">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="48d00-106">Tablas estáticas</span><span class="sxs-lookup"><span data-stu-id="48d00-106">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48d00-107">Table</span><span class="sxs-lookup"><span data-stu-id="48d00-107">Table</span></span></th>
<th><span data-ttu-id="48d00-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="48d00-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48d00-109"><a href="lync-server-2013-callpriorities-table.md">Tabla CallPriorities en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-109"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-110">Almacena la lista de posibles prioridades de llamada, como emergencia, urgente, normal, no urgente, etc.</span><span class="sxs-lookup"><span data-stu-id="48d00-110">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabla ConferenceJoinTimeThresholds en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-111"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-112">Almacena los límites de clasificación usados por el informe de resumen de hora de incorporación a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="48d00-112">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-113"><a href="lync-server-2013-deregistertype-table.md">Tabla DeRegisterType en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-113"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-114">Almacena la lista de posibles motivos de anulación del registro de usuario, como el &quot; cliente iniciado, el &quot; &quot; registro expirado, el &quot; &quot; bloqueo del cliente &quot; y mucho más.</span><span class="sxs-lookup"><span data-stu-id="48d00-114">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-115"><a href="lync-server-2013-medialist-table.md">Tabla de MediaL en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-115"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-116">Almacena la lista de tipos de medios que pueden generar entradas en la base de datos (por ejemplo, mensajería instantánea, audio, vídeo y transferencia de archivos).</span><span class="sxs-lookup"><span data-stu-id="48d00-116">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-117"><a href="lync-server-2013-purgesettings-table.md">Tabla PurgeSettings en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-117"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-118">Almacena información que especifica si los registros de detalles de llamadas no actualizados se eliminarán automáticamente de la base de datos de CDR (así como cuándo se eliminarán).</span><span class="sxs-lookup"><span data-stu-id="48d00-118">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-119"><a href="lync-server-2013-roles-table.md">Tabla roles en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-119"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-120">Almacena la lista de posibles roles de conferencia (por ejemplo, participante y moderador).</span><span class="sxs-lookup"><span data-stu-id="48d00-120">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-121"><a href="lync-server-2013-sipresponsemetadata-table.md">Tabla SIPResponseMetaData en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-121"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-122">Almacena una lista de códigos de respuesta SIP, así como una clasificación y una definición de cada uno de estos códigos.</span><span class="sxs-lookup"><span data-stu-id="48d00-122">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="48d00-123">Tablas auxiliares</span><span class="sxs-lookup"><span data-stu-id="48d00-123">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48d00-124">Table</span><span class="sxs-lookup"><span data-stu-id="48d00-124">Table</span></span></th>
<th><span data-ttu-id="48d00-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="48d00-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48d00-126"><a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-126"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-127">Almacena los clientes (tipo de cliente y número de versión) de cada cliente que participa de una llamada con información capturada en esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="48d00-127">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-128"><a href="lync-server-2013-conferenceuris-table.md">Tabla ConferenceUris en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-128"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-129">Almacena una lista de ConferenceURI utilizados en las llamadas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="48d00-129">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-130"><a href="lync-server-2013-contenttypes-table.md">Tabla ContentTypes en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-130"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-131">Almacena una lista de tipos de contenido del Protocolo de inicio de sesión (SIP) utilizados en las llamadas punto a punto y las llamadas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="48d00-131">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-132"><a href="lync-server-2013-devices-table.md">Tabla Devices en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-132"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-133">Almacena una lista de dispositivos, incluido el fabricante, la versión de hardware y la dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="48d00-133">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-134"><a href="lync-server-2013-dialogs-table.md">Tabla de cuadros de diálogo en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-134"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-135">Almacena información acerca del identificador de diálogo de cada sesión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="48d00-135">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-136"><a href="lync-server-2013-edgeservers-table.md">Tabla EdgeServers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-136"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-137">Almacena una lista de servidores perimetrales utilizados para las llamadas externas.</span><span class="sxs-lookup"><span data-stu-id="48d00-137">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-138"><a href="lync-server-2013-gateways-table.md">Tabla gateways en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-138"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-139">Almacena una lista de puertas de enlace utilizadas para las llamadas de voz sobre IP (VoIP).</span><span class="sxs-lookup"><span data-stu-id="48d00-139">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-140"><a href="lync-server-2013-hardwareversions-table.md">Tabla HardwareVersions en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-140"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-141">Almacena una lista de versiones de hardware de dispositivos (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="48d00-141">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-142"><a href="lync-server-2013-manufacturers-table.md">Tabla Manufacturers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-142"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-143">Almacena una lista de fabricantes de dispositivos (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="48d00-143">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-144"><a href="lync-server-2013-mcus-table.md">Tabla MCU en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-144"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-145">Almacena información acerca de los diferentes servidores de conferencia A/V y sus URI.</span><span class="sxs-lookup"><span data-stu-id="48d00-145">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-146"><a href="lync-server-2013-mediationservers-table.md">Tabla MediationServers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-146"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-147">Almacena una lista de servidores de mediación utilizados para las llamadas VoIP.</span><span class="sxs-lookup"><span data-stu-id="48d00-147">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-148"><a href="lync-server-2013-phones-table.md">Tabla teléfonos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-148"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-149">Almacena todos los números de teléfono utilizados en las llamadas VoIP que se archivaron o cuyos detalles se registraron.</span><span class="sxs-lookup"><span data-stu-id="48d00-149">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-150"><a href="lync-server-2013-pools-table.md">Tabla pools en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-150"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-151">Almacena los nombres del grupo de servidores en el que se capturan los mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="48d00-151">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-152"><a href="lync-server-2013-servers-table.md">Tabla Servers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-152"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-153">Almacena el nombre de los servidores que participan en llamadas.</span><span class="sxs-lookup"><span data-stu-id="48d00-153">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-154"><a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-154"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-155">Almacena los inquilinos admitidos por la implementación actual.</span><span class="sxs-lookup"><span data-stu-id="48d00-155">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="48d00-156">Existen inquilinos integrados para usuarios de empresa, federados, de conectividad de mensajería instantánea pública y anónimos.</span><span class="sxs-lookup"><span data-stu-id="48d00-156">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-157"><a href="lync-server-2013-useragentdef-table.md">Tabla UserAgentDef en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-157"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-158">Asigna los identificadores de agente de usuario a los nombres descriptivos del agente.</span><span class="sxs-lookup"><span data-stu-id="48d00-158">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-159"><a href="lync-server-2013-users-table.md">Tabla users en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-159"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-160">Almacena los URI de los usuarios que participaron de sesiones registradas o archivadas en esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="48d00-160">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-161"><a href="lync-server-2013-userstatistics-table.md">Tabla UserStatistics en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-161"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-162">Almacena información sobre el uso del sistema de un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="48d00-162">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="48d00-163">Tablas específicas de registros CDR de conferencias</span><span class="sxs-lookup"><span data-stu-id="48d00-163">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48d00-164">Table</span><span class="sxs-lookup"><span data-stu-id="48d00-164">Table</span></span></th>
<th><span data-ttu-id="48d00-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="48d00-165">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48d00-166"><a href="lync-server-2013-conferences-table.md">Tabla conferencias en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-166"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-167">Almacena información acerca de todas las conferencias que se archivaron o cuyos detalles se registraron, incluido el URI de conferencia, y la hora de inicio y de finalización.</span><span class="sxs-lookup"><span data-stu-id="48d00-167">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-168"><a href="lync-server-2013-conferencesessiondetails-table.md">Tabla ConferenceSessionDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-168"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-169">Almacena información acerca de cada sesión de conferencia basada en SIP, incluida la hora de inicio y de finalización, el identificador de usuario, el código de respuesta y el identificador de diagnóstico de cada sesión.</span><span class="sxs-lookup"><span data-stu-id="48d00-169">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabla FocusJoinsAndLeaves en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-170"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-171">Almacena información acerca de los usuarios que se unen a conferencias y las abandonan, incluida la versión de cliente y el rol de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="48d00-171">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabla McuJoinsAndLeaves en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-172"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-173">Almacena información acerca de los servidores de conferencia A/V utilizados en una conferencia, y la hora de conexión y desconexión del usuario.</span><span class="sxs-lookup"><span data-stu-id="48d00-173">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="48d00-174">Tablas para mensajes de conferencias de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="48d00-174">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48d00-175">Table</span><span class="sxs-lookup"><span data-stu-id="48d00-175">Table</span></span></th>
<th><span data-ttu-id="48d00-176">Descripción</span><span class="sxs-lookup"><span data-stu-id="48d00-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48d00-177"><a href="lync-server-2013-conferencemessagecount-table.md">Tabla ConferenceMessageCount en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-177"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-178">Para cada conferencia de mensajería instantánea, almacena el número de mensajes enviados por cada usuario.</span><span class="sxs-lookup"><span data-stu-id="48d00-178">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-179"><a href="lync-server-2013-imreportsummary-table.md">Tabla IMReportSummary en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-179"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-180">Proporciona un informe general de las sesiones de mensajería instantánea llevadas a cabo en una organización.</span><span class="sxs-lookup"><span data-stu-id="48d00-180">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="48d00-181">Tablas para sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="48d00-181">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48d00-182">Table</span><span class="sxs-lookup"><span data-stu-id="48d00-182">Table</span></span></th>
<th><span data-ttu-id="48d00-183">Descripción</span><span class="sxs-lookup"><span data-stu-id="48d00-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48d00-184"><a href="lync-server-2013-sessiondetails-table.md">Tabla SessionDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-184"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-185">Almacena información acerca de cada sesión punto a punto, incluida la hora de inicio y de finalización, el identificador de usuario, el código de respuesta y el recuento de mensajes de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="48d00-185">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-186"><a href="lync-server-2013-filetransfers-table.md">Tabla FileTransfers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-186"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-187">Almacena información acerca de las sesiones de transferencia de archivos, incluido el nombre de archivo y el resultado (aceptado, rechazado o cancelado).</span><span class="sxs-lookup"><span data-stu-id="48d00-187">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-188"><a href="lync-server-2013-media-table.md">Tabla de medios en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-188"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-189">Almacena información acerca de los diferentes tipos de medios utilizados en las sesiones punto a punto.</span><span class="sxs-lookup"><span data-stu-id="48d00-189">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="48d00-190">Tabla para detalles de llamadas VoIP</span><span class="sxs-lookup"><span data-stu-id="48d00-190">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48d00-191">Table</span><span class="sxs-lookup"><span data-stu-id="48d00-191">Table</span></span></th>
<th><span data-ttu-id="48d00-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="48d00-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48d00-193"><a href="lync-server-2013-voipdetails-table.md">Tabla VoipDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-193"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-194">Para cada llamada VoIP/RTC de dos participantes, almacena información acerca de la llamada, como el identificador del teléfono VoIP, la puerta de enlace utilizada y el participante que desconectó la llamada.</span><span class="sxs-lookup"><span data-stu-id="48d00-194">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="48d00-195">Hace referencia a la <a href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</a> para llamar a las horas de inicio y finalización y el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="48d00-195">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="48d00-196">Si un participante de la llamada es un usuario VoIP o si se utilizó un servidor de mediación en la llamada, se creará un registro en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="48d00-196">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="48d00-197">La información sobre las llamadas VoIP/VoIP que no implican un teléfono de red telefónica conmutada (RTC) se captura en la <A href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="48d00-197">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="48d00-198">Tabla para auditoría de llamadas E9-1-1</span><span class="sxs-lookup"><span data-stu-id="48d00-198">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48d00-199">Table</span><span class="sxs-lookup"><span data-stu-id="48d00-199">Table</span></span></th>
<th><span data-ttu-id="48d00-200">Descripción</span><span class="sxs-lookup"><span data-stu-id="48d00-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48d00-201"><a href="lync-server-2013-locations-table.md">Tabla Locations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-201"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-202">Para cada llamada de emergencia, como una llamada Enhanced 9-1-1 (E9-1-1), almacena información acerca de la ubicación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="48d00-202">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="48d00-203">Hace referencia a la <a href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</a> para llamar a las horas de inicio y finalización y el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="48d00-203">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="48d00-p105">Esta tabla solamente contiene el objeto binario grande de la ubicación de la llamada E9-1-1. Remítase a la tabla SessionDetails para obtener información adicional sobre la llamada.</span><span class="sxs-lookup"><span data-stu-id="48d00-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="48d00-206">Tablas para solución de problemas</span><span class="sxs-lookup"><span data-stu-id="48d00-206">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48d00-207">Table</span><span class="sxs-lookup"><span data-stu-id="48d00-207">Table</span></span></th>
<th><span data-ttu-id="48d00-208">Descripción</span><span class="sxs-lookup"><span data-stu-id="48d00-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48d00-209"><a href="lync-server-2013-application-table.md">Tabla de aplicaciones en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-209"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-210">Almacena información sobre varios procesos en Lync Server 2013 que participan en el enrutamiento y las conexiones.</span><span class="sxs-lookup"><span data-stu-id="48d00-210">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-211"><a href="lync-server-2013-calltype-table.md">Tabla CallType en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-211"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-212">Almacena información acerca de los tipos de llamada, como “audio”, “mensajería instantánea”, “audio y vídeo” y “uso compartido de aplicaciones”.</span><span class="sxs-lookup"><span data-stu-id="48d00-212">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-213"><a href="lync-server-2013-errorcategory-table.md">Tabla categoría en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-213"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-214">Almacena el nombre descriptivo para cada clasificación de diagnóstico de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48d00-214">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-215"><a href="lync-server-2013-errordef-table.md">Tabla ErrorDef en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-215"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-216">Almacena información acerca de los tipos de errores y sus definiciones.</span><span class="sxs-lookup"><span data-stu-id="48d00-216">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-217"><a href="lync-server-2013-errorreport-table.md">Tabla ErrorReport en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-217"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-218">Almacena información acerca de los errores generados.</span><span class="sxs-lookup"><span data-stu-id="48d00-218">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-219"><a href="lync-server-2013-progressreport-table.md">Tabla ProgressReport en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="48d00-219"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="48d00-220">Almacena información sobre los informes de progreso de varios pasos implicados en los procesos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48d00-220">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="48d00-221">Las tablas de la lista siguiente se usan internamente en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48d00-221">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="48d00-222">Los detalles no se describen en este documento.</span><span class="sxs-lookup"><span data-stu-id="48d00-222">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="48d00-223">Tablas para uso interno de Lync Server</span><span class="sxs-lookup"><span data-stu-id="48d00-223">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48d00-224">Table</span><span class="sxs-lookup"><span data-stu-id="48d00-224">Table</span></span></th>
<th><span data-ttu-id="48d00-225">Descripción</span><span class="sxs-lookup"><span data-stu-id="48d00-225">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48d00-226"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-226"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-227">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-227">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-228"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-228"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-229">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-229">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-230"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-230"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-231">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-231">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-232"><strong>Tabla FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-232"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-233">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-233">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-234"><strong>Tabla MSMQProcessing</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-234"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-235">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-235">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-236"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-236"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-237">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-237">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-238"><strong>Tabla Syndicators</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-238"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-239">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-239">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-240"><strong>Tabla SyndicatorsTenantMap</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-240"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-241">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-241">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-242"><strong>Tabla Task</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-242"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-243">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-243">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-244"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-244"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-245">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-245">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-246"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-246"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-247">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-247">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-248"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-248"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-249">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-249">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-250"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-250"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-251">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-251">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-252"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-252"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-253">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-253">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-254"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-254"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-255">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-255">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-256"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-256"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-257">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-257">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-258"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-258"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-259">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-259">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48d00-260"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-260"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-261">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-261">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48d00-262"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="48d00-262"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="48d00-263">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="48d00-263">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

