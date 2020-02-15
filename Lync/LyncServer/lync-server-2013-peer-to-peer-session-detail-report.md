---
title: 'Lync Server 2013: informe de detalles de sesiones punto a punto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c977b2f9f9a6248ab7ba5d5391397d4cd4326a18
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="e81d0-102">Informe de detalles de sesiones punto a punto en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e81d0-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e81d0-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e81d0-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e81d0-p101">El informe de detalles de sesiones punto a punto devuelve información detallada sobre una sesión punto a punto. Por ejemplo, si selecciona una sesión de mensajería instantánea, el informe reflejará el número de mensajes enviado por cada usuario durante la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-p101">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session. For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="e81d0-106">Acceso al informe de detalles de sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="e81d0-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="e81d0-107">Se puede acceder al informe de detalles de sesiones punto a punto desde cualquiera de los siguientes informes (todos se encuentran en la página principal de informes de supervisión):</span><span class="sxs-lookup"><span data-stu-id="e81d0-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="e81d0-108">Informe de inventario de teléfono IP</span><span class="sxs-lookup"><span data-stu-id="e81d0-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="e81d0-109">Informe de actividad de usuario</span><span class="sxs-lookup"><span data-stu-id="e81d0-109">User Activity Report</span></span>

  - <span data-ttu-id="e81d0-110">Informe de control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="e81d0-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="e81d0-111">Informe de lista de errores</span><span class="sxs-lookup"><span data-stu-id="e81d0-111">Failure List Report</span></span>

<span data-ttu-id="e81d0-112">Desde dentro del informe de detalles de sesiones punto a punto, puede tener acceso al [Informe de diagnósticos en Lync Server 2013](lync-server-2013-diagnostic-report.md) haciendo clic en la métrica informe de diagnósticos (detalles).</span><span class="sxs-lookup"><span data-stu-id="e81d0-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="e81d0-113">También se puede acceder al informe de errores principales haciendo clic en cualquiera de estas dos métricas:</span><span class="sxs-lookup"><span data-stu-id="e81d0-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="e81d0-114">Respuesta</span><span class="sxs-lookup"><span data-stu-id="e81d0-114">Response</span></span>

  - <span data-ttu-id="e81d0-115">Id. de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e81d0-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="e81d0-116">Usar el informe de detalles de sesiones punto a punto de la mejor forma posible</span><span class="sxs-lookup"><span data-stu-id="e81d0-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="e81d0-p103">El informe de detalles de sesiones punto a punto condensa un gran número de métricas, de las cuales probablemente muchas no sean muy conocidas para los administradores de sistema. No obstante, muchas veces se puede acceder a información sobre herramientas en la que se ofrece una breve descripción de la métrica; para ello, basta con mantener el mouse encima de la etiqueta de la métrica.</span><span class="sxs-lookup"><span data-stu-id="e81d0-p103">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators. Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="e81d0-p104">Recuerde que las métricas reales que aparecen reflejadas en un informe determinado dependerán del tipo de sesión punto a punto seleccionado. Así, las métricas de una sesión de audio/vídeo serán distintas de las de una sesión de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="e81d0-p104">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected. An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="e81d0-121">El mouse también se puede mantener sobre las métricas Código de respuesta e Id. de diagnóstico para obtener una descripción de dichos valores:</span><span class="sxs-lookup"><span data-stu-id="e81d0-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e81d0-122">Filtros</span><span class="sxs-lookup"><span data-stu-id="e81d0-122">Filters</span></span>

<span data-ttu-id="e81d0-p105">Ninguno. El informe de detalles de sesiones punto a punto no se puede filtrar.</span><span class="sxs-lookup"><span data-stu-id="e81d0-p105">None. You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="e81d0-125">Métricas de información de la sesión</span><span class="sxs-lookup"><span data-stu-id="e81d0-125">Session Information Metrics</span></span>

