---
title: 'Lync Server 2013: lista de tablas de CDR'
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
ms.openlocfilehash: 6f7f6fed1fad8cf706b86ef0cb141ab04fb39382
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="b3b19-102">Lista de tablas de CDR en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3b19-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3b19-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b3b19-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b3b19-104">El esquema de la base de datos del registro detallado de llamadas (CDR) incluye las tablas siguientes.</span><span class="sxs-lookup"><span data-stu-id="b3b19-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="b3b19-105">Tablas estáticas</span><span class="sxs-lookup"><span data-stu-id="b3b19-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3b19-106">Table</span><span class="sxs-lookup"><span data-stu-id="b3b19-106">Table</span></span></th>
<th><span data-ttu-id="b3b19-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3b19-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-108"><a href="lync-server-2013-callpriorities-table.md">Tabla CallPriorities en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-109">Almacena la lista de posibles prioridades de llamada, como emergencia, urgente, normal, no urgente, etc.</span><span class="sxs-lookup"><span data-stu-id="b3b19-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabla ConferenceJoinTimeThresholds en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-111">Almacena los límites de clasificación usados por el informe de resumen de hora de incorporación a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="b3b19-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-112"><a href="lync-server-2013-deregistertype-table.md">Tabla DeRegisterType en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-113">Almacena la lista de posibles motivos de anulación del registro de usuario &quot;, como el&quot; &quot;cliente iniciado, el&quot; &quot;registro expirado&quot; , el bloqueo del cliente y mucho más.</span><span class="sxs-lookup"><span data-stu-id="b3b19-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-114"><a href="lync-server-2013-medialist-table.md">Tabla de MediaL en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-115">Almacena la lista de tipos de medios que pueden generar entradas en la base de datos (por ejemplo, mensajería instantánea, audio, vídeo y transferencia de archivos).</span><span class="sxs-lookup"><span data-stu-id="b3b19-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-116"><a href="lync-server-2013-purgesettings-table.md">Tabla PurgeSettings en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-117">Almacena información que especifica si los registros de detalles de llamadas no actualizados se eliminarán automáticamente de la base de datos de CDR (así como cuándo se eliminarán).</span><span class="sxs-lookup"><span data-stu-id="b3b19-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-118"><a href="lync-server-2013-roles-table.md">Tabla roles en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-119">Almacena la lista de posibles roles de conferencia (por ejemplo, participante y moderador).</span><span class="sxs-lookup"><span data-stu-id="b3b19-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Tabla SIPResponseMetaData en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-121">Almacena una lista de códigos de respuesta SIP, así como una clasificación y una definición de cada uno de estos códigos.</span><span class="sxs-lookup"><span data-stu-id="b3b19-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="b3b19-122">Tablas auxiliares</span><span class="sxs-lookup"><span data-stu-id="b3b19-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3b19-123">Table</span><span class="sxs-lookup"><span data-stu-id="b3b19-123">Table</span></span></th>
<th><span data-ttu-id="b3b19-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3b19-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-125"><a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-126">Almacena los clientes (tipo de cliente y número de versión) de cada cliente que participa de una llamada con información capturada en esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="b3b19-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-127"><a href="lync-server-2013-conferenceuris-table.md">Tabla ConferenceUris en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-128">Almacena una lista de ConferenceURI utilizados en las llamadas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="b3b19-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-129"><a href="lync-server-2013-contenttypes-table.md">Tabla ContentTypes en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-130">Almacena una lista de tipos de contenido del Protocolo de inicio de sesión (SIP) utilizados en las llamadas punto a punto y las llamadas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="b3b19-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-131"><a href="lync-server-2013-devices-table.md">Tabla Devices en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-132">Almacena una lista de dispositivos, incluido el fabricante, la versión de hardware y la dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="b3b19-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-133"><a href="lync-server-2013-dialogs-table.md">Tabla de cuadros de diálogo en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-134">Almacena información acerca del identificador de diálogo de cada sesión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b3b19-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-135"><a href="lync-server-2013-edgeservers-table.md">Tabla EdgeServers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-136">Almacena una lista de servidores perimetrales utilizados para las llamadas externas.</span><span class="sxs-lookup"><span data-stu-id="b3b19-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-137"><a href="lync-server-2013-gateways-table.md">Tabla gateways en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-138">Almacena una lista de puertas de enlace utilizadas para las llamadas de voz sobre IP (VoIP).</span><span class="sxs-lookup"><span data-stu-id="b3b19-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-139"><a href="lync-server-2013-hardwareversions-table.md">Tabla HardwareVersions en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-140">Almacena una lista de versiones de hardware de dispositivos (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="b3b19-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-141"><a href="lync-server-2013-manufacturers-table.md">Tabla Manufacturers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-142">Almacena una lista de fabricantes de dispositivos (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="b3b19-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-143"><a href="lync-server-2013-mcus-table.md">Tabla MCU en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-144">Almacena información acerca de los diferentes servidores de conferencia A/V y sus URI.</span><span class="sxs-lookup"><span data-stu-id="b3b19-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-145"><a href="lync-server-2013-mediationservers-table.md">Tabla MediationServers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-146">Almacena una lista de servidores de mediación utilizados para las llamadas VoIP.</span><span class="sxs-lookup"><span data-stu-id="b3b19-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-147"><a href="lync-server-2013-phones-table.md">Tabla teléfonos en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-148">Almacena todos los números de teléfono utilizados en las llamadas VoIP que se archivaron o cuyos detalles se registraron.</span><span class="sxs-lookup"><span data-stu-id="b3b19-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-149"><a href="lync-server-2013-pools-table.md">Tabla pools en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-150">Almacena los nombres del grupo de servidores en el que se capturan los mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="b3b19-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-151"><a href="lync-server-2013-servers-table.md">Tabla Servers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-152">Almacena el nombre de los servidores que participan en llamadas.</span><span class="sxs-lookup"><span data-stu-id="b3b19-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-153"><a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-154">Almacena los inquilinos admitidos por la implementación actual.</span><span class="sxs-lookup"><span data-stu-id="b3b19-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="b3b19-155">Existen inquilinos integrados para usuarios de empresa, federados, de conectividad de mensajería instantánea pública y anónimos.</span><span class="sxs-lookup"><span data-stu-id="b3b19-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-156"><a href="lync-server-2013-useragentdef-table.md">Tabla UserAgentDef en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-157">Asigna los identificadores de agente de usuario a los nombres descriptivos del agente.</span><span class="sxs-lookup"><span data-stu-id="b3b19-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-158"><a href="lync-server-2013-users-table.md">Tabla users en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-159">Almacena los URI de los usuarios que participaron de sesiones registradas o archivadas en esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="b3b19-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-160"><a href="lync-server-2013-userstatistics-table.md">Tabla UserStatistics en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-161">Almacena información sobre el uso del sistema de un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="b3b19-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="b3b19-162">Tablas específicas de registros CDR de conferencias</span><span class="sxs-lookup"><span data-stu-id="b3b19-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3b19-163">Table</span><span class="sxs-lookup"><span data-stu-id="b3b19-163">Table</span></span></th>
<th><span data-ttu-id="b3b19-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3b19-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-165"><a href="lync-server-2013-conferences-table.md">Tabla conferencias en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-166">Almacena información acerca de todas las conferencias que se archivaron o cuyos detalles se registraron, incluido el URI de conferencia, y la hora de inicio y de finalización.</span><span class="sxs-lookup"><span data-stu-id="b3b19-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Tabla ConferenceSessionDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-168">Almacena información acerca de cada sesión de conferencia basada en SIP, incluida la hora de inicio y de finalización, el identificador de usuario, el código de respuesta y el identificador de diagnóstico de cada sesión.</span><span class="sxs-lookup"><span data-stu-id="b3b19-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabla FocusJoinsAndLeaves en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-170">Almacena información acerca de los usuarios que se unen a conferencias y las abandonan, incluida la versión de cliente y el rol de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b3b19-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabla McuJoinsAndLeaves en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-172">Almacena información acerca de los servidores de conferencia A/V utilizados en una conferencia, y la hora de conexión y desconexión del usuario.</span><span class="sxs-lookup"><span data-stu-id="b3b19-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="b3b19-173">Tablas para mensajes de conferencias de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="b3b19-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3b19-174">Table</span><span class="sxs-lookup"><span data-stu-id="b3b19-174">Table</span></span></th>
<th><span data-ttu-id="b3b19-175">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3b19-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-176"><a href="lync-server-2013-conferencemessagecount-table.md">Tabla ConferenceMessageCount en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-177">Para cada conferencia de mensajería instantánea, almacena el número de mensajes enviados por cada usuario.</span><span class="sxs-lookup"><span data-stu-id="b3b19-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-178"><a href="lync-server-2013-imreportsummary-table.md">Tabla IMReportSummary en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-179">Proporciona un informe general de las sesiones de mensajería instantánea llevadas a cabo en una organización.</span><span class="sxs-lookup"><span data-stu-id="b3b19-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="b3b19-180">Tablas para sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="b3b19-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3b19-181">Table</span><span class="sxs-lookup"><span data-stu-id="b3b19-181">Table</span></span></th>
<th><span data-ttu-id="b3b19-182">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3b19-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-183"><a href="lync-server-2013-sessiondetails-table.md">Tabla SessionDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-184">Almacena información acerca de cada sesión punto a punto, incluida la hora de inicio y de finalización, el identificador de usuario, el código de respuesta y el recuento de mensajes de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="b3b19-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-185"><a href="lync-server-2013-filetransfers-table.md">Tabla FileTransfers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-186">Almacena información acerca de las sesiones de transferencia de archivos, incluido el nombre de archivo y el resultado (aceptado, rechazado o cancelado).</span><span class="sxs-lookup"><span data-stu-id="b3b19-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-187"><a href="lync-server-2013-media-table.md">Tabla de medios en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-188">Almacena información acerca de los diferentes tipos de medios utilizados en las sesiones punto a punto.</span><span class="sxs-lookup"><span data-stu-id="b3b19-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="b3b19-189">Tabla para detalles de llamadas VoIP</span><span class="sxs-lookup"><span data-stu-id="b3b19-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3b19-190">Table</span><span class="sxs-lookup"><span data-stu-id="b3b19-190">Table</span></span></th>
<th><span data-ttu-id="b3b19-191">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3b19-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-192"><a href="lync-server-2013-voipdetails-table.md">Tabla VoipDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-193">Para cada llamada VoIP/RTC de dos participantes, almacena información acerca de la llamada, como el identificador del teléfono VoIP, la puerta de enlace utilizada y el participante que desconectó la llamada.</span><span class="sxs-lookup"><span data-stu-id="b3b19-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="b3b19-194">Hace referencia a la <a href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</a> para llamar a las horas de inicio y finalización y el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="b3b19-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b3b19-195">Si un participante de la llamada es un usuario VoIP o si se utilizó un servidor de mediación en la llamada, se creará un registro en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="b3b19-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="b3b19-196">La información sobre las llamadas VoIP/VoIP que no implican un teléfono de red telefónica conmutada (RTC) se captura en la <A href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b3b19-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="b3b19-197">Tabla para auditoría de llamadas E9-1-1</span><span class="sxs-lookup"><span data-stu-id="b3b19-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3b19-198">Table</span><span class="sxs-lookup"><span data-stu-id="b3b19-198">Table</span></span></th>
<th><span data-ttu-id="b3b19-199">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3b19-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-200"><a href="lync-server-2013-locations-table.md">Tabla Locations in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-201">Para cada llamada de emergencia, como una llamada Enhanced 9-1-1 (E9-1-1), almacena información acerca de la ubicación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b3b19-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="b3b19-202">Hace referencia a la <a href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</a> para llamar a las horas de inicio y finalización y el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="b3b19-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b3b19-p105">Esta tabla solamente contiene el objeto binario grande de la ubicación de la llamada E9-1-1. Remítase a la tabla SessionDetails para obtener información adicional sobre la llamada.</span><span class="sxs-lookup"><span data-stu-id="b3b19-p105">This table only contains the location blob for the E9-1-1 call. Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="b3b19-205">Tablas para solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b3b19-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3b19-206">Table</span><span class="sxs-lookup"><span data-stu-id="b3b19-206">Table</span></span></th>
<th><span data-ttu-id="b3b19-207">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3b19-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-208"><a href="lync-server-2013-application-table.md">Tabla de aplicaciones en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-209">Almacena información sobre varios procesos en Lync Server 2013 que participan en el enrutamiento y las conexiones.</span><span class="sxs-lookup"><span data-stu-id="b3b19-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-210"><a href="lync-server-2013-calltype-table.md">Tabla CallType en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-211">Almacena información acerca de los tipos de llamada, como “audio”, “mensajería instantánea”, “audio y vídeo” y “uso compartido de aplicaciones”.</span><span class="sxs-lookup"><span data-stu-id="b3b19-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-212"><a href="lync-server-2013-errorcategory-table.md">Tabla categoría en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-213">Almacena el nombre descriptivo para cada clasificación de diagnóstico de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3b19-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-214"><a href="lync-server-2013-errordef-table.md">Tabla ErrorDef en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-215">Almacena información acerca de los tipos de errores y sus definiciones.</span><span class="sxs-lookup"><span data-stu-id="b3b19-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-216"><a href="lync-server-2013-errorreport-table.md">Tabla ErrorReport en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-217">Almacena información acerca de los errores generados.</span><span class="sxs-lookup"><span data-stu-id="b3b19-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-218"><a href="lync-server-2013-progressreport-table.md">Tabla ProgressReport en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b3b19-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b3b19-219">Almacena información sobre los informes de progreso de varios pasos implicados en los procesos de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3b19-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b3b19-220">Las tablas de la lista siguiente se usan internamente en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3b19-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="b3b19-221">Los detalles no se describen en este documento.</span><span class="sxs-lookup"><span data-stu-id="b3b19-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="b3b19-222">Tablas para uso interno de Lync Server</span><span class="sxs-lookup"><span data-stu-id="b3b19-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3b19-223">Table</span><span class="sxs-lookup"><span data-stu-id="b3b19-223">Table</span></span></th>
<th><span data-ttu-id="b3b19-224">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3b19-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-226">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-228">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-230">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-231"><strong>Tabla FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-232">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-233"><strong>Tabla MSMQProcessing</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-234">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-236">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-237"><strong>Tabla Syndicators</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-238">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-239"><strong>Tabla SyndicatorsTenantMap</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-240">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-241"><strong>Tabla Task</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-242">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-244">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-246">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-248">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-250">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-252">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-253"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-254">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-256">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-258">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3b19-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-260">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3b19-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="b3b19-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="b3b19-262">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b3b19-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

