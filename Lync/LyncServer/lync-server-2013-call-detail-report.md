---
title: 'Lync Server 2013: informe de detalles de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e14ca8565216efbdeaae3060587d5d18d919876
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="c329f-102">Informe de detalles de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c329f-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c329f-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="c329f-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="c329f-104">El informe de detalles de llamadas proporciona un aspecto detallado de una llamada individual; el informe incluye casi todas las métricas de calidad de la experiencia y las estadísticas recopiladas por Lync Server, divididas en secciones de informes como:</span><span class="sxs-lookup"><span data-stu-id="c329f-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="c329f-105">Información de llamada</span><span class="sxs-lookup"><span data-stu-id="c329f-105">Call Information</span></span>

  - <span data-ttu-id="c329f-106">Métricas de dispositivo y señal del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="c329f-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="c329f-107">Métricas de dispositivo y señal del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="c329f-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="c329f-108">Evento de cliente de autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="c329f-108">Caller Client Event</span></span>

  - <span data-ttu-id="c329f-109">Evento de cliente de destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="c329f-109">Callee Client Event</span></span>

  - <span data-ttu-id="c329f-110">Secuencia de audio (del autor al destinatario de la llamada)</span><span class="sxs-lookup"><span data-stu-id="c329f-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="c329f-111">Secuencia de vídeo (del autor al destinatario de la llamada)</span><span class="sxs-lookup"><span data-stu-id="c329f-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="c329f-112">Secuencia de audio (del destinatario al autor de la llamada)</span><span class="sxs-lookup"><span data-stu-id="c329f-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="c329f-113">Secuencia de vídeo (del destinatario al autor de la llamada)</span><span class="sxs-lookup"><span data-stu-id="c329f-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="c329f-p101">Tenga en cuenta que las categorías y las métricas que se muestran en los informes depende de dos cosas: el tipo de sesión y el tipo de extremo utilizado en la sesión. Por ejemplo, no se mostrarán métricas de secuencias de vídeos en llamadas solo de audio, ya que la llamada no tiene ninguna secuencia de vídeo. Del mismo modo, puede que tenga un informe en el que solo se muestren estadísticas del autor de la llamada y no del destinatario. Ello se debe a que el destinatario de la llamada no estaba utilizando ningún dispositivo compatible con SIP. Los extremos son responsables de informar de las estadísticas al final de la llamada; sin embargo, un teléfono móvil (que no usa SIP ni estadísticas SIP) no puede informar de este tipo de información. Por ello, si llama a alguien que responde con un teléfono móvil, obtendrá un informe de dicho teléfono móvil cuando finalice la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="c329f-120">El Informe de detalles de llamadas resulta de gran utilidad para determinar exactamente por qué se han registrado problemas de calidad multimedia en una llamada determinada.</span><span class="sxs-lookup"><span data-stu-id="c329f-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="c329f-121">Acceso al Informe de detalles de llamadas</span><span class="sxs-lookup"><span data-stu-id="c329f-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="c329f-122">Es posible tener acceso al Informe de detalles de llamadas desde cualquiera de los informes siguientes:</span><span class="sxs-lookup"><span data-stu-id="c329f-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="c329f-123">El [Informe de ubicación en Lync Server 2013](lync-server-2013-location-report.md) (haciendo clic en el volumen de llamadas o en la métrica de porcentaje de llamadas deficientes)</span><span class="sxs-lookup"><span data-stu-id="c329f-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="c329f-124">El [Informe de Resumen de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (haciendo clic en la métrica porcentaje de llamadas defectuosas o volumen de llamadas)</span><span class="sxs-lookup"><span data-stu-id="c329f-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="c329f-125">El [Informe de comparación de calidad de medios en Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (haciendo clic en el [Informe de lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) y, a continuación, haciendo clic en la métrica detalles).</span><span class="sxs-lookup"><span data-stu-id="c329f-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="c329f-126">El [Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md) (haciendo clic en la métrica porcentaje de llamadas defectuosas o volumen de llamadas)</span><span class="sxs-lookup"><span data-stu-id="c329f-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="c329f-127">El [Informe de lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) (haciendo clic en la métrica detalles)</span><span class="sxs-lookup"><span data-stu-id="c329f-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="c329f-128">Desde el informe de detalles de llamadas, puede acceder al [Informe de dispositivos en Lync Server 2013](lync-server-2013-device-report.md) haciendo clic en cualquiera de las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c329f-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="c329f-129">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="c329f-129">Capture device</span></span>

  - <span data-ttu-id="c329f-130">Dispositivo de presentación</span><span class="sxs-lookup"><span data-stu-id="c329f-130">Render device</span></span>

<span data-ttu-id="c329f-131">También se puede tener acceso al Informe de tendencias de calidad de medios de servidor haciendo clic en la métrica del servidor perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="c329f-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="c329f-132">Cómo sacar el máximo partido al Informe de detalles de llamadas</span><span class="sxs-lookup"><span data-stu-id="c329f-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="c329f-p102">El Informe de detalles de llamadas incluye más de 250 métricas distintas e incluye elementos como, por ejemplo, el Desfase de marca de tiempo de micrófono, el Tiempo de SNR bajo y el Tiempo de extremo próximo a eco. Si no recuerda qué miden todas estas métricas, coloque el mouse sobre la etiqueta de la métrica para que se muestre información de descripción.</span><span class="sxs-lookup"><span data-stu-id="c329f-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="c329f-p103">Si tiene problemas para encontrar una métrica, escriba una parte del nombre de la métrica en el cuadro de búsqueda y haga clic en Buscar. Por ejemplo, si no encuentra la métrica Tiempo de SNR bajo, escriba SNR en el cuadro de búsqueda y, a continuación, haga clic en Buscar.</span><span class="sxs-lookup"><span data-stu-id="c329f-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="c329f-137">Tenga en cuenta que el informe solo realiza un seguimiento de la información sobre una llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-137">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="c329f-138">No se registra la propia llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-138">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c329f-139">Filtros</span><span class="sxs-lookup"><span data-stu-id="c329f-139">Filters</span></span>

<span data-ttu-id="c329f-p105">Ninguno. No se puede filtrar el informe de detalles de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c329f-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c329f-142">Métricas</span><span class="sxs-lookup"><span data-stu-id="c329f-142">Metrics</span></span>

<span data-ttu-id="c329f-143">En la tabla siguiente se muestra la información que recoge el informe de detalles de llamadas sobre cada llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="c329f-144">Métricas del informe de detalles de llamadas</span><span class="sxs-lookup"><span data-stu-id="c329f-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c329f-145">Nombre</span><span class="sxs-lookup"><span data-stu-id="c329f-145">Name</span></span></th>
<th><span data-ttu-id="c329f-146">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="c329f-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c329f-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="c329f-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c329f-148"><strong>PAI de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-149">No</span><span class="sxs-lookup"><span data-stu-id="c329f-149">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-p106">P-Asserted-Identity del usuario que inició la llamada. P-Asserted-Identity se utiliza para transmitir la identidad demostrada de un usuario en una red de confianza.</span><span class="sxs-lookup"><span data-stu-id="c329f-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c329f-152"><strong>URI de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-153">No</span><span class="sxs-lookup"><span data-stu-id="c329f-153">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-154">Dirección SIP del usuario que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c329f-155"><strong>Extremo de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-156">No</span><span class="sxs-lookup"><span data-stu-id="c329f-156">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-157">Dispositivo usado para realizar la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c329f-158"><strong>Agente de usuario de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-159">No</span><span class="sxs-lookup"><span data-stu-id="c329f-159">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-160">Software usado en el dispositivo que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c329f-161"><strong>Inicio de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-162">No</span><span class="sxs-lookup"><span data-stu-id="c329f-162">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-163">Fecha y hora en las que se realizó inicialmente la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c329f-164"><strong>Llamada sin pasar por el servidor de mediación</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-165">No</span><span class="sxs-lookup"><span data-stu-id="c329f-165">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-166">Indica si la llamada se conectó a una puerta de enlace de voz RTC o a un IP PBX cualificado sin pasar por el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c329f-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c329f-167"><strong>Sistema operativo del autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-168">No</span><span class="sxs-lookup"><span data-stu-id="c329f-168">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-169">Sistema operativo del equipo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c329f-170"><strong>CPU de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-171">No</span><span class="sxs-lookup"><span data-stu-id="c329f-171">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-172">CPU instalada en el equipo del usuario que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c329f-173"><strong>Número de núcleo de CPU de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-174">No</span><span class="sxs-lookup"><span data-stu-id="c329f-174">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-175">Número de procesador del equipo usado por la persona que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c329f-176"><strong>Velocidad de CPU de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-177">No</span><span class="sxs-lookup"><span data-stu-id="c329f-177">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-178">Velocidad del procesador de la CPU del equipo usado por la persona que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c329f-179"><strong>Virtualización de CPU de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-180">No</span><span class="sxs-lookup"><span data-stu-id="c329f-180">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-181">Virtualización (si la hay) usada en el equipo de la persona que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c329f-182"><strong>PAI de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-183">No</span><span class="sxs-lookup"><span data-stu-id="c329f-183">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-p107">P-Asserted-Identity del usuario invitado a unirse a la llamada. P-Asserted-Identity se utiliza para transmitir la identidad demostrada de un usuario en una red de confianza.</span><span class="sxs-lookup"><span data-stu-id="c329f-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c329f-186"><strong>URI de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-187">No</span><span class="sxs-lookup"><span data-stu-id="c329f-187">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-188">Dirección SIP del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c329f-189"><strong>Extremo de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-190">No</span><span class="sxs-lookup"><span data-stu-id="c329f-190">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-191">Dispositivo usado para recibir la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c329f-192"><strong>Agente de usuario de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-193">No</span><span class="sxs-lookup"><span data-stu-id="c329f-193">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-194">Software usado en el dispositivo que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c329f-195"><strong>Duración</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-196">No</span><span class="sxs-lookup"><span data-stu-id="c329f-196">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-197">Duración de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c329f-198"><strong>Marcador de advertencia de desvío de medios</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-199">No</span><span class="sxs-lookup"><span data-stu-id="c329f-199">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-200">Advertencia emitida cuando se ignora el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c329f-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c329f-201"><strong>Sistema operativo del destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-202">No</span><span class="sxs-lookup"><span data-stu-id="c329f-202">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-203">Sistema operativo del equipo del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c329f-204"><strong>CPU de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-205">No</span><span class="sxs-lookup"><span data-stu-id="c329f-205">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-206">CPU instalada en el equipo del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c329f-207"><strong>Número de núcleo de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-208">No</span><span class="sxs-lookup"><span data-stu-id="c329f-208">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-209">Número de procesador del equipo usado por la persona que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c329f-210"><strong>Velocidad de CPU de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-211">No</span><span class="sxs-lookup"><span data-stu-id="c329f-211">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-212">Velocidad del procesador de la CPU del equipo usado por la persona que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c329f-213"><strong>Virtualización de CPU de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="c329f-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="c329f-214">No</span><span class="sxs-lookup"><span data-stu-id="c329f-214">No</span></span></p></td>
<td><p><span data-ttu-id="c329f-215">Virtualización (si la hay) usada en el equipo de la persona que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="c329f-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