<span data-ttu-id="e81d0-126">En la siguiente tabla se recoge la información que el informe de detalles de sesiones punto a punto proporciona sobre cada sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="e81d0-127">Métricas de información de la sesión</span><span class="sxs-lookup"><span data-stu-id="e81d0-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e81d0-128">Nombre</span><span class="sxs-lookup"><span data-stu-id="e81d0-128">Name</span></span></th>
<th><span data-ttu-id="e81d0-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="e81d0-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-130"><strong>FQDN del grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-131">Nombre de dominio completo (FQDN) del grupo de registrador o servidor perimetral involucrado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-132"><strong>Hora de invitación</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-133">Fecha y hora en que se envió inicialmente la invitación a la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-134"><strong>Tiempo de respuesta</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-135">Fecha y hora en que se recibió la aceptación de la invitación.</span><span class="sxs-lookup"><span data-stu-id="e81d0-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-136"><strong>Remitente</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-137">Dirección SIP del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-138"><strong>Agente de remitente</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-139">Software que utiliza el extremo del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-140"><strong>¿Es el remitente interno?</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-141">Indica si el usuario que inició la sesión estaba conectado a la red interna.</span><span class="sxs-lookup"><span data-stu-id="e81d0-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-142"><strong>¿Tiene el remitente un teléfono de escritorio integrado?</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-143">Indica si el extremo que utilizó el usuario que inició sesión está integrado en su teléfono de escritorio integrado.</span><span class="sxs-lookup"><span data-stu-id="e81d0-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-144"><strong>Prioridad de sesión</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-p106">Prioridad asignada a la sesión. Entre las propiedades válidas se encuentran Desconocido, No urgente, Normal, Urgente y Emergencia.</span><span class="sxs-lookup"><span data-stu-id="e81d0-p106">Priority assigned to the session. Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-147"><strong>Código de respuesta</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-148">Código de respuesta SIP enviado cuando se produjo un error en la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-149"><strong>Front-end</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-150">Nombre del servidor front-end que se usó en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="e81d0-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-151"><strong>Hora de captura</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-152">Fecha y hora en que se registró la información de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-153"><strong>Hora de finalización</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-154">Fecha y hora en que la sesión finalizó.</span><span class="sxs-lookup"><span data-stu-id="e81d0-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-155"><strong>Destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-156">Dirección SIP del usuario invitado a la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-157"><strong>Agente de destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-158">Software utilizado por el extremo del usuario invitado a la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-159"><strong>¿Es el destinatario interno?</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-160">Indica si el usuario invitado a la sesión estaba conectado a la red interna.</span><span class="sxs-lookup"><span data-stu-id="e81d0-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-161"><strong>¿Tiene el destinatario un teléfono de escritorio integrado?</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-162">Indica si el extremo que utilizó el usuario invitado a la sesión está integrado en su teléfono de escritorio integrado.</span><span class="sxs-lookup"><span data-stu-id="e81d0-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-163"><strong>¿Es un reintento de sesión?</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-164">Indica si se trata de un reintento de una sesión que no se pudo iniciar correctamente.</span><span class="sxs-lookup"><span data-stu-id="e81d0-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-165"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-p107">Identificador único (en forma de encabezado de tipo ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información de utilidad para resolver errores. Mantenga el mouse encima del número del identificador para ver más información al respecto.</span><span class="sxs-lookup"><span data-stu-id="e81d0-p107">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="e81d0-168">Métricas de modalidades</span><span class="sxs-lookup"><span data-stu-id="e81d0-168">Metrics for Modalities</span></span>

<span data-ttu-id="e81d0-169">En la siguiente tabla se recoge la información que el informe de detalles de sesiones punto a punto proporciona sobre cada modalidad de sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="e81d0-170">Métricas de modalidades</span><span class="sxs-lookup"><span data-stu-id="e81d0-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e81d0-171">Nombre</span><span class="sxs-lookup"><span data-stu-id="e81d0-171">Name</span></span></th>
<th><span data-ttu-id="e81d0-172">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="e81d0-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e81d0-173">Descripción</span><span class="sxs-lookup"><span data-stu-id="e81d0-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-174"><strong>Modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-175">No</span><span class="sxs-lookup"><span data-stu-id="e81d0-175">No</span></span></p></td>
<td><p><span data-ttu-id="e81d0-p108">Modalidades usadas en la sesión (por ejemplo, mensajería instantánea o transferencia de archivos).</span><span class="sxs-lookup"><span data-stu-id="e81d0-p108">Modalities used in the session. For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-178"><strong>Mensajes del remitente</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-179">No</span><span class="sxs-lookup"><span data-stu-id="e81d0-179">No</span></span></p></td>
<td><p><span data-ttu-id="e81d0-180">Número de mensajes que envió el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-181"><strong>Mensajes del destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-182">No</span><span class="sxs-lookup"><span data-stu-id="e81d0-182">No</span></span></p></td>
<td><p><span data-ttu-id="e81d0-183">Número de mensajes que envió el usuario invitado a unirse a la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="e81d0-184">Métricas de informes de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e81d0-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="e81d0-185">En la siguiente tabla se recoge la información que el informe de detalles de sesiones punto a punto proporciona sobre cada informe de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e81d0-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="e81d0-186">Métricas de informes de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e81d0-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e81d0-187">Nombre</span><span class="sxs-lookup"><span data-stu-id="e81d0-187">Name</span></span></th>
<th><span data-ttu-id="e81d0-188">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="e81d0-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e81d0-189">Descripción</span><span class="sxs-lookup"><span data-stu-id="e81d0-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-190"><strong>Detalle</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-191">No</span><span class="sxs-lookup"><span data-stu-id="e81d0-191">No</span></span></p></td>
<td><p><span data-ttu-id="e81d0-192">Cuando se hace clic en este elemento, el informe muestra el informe de diagnóstico correspondiente a la sesión.</span><span class="sxs-lookup"><span data-stu-id="e81d0-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-193"><strong>Hora del informe</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-194">No</span><span class="sxs-lookup"><span data-stu-id="e81d0-194">No</span></span></p></td>
<td><p><span data-ttu-id="e81d0-195">Fecha y hora en que se registró el informe.</span><span class="sxs-lookup"><span data-stu-id="e81d0-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-196"><strong>Solicitud</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-197">No</span><span class="sxs-lookup"><span data-stu-id="e81d0-197">No</span></span></p></td>
<td><p><span data-ttu-id="e81d0-p109">Tipo de solicitud SIP (por ejemplo, INVITE o BYE).</span><span class="sxs-lookup"><span data-stu-id="e81d0-p109">SIP request type. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-200"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-201">No</span><span class="sxs-lookup"><span data-stu-id="e81d0-201">No</span></span></p></td>
<td><p><span data-ttu-id="e81d0-202">Identificador único (en forma de encabezado de tipo ms-diagnostics) que se adjunta a un mensaje SIP y que suele ofrecer información de utilidad para resolver errores.</span><span class="sxs-lookup"><span data-stu-id="e81d0-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e81d0-203"><strong>Tipo de contenido</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-204">No</span><span class="sxs-lookup"><span data-stu-id="e81d0-204">No</span></span></p></td>
<td><p><span data-ttu-id="e81d0-p110">Tipo de contenido multimedia usado en la conferencia (por ejemplo, un tipo de contenido bastante habitual es Application/sdp). El protocolo SDP es un protocolo de Internet estándar que se usa en anuncios de sesiones, invitaciones a sesiones y otras formas de inicio de sesiones multimedia.</span><span class="sxs-lookup"><span data-stu-id="e81d0-p110">Type of media content used in the conference. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e81d0-208"><strong>Informe realizado por</strong></span><span class="sxs-lookup"><span data-stu-id="e81d0-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="e81d0-209">No</span><span class="sxs-lookup"><span data-stu-id="e81d0-209">No</span></span></p></td>
<td><p><span data-ttu-id="e81d0-210">Equipo (cliente o servidor) que notificó el problema.</span><span class="sxs-lookup"><span data-stu-id="e81d0-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

