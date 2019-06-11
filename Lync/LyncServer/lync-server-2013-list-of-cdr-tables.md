---
title: 'Lync Server 2013: Lista de tablas de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1ac043d144e73d8e1b40ca717e278619e053fdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a><span data-ttu-id="e735a-102">Lista de tablas de CDR en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e735a-102">List of CDR tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e735a-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e735a-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e735a-104">El esquema de la base de datos de grabación de detalles de llamadas (CDR) consta de las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="e735a-104">The call detail recording (CDR) database schema consists of the following tables.</span></span>

<div>

## <a name="static-tables"></a><span data-ttu-id="e735a-105">Tablas estáticas</span><span class="sxs-lookup"><span data-stu-id="e735a-105">Static Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e735a-106">Tabla</span><span class="sxs-lookup"><span data-stu-id="e735a-106">Table</span></span></th>
<th><span data-ttu-id="e735a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e735a-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e735a-108"><a href="lync-server-2013-callpriorities-table.md">Tabla CallPriorities en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-108"><a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-109">Almacena la lista de posibles prioridades de llamadas, como emergencia, urgente, normal, no urgentes, etc.</span><span class="sxs-lookup"><span data-stu-id="e735a-109">Stores the list of possible call priorities, such as emergency, urgent, normal, non-urgent, and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabla ConferenceJoinTimeThresholds en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-110"><a href="lync-server-2013-conferencejointimethresholds-table.md">ConferenceJoinTimeThresholds table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-111">Almacena los límites de clasificación usados por el informe de Resumen de tiempo de combinación de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e735a-111">Stores the classification boundaries used by the Conference Join Time Summary Report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-112"><a href="lync-server-2013-deregistertype-table.md">Tabla DeRegisterType en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-112"><a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-113">Almacena la lista de posibles razones de anulación del registro de usuarios &quot;, como el&quot; &quot;cliente iniciado, el&quot; &quot;registro expirado&quot; , el bloqueo del cliente y mucho más.</span><span class="sxs-lookup"><span data-stu-id="e735a-113">Stores the list of possible user de-register reasons, such as &quot;client initiated,&quot; &quot;registration expired,&quot; &quot;client crash,&quot; and more.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-114"><a href="lync-server-2013-medialist-table.md">Tabla MediaList en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-114"><a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-115">Almacena la lista de tipos de medios que pueden generar entradas en la base de datos (por ejemplo, mensajería instantánea, audio, vídeo y transferencia de archivos).</span><span class="sxs-lookup"><span data-stu-id="e735a-115">Stores the list of media types that can generate entries in the database (for example, IM, audio, video, and file transfer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-116"><a href="lync-server-2013-purgesettings-table.md">Tabla PurgeSettings en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-116"><a href="lync-server-2013-purgesettings-table.md">PurgeSettings table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-117">Almacena información que especifica si (y cuándo) los registros de detalles de llamadas obsoletas se eliminarán automáticamente de la base de datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="e735a-117">Stores information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-118"><a href="lync-server-2013-roles-table.md">Tabla Roles en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-118"><a href="lync-server-2013-roles-table.md">Roles table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-119">Almacena la lista de posibles roles de conferencia (por ejemplo, asistente y moderador).</span><span class="sxs-lookup"><span data-stu-id="e735a-119">Stores the list of possible conference roles (for example, attendee and presenter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-120"><a href="lync-server-2013-sipresponsemetadata-table.md">Tabla SIPResponseMetaData en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-120"><a href="lync-server-2013-sipresponsemetadata-table.md">SIPResponseMetaData table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-121">Almacena una lista de códigos de respuesta SIP, así como la clasificación y definición de cada uno de esos códigos.</span><span class="sxs-lookup"><span data-stu-id="e735a-121">Stores a list of SIP response codes and the classification and definition of each of those codes.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a><span data-ttu-id="e735a-122">Tablas de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="e735a-122">Supporting Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e735a-123">Tabla</span><span class="sxs-lookup"><span data-stu-id="e735a-123">Table</span></span></th>
<th><span data-ttu-id="e735a-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="e735a-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e735a-125"><a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-125"><a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-126">Almacena los clientes (tanto el tipo de cliente como el número de versión) de cada cliente implicado en una llamada con información capturada en esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="e735a-126">Stores the clients (both client type and version number) of each client involved in a call with information captured in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-127"><a href="lync-server-2013-conferenceuris-table.md">Tabla ConferenceUris en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-127"><a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-128">Almacena una lista de ConferenceURIs que se usan en llamadas relacionadas con la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="e735a-128">Stores a list of ConferenceURIs that are used in conference related calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-129"><a href="lync-server-2013-contenttypes-table.md">Tabla ContentTypes en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-129"><a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-130">Almacena una lista de tipos de contenido de protocolo de inicio de sesión (SIP) que se usan en las llamadas de punto a punto y en las llamadas en conferencia.</span><span class="sxs-lookup"><span data-stu-id="e735a-130">Stores a list of Session Initiation Protocol (SIP) content types that are used in both peer-to-peer calls and conference calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-131"><a href="lync-server-2013-devices-table.md">Tabla Devices en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-131"><a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-132">Almacena una lista de dispositivos, incluidos el fabricante, la versión de hardware y la dirección MAC.</span><span class="sxs-lookup"><span data-stu-id="e735a-132">Stores a list of devices, including their manufacturer, hardware version, and MAC address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-133"><a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-133"><a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-134">Almacena información sobre el identificador de cuadro de diálogo para cada sesión de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e735a-134">Stores information about the Dialog ID for each session in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-135"><a href="lync-server-2013-edgeservers-table.md">Tabla EdgeServers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-135"><a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-136">Almacena una lista de servidores perimetrales que se usan para llamadas externas.</span><span class="sxs-lookup"><span data-stu-id="e735a-136">Stores a list of Edge Servers that are used for external calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-137"><a href="lync-server-2013-gateways-table.md">Tabla Gateways en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-137"><a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-138">Almacena una lista de puertas de enlace que se usan para llamadas de protocolo de voz a través de Internet (VoIP).</span><span class="sxs-lookup"><span data-stu-id="e735a-138">Stores a list of Gateways that are used for Voice over Internet Protocol (VoIP) calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-139"><a href="lync-server-2013-hardwareversions-table.md">Tabla HardwareVersions en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-139"><a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-140">Almacena una lista de versiones de hardware de los dispositivos (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="e735a-140">Stores a list of hardware versions of devices (desk phone).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-141"><a href="lync-server-2013-manufacturers-table.md">Tabla Manufacturers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-141"><a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-142">Almacena una lista de fabricantes de dispositivos (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="e735a-142">Stores a list of manufacturers of devices (desk phone).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-143"><a href="lync-server-2013-mcus-table.md">Tabla Mcus en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-143"><a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-144">Almacena información acerca de los diversos servidores de conferencia A/V y sus URI.</span><span class="sxs-lookup"><span data-stu-id="e735a-144">Stores information about the various A/V Conferencing Servers and their URIs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-145"><a href="lync-server-2013-mediationservers-table.md">Tabla MediationServers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-145"><a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-146">Almacena una lista de servidores de mediación que se usan para llamadas de VoIP.</span><span class="sxs-lookup"><span data-stu-id="e735a-146">Stores a list of Mediation Servers that are used for VoIP calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-147"><a href="lync-server-2013-phones-table.md">Tabla Phones en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-147"><a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-148">Almacena todos los números de teléfono usados en llamadas VoIP que fueron archivados o cuyos detalles de llamadas fueron grabados.</span><span class="sxs-lookup"><span data-stu-id="e735a-148">Stores all the phone numbers used in VoIP calls that were archived or whose call details were recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-149"><a href="lync-server-2013-pools-table.md">Tabla Pools en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-149"><a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-150">Almacena los nombres del grupo en el que se capturan los mensajes INSTANTÁNEos.</span><span class="sxs-lookup"><span data-stu-id="e735a-150">Stores the names of the pool on which IM messages are captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-151"><a href="lync-server-2013-servers-table.md">Tabla Servers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-151"><a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-152">Almacena el nombre de los servidores implicados en las llamadas.</span><span class="sxs-lookup"><span data-stu-id="e735a-152">Stores the name of servers involved in calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-153"><a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-153"><a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-154">Almacena los espacios empresariales admitidos por la implementación actual.</span><span class="sxs-lookup"><span data-stu-id="e735a-154">Stores the tenants supported by current deployment.</span></span> <span data-ttu-id="e735a-155">Hay algunos inquilinos de compilación para usuarios de empresa, usuarios federados, usuarios de la conectividad de mensajería instantánea pública y usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="e735a-155">There some build-in tenants for Enterprise user, Federated User, public IM connectivity user, and Anonymous users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-156"><a href="lync-server-2013-useragentdef-table.md">Tabla UserAgentDef en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-156"><a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-157">Asigna identificadores de agente de usuario a los nombres descriptivos del agente.</span><span class="sxs-lookup"><span data-stu-id="e735a-157">Maps user agent identifiers to the agent’s descriptive names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-158"><a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-158"><a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-159">Almacena los URI de usuario de los usuarios que participaron en sesiones grabadas o archivadas en esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="e735a-159">Stores the user URIs of users who have participated in sessions recorded or archived in this database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-160"><a href="lync-server-2013-userstatistics-table.md">Tabla UserStatistics en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-160"><a href="lync-server-2013-userstatistics-table.md">UserStatistics table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-161">Almacena información sobre el uso del sistema por un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="e735a-161">Stores information about an individual user’s usage of the system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a><span data-ttu-id="e735a-162">Tablas específicas de registros de CDR de conferencia</span><span class="sxs-lookup"><span data-stu-id="e735a-162">Tables Specific to Conference CDR Records</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e735a-163">Tabla</span><span class="sxs-lookup"><span data-stu-id="e735a-163">Table</span></span></th>
<th><span data-ttu-id="e735a-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="e735a-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e735a-165"><a href="lync-server-2013-conferences-table.md">Tabla Conferences en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-165"><a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-166">Almacena información sobre todas las conferencias que se archivaron o cuyos detalles se grabaron, incluyendo ConferenceURI, y la hora de inicio y finalización.</span><span class="sxs-lookup"><span data-stu-id="e735a-166">Stores information about all conferences that were archived or whose details were recorded, including ConferenceURI, and start and end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-167"><a href="lync-server-2013-conferencesessiondetails-table.md">Tabla ConferenceSessionDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-167"><a href="lync-server-2013-conferencesessiondetails-table.md">ConferenceSessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-168">Almacena información sobre todas las sesiones de conferencia basadas en SIP, como la hora de inicio y finalización, el identificador de usuario, el código de respuesta y el identificador de diagnóstico de cada sesión.</span><span class="sxs-lookup"><span data-stu-id="e735a-168">Stores information about every SIP-based conference session, including start and end time, user ID, response code, and diagnostic ID for each session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabla FocusJoinsAndLeaves en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-169"><a href="lync-server-2013-focusjoinsandleaves-table.md">FocusJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-170">Almacena información acerca de las uniones y las hojas de reuniones, incluidos el rol de los usuarios y la versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="e735a-170">Stores information about conference joins and leaves, including users’ role and client version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabla McuJoinsAndLeaves en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-171"><a href="lync-server-2013-mcujoinsandleaves-table.md">McuJoinsAndLeaves table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-172">Almacena información sobre los servidores de conferencia A/V implicados en una conferencia y la combinación de usuarios y horas de salida.</span><span class="sxs-lookup"><span data-stu-id="e735a-172">Stores information about the A/V Conferencing Servers that are involved in a conference and the user join and leave times.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a><span data-ttu-id="e735a-173">Tablas de mensajes en conferencias de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="e735a-173">Tables for Messages in IM Conferences</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e735a-174">Tabla</span><span class="sxs-lookup"><span data-stu-id="e735a-174">Table</span></span></th>
<th><span data-ttu-id="e735a-175">Descripción</span><span class="sxs-lookup"><span data-stu-id="e735a-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e735a-176"><a href="lync-server-2013-conferencemessagecount-table.md">Tabla ConferenceMessageCount en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-176"><a href="lync-server-2013-conferencemessagecount-table.md">ConferenceMessageCount table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-177">Para cada Conferencia de mensajería instantánea, almacena el número de mensajes que envió cada usuario.</span><span class="sxs-lookup"><span data-stu-id="e735a-177">For each IM conference, stores the number of messages that were sent by each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-178"><a href="lync-server-2013-imreportsummary-table.md">Tabla IMReportSummary en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-178"><a href="lync-server-2013-imreportsummary-table.md">IMReportSummary table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-179">Proporciona un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización.</span><span class="sxs-lookup"><span data-stu-id="e735a-179">Provides an overall report on the instant messaging sessions held in an organization.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a><span data-ttu-id="e735a-180">Tablas para sesiones de punto a punto</span><span class="sxs-lookup"><span data-stu-id="e735a-180">Tables for Peer-to-Peer Sessions</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e735a-181">Tabla</span><span class="sxs-lookup"><span data-stu-id="e735a-181">Table</span></span></th>
<th><span data-ttu-id="e735a-182">Descripción</span><span class="sxs-lookup"><span data-stu-id="e735a-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e735a-183"><a href="lync-server-2013-sessiondetails-table.md">Tabla SessionDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-183"><a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-184">Almacena información sobre cada sesión de punto a punto, incluyendo la hora de inicio y finalización, el identificador de usuario, el código de respuesta y el recuento de mensajes de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="e735a-184">Stores information about every peer-to-peer session, including start and end time, user ID, response code, and message count for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-185"><a href="lync-server-2013-filetransfers-table.md">Tabla FileTransfers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-185"><a href="lync-server-2013-filetransfers-table.md">FileTransfers table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-186">Almacena información sobre las sesiones de transferencia de archivos, incluidos el nombre de archivo y el resultado (aceptada, rechazada o cancelada).</span><span class="sxs-lookup"><span data-stu-id="e735a-186">Stores information about file transfer sessions, including file name and result (accepted, rejected, or canceled).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-187"><a href="lync-server-2013-media-table.md">Tabla Media en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-187"><a href="lync-server-2013-media-table.md">Media table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-188">Almacena información sobre los diferentes tipos de medios implicados en sesiones de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="e735a-188">Stores information about the different media types involved in peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a><span data-ttu-id="e735a-189">Tabla de detalles de llamadas VoIP</span><span class="sxs-lookup"><span data-stu-id="e735a-189">Table for VoIP Call Details</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e735a-190">Tabla</span><span class="sxs-lookup"><span data-stu-id="e735a-190">Table</span></span></th>
<th><span data-ttu-id="e735a-191">Descripción</span><span class="sxs-lookup"><span data-stu-id="e735a-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e735a-192"><a href="lync-server-2013-voipdetails-table.md">Tabla VoipDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-192"><a href="lync-server-2013-voipdetails-table.md">VoipDetails table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-193">Para cada llamada de VoIP/RTC de dos partes, almacena información sobre la llamada, como el identificador de teléfono del teléfono VoIP, la puerta de enlace usada y qué parte se desconectó.</span><span class="sxs-lookup"><span data-stu-id="e735a-193">For each two-party VoIP/PSTN call, stores information about the call, such as the phone ID of VoIP phone, gateway used, and which party disconnected.</span></span> <span data-ttu-id="e735a-194">Hace referencia a la <a href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</a> para las horas de inicio y finalización de la llamada y el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e735a-194">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e735a-195">Si una de las partes de una llamada es un usuario de VoIP o si un servidor de mediación participó en la llamada, se creará un registro en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="e735a-195">If one party on a call is a VoIP user or if a Mediation Server was involved in the call, a record will be created in this table.</span></span> <span data-ttu-id="e735a-196">La información sobre las llamadas de VoIP o VoIP que no implica un teléfono de red telefónica conmutada (RTC) se captura en la <A href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e735a-196">Information about VoIP/VoIP calls not involving a public switched telephone network (PSTN) phone is captured in the <A href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</A>.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a><span data-ttu-id="e735a-197">Tabla de auditorías de llamadas de E9-1-1</span><span class="sxs-lookup"><span data-stu-id="e735a-197">Table for E9-1-1 Call Auditing</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e735a-198">Tabla</span><span class="sxs-lookup"><span data-stu-id="e735a-198">Table</span></span></th>
<th><span data-ttu-id="e735a-199">Descripción</span><span class="sxs-lookup"><span data-stu-id="e735a-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e735a-200"><a href="lync-server-2013-locations-table.md">Tabla Locations en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-200"><a href="lync-server-2013-locations-table.md">Locations table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-201">Para cada llamada de emergencia, como una llamada mejorada de 9-1-1 (E9-1-1), almacena información sobre la ubicación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e735a-201">For each emergency call, such as an Enhanced 9-1-1 (E9-1-1) call, stores location information about the call.</span></span> <span data-ttu-id="e735a-202">Hace referencia a la <a href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</a> para las horas de inicio y finalización de la llamada y el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e735a-202">Refers to the <a href="lync-server-2013-sessiondetails-table.md">SessionDetails table in Lync Server 2013</a> for call start/end times and response code.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e735a-203">Esta tabla solo contiene el BLOB de ubicación para la llamada de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="e735a-203">This table only contains the location blob for the E9-1-1 call.</span></span> <span data-ttu-id="e735a-204">Hace referencia a la tabla SessionDetails para obtener información detallada sobre la llamada.</span><span class="sxs-lookup"><span data-stu-id="e735a-204">Refers to the SessionDetails table for other detailed information about the call.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a><span data-ttu-id="e735a-205">Tablas para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="e735a-205">Tables for Troubleshooting</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e735a-206">Tabla</span><span class="sxs-lookup"><span data-stu-id="e735a-206">Table</span></span></th>
<th><span data-ttu-id="e735a-207">Descripción</span><span class="sxs-lookup"><span data-stu-id="e735a-207">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e735a-208"><a href="lync-server-2013-application-table.md">Tabla Application en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-208"><a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-209">Almacena información acerca de los distintos procesos de Lync Server 2013 que participan en el enrutamiento y en las conexiones.</span><span class="sxs-lookup"><span data-stu-id="e735a-209">Stores information about various processes within Lync Server 2013 that are involved in routing and connections.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-210"><a href="lync-server-2013-calltype-table.md">Tabla CallType en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-210"><a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-211">Almacena información sobre los tipos de la llamada, como "audio", "mensajería instantánea", "audio y vídeo" y "uso compartido de aplicaciones".</span><span class="sxs-lookup"><span data-stu-id="e735a-211">Stores information about types of the call, such as, “audio”, “Instant Messaging”, “audio and video” and “application sharing”.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-212"><a href="lync-server-2013-errorcategory-table.md">Tabla ErrorCategory en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-212"><a href="lync-server-2013-errorcategory-table.md">ErrorCategory table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-213">Almacena el nombre descriptivo de cada clasificación de diagnóstico de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e735a-213">Stores the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-214"><a href="lync-server-2013-errordef-table.md">Tabla ErrorDef en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-214"><a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-215">Almacena información sobre los tipos de errores y sus definiciones.</span><span class="sxs-lookup"><span data-stu-id="e735a-215">Stores information about types of errors and their definitions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-216"><a href="lync-server-2013-errorreport-table.md">Tabla ErrorReport en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-216"><a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-217">Almacena información sobre los errores que se han producido.</span><span class="sxs-lookup"><span data-stu-id="e735a-217">Stores information about errors that have occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-218"><a href="lync-server-2013-progressreport-table.md">Tabla ProgressReport en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e735a-218"><a href="lync-server-2013-progressreport-table.md">ProgressReport table in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="e735a-219">Almacena información sobre los informes de progreso de varios pasos implicados en los procesos de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e735a-219">Stores information about the progress reports of various steps involved in Lync Server 2013 processes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e735a-220">Las tablas de la siguiente lista son utilizadas internamente por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e735a-220">The tables in the following list are used internally by Lync Server.</span></span> <span data-ttu-id="e735a-221">Los detalles no se describen en este documento.</span><span class="sxs-lookup"><span data-stu-id="e735a-221">Their details are not described in this document.</span></span>

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a><span data-ttu-id="e735a-222">Tablas para uso interno de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e735a-222">Tables for Internal Use by Lync Server</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e735a-223">Tabla</span><span class="sxs-lookup"><span data-stu-id="e735a-223">Table</span></span></th>
<th><span data-ttu-id="e735a-224">Descripción</span><span class="sxs-lookup"><span data-stu-id="e735a-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e735a-225"><strong>DbConfigDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-225"><strong>DbConfigDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-226">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-226">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-227"><strong>DbConfigInt</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-227"><strong>DbConfigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-228">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-228">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-229"><strong>DbErrorMessage</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-229"><strong>DbErrorMessage</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-230">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-230">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-231"><strong>Tabla de FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-231"><strong>FrontEnd Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-232">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-232">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-233"><strong>Tabla MSMQProcessing</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-233"><strong>MSMQProcessing Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-234">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-234">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-235"><strong>SummaryTableConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-235"><strong>SummaryTableConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-236">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-236">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-237"><strong>Tabla de sindicación</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-237"><strong>Syndicators Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-238">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-238">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-239"><strong>Tabla SyndicatorsTenantMap</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-239"><strong>SyndicatorsTenantMap Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-240">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-240">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-241"><strong>Tabla de tareas</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-241"><strong>Task Table</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-242">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-242">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-243"><strong>UserStatistics</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-243"><strong>UserStatistics</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-244">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-244">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-245"><strong>UsageSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-245"><strong>UsageSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-246">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-246">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-247"><strong>UsageSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-247"><strong>UsageSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-248">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-248">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-249"><strong>DaylightSavingYears</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-249"><strong>DaylightSavingYears</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-250">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-250">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-251"><strong>TimeZoneConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-251"><strong>TimeZoneConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-252">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-252">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-253"><strong>TimeZones</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-253"><strong>TimeZones</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-254">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-254">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-255"><strong>FailureSummary_UQ</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-255"><strong>FailureSummary_UQ</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-256">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-256">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-257"><strong>FailureSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-257"><strong>FailureSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-258">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-258">For internal use only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e735a-259"><strong>ServerSummary</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-259"><strong>ServerSummary</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-260">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-260">For internal use only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e735a-261"><strong>MsDiagMetaData</strong></span><span class="sxs-lookup"><span data-stu-id="e735a-261"><strong>MsDiagMetaData</strong></span></span></p></td>
<td><p><span data-ttu-id="e735a-262">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e735a-262">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

