---
title: 'Lync Server 2013: informe detallado de la Conferencia'
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
ms.openlocfilehash: 7e8e2cd992e83adb29c43935d4b4c7f223580d53
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="7d7d8-102">Informe detallado de la Conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d7d8-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d7d8-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7d7d8-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7d7d8-p101">El Informe de detalles de conferencia proporciona información detallada sobre todos los usuarios que participaron en una conferencia. Por ejemplo, puede ver información como la fecha y hora en que un usuario se conectó a la conferencia, la fecha y hora en la que el usuario se desconectó de la conferencia y el agente del usuario del extremo que se utilizó para conectar a ese usuario a la conferencia. También puede ver información sobre el rol del usuario en cada conferencia (por ejemplo, moderador o asistente). Quizás lo más importante, puede ver rápidamente qué usuarios se conectan satisfactoriamente y finalizan la conferencia y qué usuarios no pudieron conectarse satisfactoriamente ni finalizar la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="7d7d8-108">Acceso al Informe de detalles de conferencia</span><span class="sxs-lookup"><span data-stu-id="7d7d8-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="7d7d8-109">Es posible obtener acceso al Informe de detalles de conferencia a partir de los siguientes informes:</span><span class="sxs-lookup"><span data-stu-id="7d7d8-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="7d7d8-110">El [Informe de control de admisión de llamadas en Lync Server 2013](lync-server-2013-call-admission-control-report.md) (al hacer clic en la métrica de detalle de una conferencia)</span><span class="sxs-lookup"><span data-stu-id="7d7d8-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="7d7d8-111">El [informe lista de errores de Lync Server 2013](lync-server-2013-failure-list-report.md) (al hacer clic en la métrica de la Conferencia)</span><span class="sxs-lookup"><span data-stu-id="7d7d8-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="7d7d8-112">[Informe de actividad de usuario en Lync Server 2013](lync-server-2013-user-activity-report.md) (al hacer clic en la métrica de URI de la Conferencia)</span><span class="sxs-lookup"><span data-stu-id="7d7d8-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="7d7d8-113">En el informe de detalles de la Conferencia, puede acceder al [Informe de diagnóstico en Lync Server 2013](lync-server-2013-diagnostic-report.md) haciendo clic en la métrica de informe de diagnóstico (detalles).</span><span class="sxs-lookup"><span data-stu-id="7d7d8-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7d7d8-114">Filtros</span><span class="sxs-lookup"><span data-stu-id="7d7d8-114">Filters</span></span>

<span data-ttu-id="7d7d8-p102">Ninguno. No se puede filtrar el Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7d7d8-117">Métricas</span><span class="sxs-lookup"><span data-stu-id="7d7d8-117">Metrics</span></span>

<span data-ttu-id="7d7d8-118">La siguiente tabla muestra la información brindada en la sección Información de conferencia del Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="7d7d8-119">Métricas de Información de conferencia</span><span class="sxs-lookup"><span data-stu-id="7d7d8-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d7d8-120">Nombre</span><span class="sxs-lookup"><span data-stu-id="7d7d8-120">Name</span></span></th>
<th><span data-ttu-id="7d7d8-121">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="7d7d8-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7d7d8-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d7d8-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d7d8-123"><strong>URI de conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-p103">URI asignado a la conferencia. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d7d8-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="7d7d8-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="7d7d8-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d7d8-127"><strong>FQDN del grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-128">Nombre de dominio completo del grupo de registrador o servidor perimetral involucrado en una sesión.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d7d8-129"><strong>Hora de inicio</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-130">Fecha y hora en que comenzó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d7d8-131"><strong>Organizador</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-132">Dirección SIP del usuario que organizó la conferencia</span><span class="sxs-lookup"><span data-stu-id="7d7d8-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d7d8-133"><strong>Hora de finalización</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-134">Fecha y hora en que la conferencia finalizó.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7d7d8-135">La siguiente tabla muestra la información brindada en la sección Participación de conferencia del Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="7d7d8-136">Métricas de Participación de conferencia</span><span class="sxs-lookup"><span data-stu-id="7d7d8-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d7d8-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="7d7d8-137">Name</span></span></th>
<th><span data-ttu-id="7d7d8-138">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="7d7d8-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7d7d8-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d7d8-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d7d8-140"><strong>Usuario</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-141">Dirección SIP del usuario que participó en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d7d8-142"><strong>Rol</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-143">Rol (por ejemplo, Moderador) que ocupó el participante de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d7d8-144"><strong>Conectividad</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-145">Conectividad de red (normalmente Desde conexión interna o Desde conexión externa) del participante.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d7d8-146">Hora de conexión</span><span class="sxs-lookup"><span data-stu-id="7d7d8-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-147">Fecha y hora en que el participante se unió a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d7d8-148"><strong>Hora de desconexión</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-149">Fecha y hora en que el participante abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d7d8-150"><strong>Agente de usuario</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-151">Identificador del software del extremo del participante.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d7d8-152"><strong>Informes de diagnósticos</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-p104">Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7d7d8-155">En la tabla siguiente se enumera la información proporcionada en la sección modalidades de conferencia del informe detalles de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="7d7d8-156">Métricas de Modalidades de conferencia</span><span class="sxs-lookup"><span data-stu-id="7d7d8-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d7d8-157">Nombre</span><span class="sxs-lookup"><span data-stu-id="7d7d8-157">Name</span></span></th>
<th><span data-ttu-id="7d7d8-158">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="7d7d8-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7d7d8-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d7d8-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d7d8-160"><strong>Usuario</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-161">Dirección SIP del usuario que participó en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d7d8-162"><strong>Hora de conexión</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-163">Fecha y hora en que el participante se unió a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d7d8-164"><strong>Hora de desconexión</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-165">Fecha y hora en que un participante abandonó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d7d8-166"><strong>URI del servidor de conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-167">URI para el servidor de conferencia utilizado en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d7d8-168"><strong>Informes de diagnósticos</strong></span><span class="sxs-lookup"><span data-stu-id="7d7d8-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d7d8-p105">Proporciona información de diagnóstico y resolución de problemas. Por ejemplo, códigos de respuesta SIP, encabezados de diagnóstico, horarios de conexión a conferencias e identificadores de diagnóstico para sesiones fallidas.</span><span class="sxs-lookup"><span data-stu-id="7d7d8-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

