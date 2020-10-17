---
title: 'Lync Server 2013: lista de vistas de CDR'
description: 'Lync Server 2013: lista de vistas de CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f1c29560851c0e4466dbf4316bf0b1335906d4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550086"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="2b615-103">Lista de vistas de CDR en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b615-103">List of CDR views in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b615-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2b615-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2b615-105">Las vistas proporcionan una manera sencilla de acceder a la información sobre los escenarios más comunes utilizados para devolver datos de la base de datos de CDR.</span><span class="sxs-lookup"><span data-stu-id="2b615-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="2b615-106">Se recomienda usar vistas para crear informes personalizados en lugar de usar las tablas de base de datos de CDR reales; Esto se debe a que es más probable que las vistas de base de datos mantengan compatibilidad con versiones futuras de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b615-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b615-107">Nombre de vista</span><span class="sxs-lookup"><span data-stu-id="2b615-107">View Name</span></span></th>
<th><span data-ttu-id="2b615-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b615-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b615-109"><a href="lync-server-2013-clientversions-view.md">Vista ClientVersions en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-109"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-110">Devuelve información sobre los dispositivos o el software del cliente utilizados en una sesión de comunicación.</span><span class="sxs-lookup"><span data-stu-id="2b615-110">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b615-111"><a href="lync-server-2013-conferencemessagecount-view.md">Vista ConferenceMessageCount en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-111"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-112">Devuelve información sobre la cantidad de mensajes enviada por usuarios en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="2b615-112">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b615-113"><a href="lync-server-2013-conferences-view.md">Vista de conferencias en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-113"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-114">Devuelve información de conferencia, como por ejemplo la hora de inicio, la hora de finalización y el organizador de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="2b615-114">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b615-115"><a href="lync-server-2013-conferencesessiondetails-view.md">Vista ConferenceSessionDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-115"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-116">Devuelve información detallada de sesión de todas las sesiones de conferencia, como por ejemplo la hora de inicio y de finalización, los identificadores de usuarios, los códigos de respuesta y los identificadores de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="2b615-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b615-117"><a href="lync-server-2013-conferenceuris-view.md">Vista ConferenceUris en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-117"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-118">Devuelve información sobre URI de conferencias utilizados en una conferencia</span><span class="sxs-lookup"><span data-stu-id="2b615-118">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b615-119"><a href="lync-server-2013-errorreport-view.md">Vista ErrorReport en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-119"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-120">Devuelve información sobre los errores que se produjeron durante una sesión.</span><span class="sxs-lookup"><span data-stu-id="2b615-120">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b615-121"><a href="lync-server-2013-filetransfers-view.md">Vista FileTransfers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-121"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-122">Devuelve información sobre las sesiones de transferencia de archivos, incluido el nombre del archivo y si la transferencia fue aceptada, rechazada o cancelada.</span><span class="sxs-lookup"><span data-stu-id="2b615-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b615-123"><a href="lync-server-2013-focusjoinsandleaves-view.md">Vista FocusJoinsAndLeaves en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-123"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-124">Devuelve información sobre las actividades de conexión y desconexión de las conferencias.</span><span class="sxs-lookup"><span data-stu-id="2b615-124">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b615-125"><a href="lync-server-2013-mcujoinsandleaves-view.md">Vista McuJoinsAndLeaves en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-125"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-126">Devuelve información combinada sobre las actividades de conexión y desconexión de las conferencias (cada conexión a la conferencia se encuentra junto con la desconexión de la conferencia correspondiente).</span><span class="sxs-lookup"><span data-stu-id="2b615-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b615-127"><a href="lync-server-2013-mcus-view.md">Vista MCU en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-127"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-128">Devuelve información sobre servidores de conferencias.</span><span class="sxs-lookup"><span data-stu-id="2b615-128">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b615-129"><a href="lync-server-2013-media-view.md">Vista de elementos multimedia en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-129"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-130">Devuelve información acerca de los tipos de medios utilizados en las sesiones de comunicación punto a punto.</span><span class="sxs-lookup"><span data-stu-id="2b615-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b615-131"><a href="lync-server-2013-progressreport-view.md">Vista ProgressReport en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-131"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-132">Devuelve información sobre sesiones completadas.</span><span class="sxs-lookup"><span data-stu-id="2b615-132">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b615-133"><a href="lync-server-2013-registration-view.md">Vista de registro en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-133"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-134">Devuelve información sobre los registros con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b615-134">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b615-135"><a href="lync-server-2013-sessiondetails-view.md">Vista SessionDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-135"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-136">Returns information sobre sesiones punto a punto, incluidas las llamadas telefónicas VoIP-VoIP, las sesiones de mensajería instantánea entre dos participantes u otras sesiones de comunicación punto a punto.</span><span class="sxs-lookup"><span data-stu-id="2b615-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b615-137"><a href="lync-server-2013-user-view.md">Vista de usuario en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-137"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-138">Devuelve información sobre los usuarios que han participado en sesiones de comunicación.</span><span class="sxs-lookup"><span data-stu-id="2b615-138">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b615-139"><a href="lync-server-2013-voipdetails-view.md">Vista VoIPDetails en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b615-139"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2b615-140">Devuelve información para las sesiones punto a punto en las que haya participado al menos un usuario VoIP (Voz sobre IP).</span><span class="sxs-lookup"><span data-stu-id="2b615-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

