---
title: 'Lync Server 2013: informe de detalles de conferencia'
description: 'Lync Server 2013: informe de detalles de conferencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07c50b545f4a9ee3308a840fc2aa5a15e617a5bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577636"
---
# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="7da6d-103">Informe de detalles de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7da6d-103">Conference Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7da6d-104">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7da6d-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7da6d-p101">El Informe de detalles de conferencia proporciona información detallada sobre todos los usuarios que participaron en una conferencia. Por ejemplo, puede ver información como la fecha y hora en que un usuario se conectó a la conferencia, la fecha y hora en la que el usuario se desconectó de la conferencia y el agente del usuario del extremo que se utilizó para conectar a ese usuario a la conferencia. También puede ver información sobre el rol del usuario en cada conferencia (por ejemplo, moderador o asistente). Quizás lo más importante, puede ver rápidamente qué usuarios se conectan satisfactoriamente y finalizan la conferencia y qué usuarios no pudieron conectarse satisfactoriamente ni finalizar la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="7da6d-109">Acceso al Informe de detalles de conferencia</span><span class="sxs-lookup"><span data-stu-id="7da6d-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="7da6d-110">Es posible acceder al Informe de detalles de conferencia a partir de los siguientes informes:</span><span class="sxs-lookup"><span data-stu-id="7da6d-110">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="7da6d-111">El [Informe de control de admisión de llamadas en Lync Server 2013](lync-server-2013-call-admission-control-report.md) (haciendo clic en la métrica detalle de una conferencia)</span><span class="sxs-lookup"><span data-stu-id="7da6d-111">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="7da6d-112">El [Informe de lista de errores en Lync Server 2013](lync-server-2013-failure-list-report.md) (haciendo clic en la métrica de conferencia)</span><span class="sxs-lookup"><span data-stu-id="7da6d-112">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="7da6d-113">El [Informe de actividad de usuario en Lync Server 2013](lync-server-2013-user-activity-report.md) (haciendo clic en la métrica URI de conferencia)</span><span class="sxs-lookup"><span data-stu-id="7da6d-113">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="7da6d-114">Desde el informe de detalles de conferencia, puede tener acceso al [Informe de diagnósticos en Lync Server 2013](lync-server-2013-diagnostic-report.md) haciendo clic en la métrica informe de diagnósticos (detalle).</span><span class="sxs-lookup"><span data-stu-id="7da6d-114">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7da6d-115">Filtros</span><span class="sxs-lookup"><span data-stu-id="7da6d-115">Filters</span></span>

<span data-ttu-id="7da6d-p102">Ninguno. No se puede filtrar el Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7da6d-118">Métricas</span><span class="sxs-lookup"><span data-stu-id="7da6d-118">Metrics</span></span>

<span data-ttu-id="7da6d-119">La siguiente tabla muestra la información brindada en la sección Información de conferencia del Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="7da6d-120">Métricas de Información de conferencia</span><span class="sxs-lookup"><span data-stu-id="7da6d-120">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7da6d-121">Nombre</span><span class="sxs-lookup"><span data-stu-id="7da6d-121">Name</span></span></th>
<th><span data-ttu-id="7da6d-122">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="7da6d-122">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7da6d-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="7da6d-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7da6d-124"><strong>URI de conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-124"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-p103">URI asignado a la conferencia. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7da6d-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="7da6d-127">SIP: kmyer@litwareinc. com; gruu; Opaque = App: conf: Focus: ID: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="7da6d-127">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da6d-128"><strong>FQDN del grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-128"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-129">Nombre de dominio completo del grupo de registrador o servidor perimetral involucrado en una sesión.</span><span class="sxs-lookup"><span data-stu-id="7da6d-129">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da6d-130"><strong>Hora de inicio</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-130"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-131">Fecha y hora en que comenzó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-131">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da6d-132"><strong>Organizador</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-132"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-133">Dirección SIP del usuario que organizó la conferencia</span><span class="sxs-lookup"><span data-stu-id="7da6d-133">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da6d-134"><strong>Hora de finalización</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-134"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-135">Fecha y hora en que finalizó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-135">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7da6d-136">La siguiente tabla muestra la información brindada en la sección Participación de conferencia del Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-136">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="7da6d-137">Métricas de Participación de conferencia</span><span class="sxs-lookup"><span data-stu-id="7da6d-137">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7da6d-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="7da6d-138">Name</span></span></th>
<th><span data-ttu-id="7da6d-139">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="7da6d-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7da6d-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="7da6d-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7da6d-141"><strong>Usuario</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-141"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-142">Dirección SIP del usuario que participó en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-142">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da6d-143"><strong>Rol</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-143"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-144">Rol (por ejemplo, Moderador) que ocupó el participante de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-144">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da6d-145"><strong>Conectividad</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-145"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-146">Conectividad de red (normalmente Desde conexión interna o Desde conexión externa) del participante.</span><span class="sxs-lookup"><span data-stu-id="7da6d-146">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da6d-147">Hora de conexión</span><span class="sxs-lookup"><span data-stu-id="7da6d-147">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-148">Fecha y hora en que el participante se unió a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-148">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da6d-149"><strong>Hora de desconexión</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-149"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-150">Fecha y hora en que el participante abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-150">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da6d-151"><strong>Agente de usuario</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-151"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-152">Identificador del software del extremo del participante.</span><span class="sxs-lookup"><span data-stu-id="7da6d-152">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da6d-153"><strong>Informes de diagnósticos</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-153"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-p104">Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.</span><span class="sxs-lookup"><span data-stu-id="7da6d-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7da6d-156">En la siguiente tabla se muestra la información proporcionada en la sección modalidades de conferencia del informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-156">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="7da6d-157">Métricas de Modalidades de conferencia</span><span class="sxs-lookup"><span data-stu-id="7da6d-157">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7da6d-158">Nombre</span><span class="sxs-lookup"><span data-stu-id="7da6d-158">Name</span></span></th>
<th><span data-ttu-id="7da6d-159">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="7da6d-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7da6d-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="7da6d-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7da6d-161"><strong>Usuario</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-161"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-162">Dirección SIP del usuario que participó en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-162">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da6d-163"><strong>Hora de conexión</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-163"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-164">Fecha y hora en que el participante se unió a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-164">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da6d-165"><strong>Hora de desconexión</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-165"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-166">Fecha y hora en que un participante abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-166">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7da6d-167"><strong>URI del servidor de conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-167"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-168">URI para el servidor de conferencia utilizado en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7da6d-168">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7da6d-169"><strong>Informes de diagnósticos</strong></span><span class="sxs-lookup"><span data-stu-id="7da6d-169"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7da6d-p105">Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.</span><span class="sxs-lookup"><span data-stu-id="7da6d-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

