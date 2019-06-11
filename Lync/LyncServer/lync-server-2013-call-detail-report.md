---
title: 'Lync Server 2013: informe de detalles de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a258a5c228cfe96218c9c694b05055cc5ebd7eb6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="5c292-102">Informe de detalles de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c292-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c292-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="5c292-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="5c292-104">El informe de detalles de llamadas proporciona un aspecto detallado de una llamada individual. el informe incluye casi toda la calidad de la evaluación de la experiencia y las estadísticas recopiladas por Lync Server, divididas en secciones de informes como:</span><span class="sxs-lookup"><span data-stu-id="5c292-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="5c292-105">Información de llamada</span><span class="sxs-lookup"><span data-stu-id="5c292-105">Call Information</span></span>

  - <span data-ttu-id="5c292-106">Métricas de dispositivo y señal del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="5c292-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="5c292-107">Métricas de dispositivo y señal del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="5c292-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="5c292-108">Evento de cliente de autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="5c292-108">Caller Client Event</span></span>

  - <span data-ttu-id="5c292-109">Evento de cliente de destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="5c292-109">Callee Client Event</span></span>

  - <span data-ttu-id="5c292-110">Secuencia de audio (del autor al destinatario de la llamada)</span><span class="sxs-lookup"><span data-stu-id="5c292-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="5c292-111">Secuencia de vídeo (del autor al destinatario de la llamada)</span><span class="sxs-lookup"><span data-stu-id="5c292-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="5c292-112">Secuencia de audio (del destinatario al autor de la llamada)</span><span class="sxs-lookup"><span data-stu-id="5c292-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="5c292-113">Secuencia de vídeo (del destinatario al autor de la llamada)</span><span class="sxs-lookup"><span data-stu-id="5c292-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="5c292-p101">Tenga en cuenta que las categorías y las métricas que se muestran en los informes depende de dos cosas: el tipo de sesión y el tipo de extremo utilizado en la sesión. Por ejemplo, no se mostrarán métricas de secuencias de vídeos en llamadas solo de audio, ya que la llamada no tiene ninguna secuencia de vídeo. Del mismo modo, puede que tenga un informe en el que solo se muestren estadísticas del autor de la llamada y no del destinatario. Ello se debe a que el destinatario de la llamada no estaba utilizando ningún dispositivo compatible con SIP. Los extremos son responsables de informar de las estadísticas al final de la llamada; pero, un teléfono móvil (que no usa SIP ni estadísticas SIP) no puede informar de este tipo de información. Por ello, si llama a alguien que responde con un teléfono móvil, obtendrá un informe de dicho teléfono móvil cuando finalice la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="5c292-120">El Informe de detalles de llamadas resulta de gran utilidad para determinar exactamente por qué se han registrado problemas de calidad multimedia en una llamada determinada.</span><span class="sxs-lookup"><span data-stu-id="5c292-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="5c292-121">Acceso al Informe de detalles de llamadas</span><span class="sxs-lookup"><span data-stu-id="5c292-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="5c292-122">Es posible tener acceso al Informe de detalles de llamadas desde cualquiera de los informes siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c292-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="5c292-123">El [Informe de ubicación en Lync Server 2013](lync-server-2013-location-report.md) (haciendo clic en el volumen de la llamada o en la métrica de porcentaje de llamada deficiente)</span><span class="sxs-lookup"><span data-stu-id="5c292-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="5c292-124">El [informe Resumen de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (haciendo clic en el volumen de la llamada o en una métrica de porcentaje de llamada deficiente)</span><span class="sxs-lookup"><span data-stu-id="5c292-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="5c292-125">El [Informe de comparación de calidad multimedia en Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (haciendo clic en el [Informe de la lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) y luego en la métrica de detalles).</span><span class="sxs-lookup"><span data-stu-id="5c292-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="5c292-126">El [Informe rendimiento del servidor de Lync Server 2013](lync-server-2013-server-performance-report.md) (haciendo clic en el volumen de la llamada o en una métrica de porcentaje de llamada deficiente)</span><span class="sxs-lookup"><span data-stu-id="5c292-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="5c292-127">[Informe de la lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) (al hacer clic en la métrica de detalles)</span><span class="sxs-lookup"><span data-stu-id="5c292-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="5c292-128">Desde el informe de detalles de llamadas puede acceder al [Informe de dispositivos en Lync Server 2013](lync-server-2013-device-report.md) haciendo clic en cualquiera de las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="5c292-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="5c292-129">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="5c292-129">Capture device</span></span>

  - <span data-ttu-id="5c292-130">Dispositivo de presentación</span><span class="sxs-lookup"><span data-stu-id="5c292-130">Render device</span></span>

<span data-ttu-id="5c292-131">También se puede tener acceso al Informe de tendencias de calidad de medios de servidor haciendo clic en la métrica del servidor perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="5c292-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="5c292-132">Cómo sacar el máximo partido al Informe de detalles de llamadas</span><span class="sxs-lookup"><span data-stu-id="5c292-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="5c292-p102">El Informe de detalles de llamadas incluye más de 250 métricas distintas e incluye elementos como, por ejemplo, el Desfase de marca de tiempo de micrófono, el Tiempo de SNR bajo y el Tiempo de extremo próximo a eco. Si no recuerda qué miden todas estas métricas, coloque el mouse sobre la etiqueta de la métrica para que se muestre información de descripción.</span><span class="sxs-lookup"><span data-stu-id="5c292-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="5c292-135">Si tiene problemas para encontrar una métrica, escriba parte de la etiqueta de métrica en el cuadro de búsqueda y, a continuación, haga clic en buscar.</span><span class="sxs-lookup"><span data-stu-id="5c292-135">If you have problems locating a metric, type part of the metric label in the search box and then click Find.</span></span> <span data-ttu-id="5c292-136">Por ejemplo, si no encuentra la métrica de tiempo de SNR bajo, escriba SNR en el cuadro de búsqueda y, a continuación, haga clic en buscar.</span><span class="sxs-lookup"><span data-stu-id="5c292-136">For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="5c292-p104">Tenga en cuenta que el informe solo sigue la información de una llamada. La llamada propiamente dicha no queda registrada.</span><span class="sxs-lookup"><span data-stu-id="5c292-p104">Note that the report only tracks information about a call. The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5c292-139">Filtros</span><span class="sxs-lookup"><span data-stu-id="5c292-139">Filters</span></span>

<span data-ttu-id="5c292-p105">Ninguno. No se puede filtrar el informe de detalles de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5c292-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5c292-142">Métricas</span><span class="sxs-lookup"><span data-stu-id="5c292-142">Metrics</span></span>

<span data-ttu-id="5c292-143">En la tabla siguiente se muestra la información que recoge el informe de detalles de llamadas sobre cada llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="5c292-144">Métricas del informe de detalles de llamadas</span><span class="sxs-lookup"><span data-stu-id="5c292-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c292-145">Nombre</span><span class="sxs-lookup"><span data-stu-id="5c292-145">Name</span></span></th>
<th><span data-ttu-id="5c292-146">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="5c292-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5c292-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c292-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c292-148"><strong>PAI de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-149">No</span><span class="sxs-lookup"><span data-stu-id="5c292-149">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-p106">P-Asserted-Identity del usuario que inició la llamada. P-Asserted-Identity se utiliza para transmitir la identidad demostrada de un usuario en una red de confianza.</span><span class="sxs-lookup"><span data-stu-id="5c292-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c292-152"><strong>URI de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-153">No</span><span class="sxs-lookup"><span data-stu-id="5c292-153">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-154">Dirección SIP del usuario que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c292-155"><strong>Extremo de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-156">No</span><span class="sxs-lookup"><span data-stu-id="5c292-156">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-157">Dispositivo usado para realizar la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c292-158"><strong>Agente de usuario de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-159">No</span><span class="sxs-lookup"><span data-stu-id="5c292-159">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-160">Software usado en el dispositivo que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c292-161"><strong>Inicio de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-162">No</span><span class="sxs-lookup"><span data-stu-id="5c292-162">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-163">Fecha y hora en las que se realizó inicialmente la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c292-164"><strong>Llamada sin pasar por el servidor de mediación</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-165">No</span><span class="sxs-lookup"><span data-stu-id="5c292-165">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-166">Indica si la llamada se conectó a una puerta de enlace de voz RTC o a un IP PBX cualificado sin pasar por el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="5c292-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c292-167"><strong>Sistema operativo del autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-168">No</span><span class="sxs-lookup"><span data-stu-id="5c292-168">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-169">Sistema operativo del equipo del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c292-170"><strong>CPU de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-171">No</span><span class="sxs-lookup"><span data-stu-id="5c292-171">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-172">CPU instalada en el equipo del usuario que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c292-173"><strong>Número de núcleo de CPU de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-174">No</span><span class="sxs-lookup"><span data-stu-id="5c292-174">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-175">Número de procesador del equipo usado por la persona que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c292-176"><strong>Velocidad de CPU de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-177">No</span><span class="sxs-lookup"><span data-stu-id="5c292-177">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-178">Velocidad del procesador de la CPU del equipo usado por la persona que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c292-179"><strong>Virtualización de CPU de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-180">No</span><span class="sxs-lookup"><span data-stu-id="5c292-180">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-181">Virtualización (si la hay) usada en el equipo de la persona que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c292-182"><strong>PAI de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-183">No</span><span class="sxs-lookup"><span data-stu-id="5c292-183">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-p107">P-Asserted-Identity del usuario invitado a unirse a la llamada. P-Asserted-Identity se utiliza para transmitir la identidad demostrada de un usuario en una red de confianza.</span><span class="sxs-lookup"><span data-stu-id="5c292-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c292-186"><strong>URI de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-187">No</span><span class="sxs-lookup"><span data-stu-id="5c292-187">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-188">Dirección SIP del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c292-189"><strong>Extremo de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-190">No</span><span class="sxs-lookup"><span data-stu-id="5c292-190">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-191">Dispositivo usado para recibir la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c292-192"><strong>Agente de usuario de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-193">No</span><span class="sxs-lookup"><span data-stu-id="5c292-193">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-194">Software usado en el dispositivo que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c292-195"><strong>Duración</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-196">No</span><span class="sxs-lookup"><span data-stu-id="5c292-196">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-197">Duración de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c292-198"><strong>Marcador de advertencia de desvío de medios</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-199">No</span><span class="sxs-lookup"><span data-stu-id="5c292-199">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-200">Advertencia emitida cuando se ignora el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="5c292-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c292-201"><strong>Sistema operativo del destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-202">No</span><span class="sxs-lookup"><span data-stu-id="5c292-202">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-203">Sistema operativo del equipo del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c292-204"><strong>CPU de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-205">No</span><span class="sxs-lookup"><span data-stu-id="5c292-205">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-206">CPU instalada en el equipo del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c292-207"><strong>Número de núcleo de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-208">No</span><span class="sxs-lookup"><span data-stu-id="5c292-208">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-209">Número de procesador del equipo usado por la persona que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c292-210"><strong>Velocidad de CPU de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-211">No</span><span class="sxs-lookup"><span data-stu-id="5c292-211">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-212">Velocidad del procesador de la CPU del equipo usado por la persona que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c292-213"><strong>Virtualización de CPU de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="5c292-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="5c292-214">No</span><span class="sxs-lookup"><span data-stu-id="5c292-214">No</span></span></p></td>
<td><p><span data-ttu-id="5c292-215">Virtualización (si la hay) usada en el equipo de la persona que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="5c292-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

