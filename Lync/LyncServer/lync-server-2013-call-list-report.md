---
title: 'Lync Server 2013: informe de lista de llamadas'
description: 'Lync Server 2013: informe de lista de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b08d4c5f3011facc9cd8d4f6b2800638f3cc896
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561696"
---
# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="66cdd-103">Informe de lista de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66cdd-103">Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66cdd-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="66cdd-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="66cdd-105">El informe de lista de llamadas proporciona métricas de la calidad de la experiencia (QoE) para las llamadas individuales realizadas y recibidas en su organización.</span><span class="sxs-lookup"><span data-stu-id="66cdd-105">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="66cdd-106">Tenga en cuenta que las métricas reales que se notifiquen dependerán de cómo obtenga acceso al informe de lista de llamadas.</span><span class="sxs-lookup"><span data-stu-id="66cdd-106">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="66cdd-107">Por ejemplo, si abre el informe desde el [Informe de dispositivos en Lync Server 2013](lync-server-2013-device-report.md), verá métricas como las siguientes, métricas que también se notifican en el informe de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="66cdd-107">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="66cdd-108">Micrófono del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="66cdd-108">Caller's microphone</span></span>

  - <span data-ttu-id="66cdd-109">Altavoz del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="66cdd-109">Caller's speaker</span></span>

  - <span data-ttu-id="66cdd-110">Micrófono del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="66cdd-110">Callee's microphone</span></span>

  - <span data-ttu-id="66cdd-111">Altavoz del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="66cdd-111">Callee's speaker</span></span>

  - <span data-ttu-id="66cdd-112">Relación de tiempo de conmutación de voz</span><span class="sxs-lookup"><span data-stu-id="66cdd-112">Ratio of voice switch time</span></span>

<span data-ttu-id="66cdd-113">Sin embargo, si abre el informe de lista de llamadas desde el [Informe de ubicación en Lync Server 2013](lync-server-2013-location-report.md), no verá ninguna de estas métricas; en su lugar, verá métricas como estas:</span><span class="sxs-lookup"><span data-stu-id="66cdd-113">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="66cdd-114">Recorrido de ida y vuelta (ms)</span><span class="sxs-lookup"><span data-stu-id="66cdd-114">Round trip (ms)</span></span>

  - <span data-ttu-id="66cdd-115">Degradación (MOS)</span><span class="sxs-lookup"><span data-stu-id="66cdd-115">Degradation (MOS)</span></span>

  - <span data-ttu-id="66cdd-116">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="66cdd-116">Packet loss</span></span>

  - <span data-ttu-id="66cdd-117">Vibración (ms)</span><span class="sxs-lookup"><span data-stu-id="66cdd-117">Jitter (ms)</span></span>

<span data-ttu-id="66cdd-118">Esas son las métricas que se indican en el informe de ubicación.</span><span class="sxs-lookup"><span data-stu-id="66cdd-118">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="66cdd-119">Sin embargo, en el informe de lista de llamadas, siempre puede hacer clic en la métrica de detalles para proporcionar la información completa de QoE para cada llamada.</span><span class="sxs-lookup"><span data-stu-id="66cdd-119">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="66cdd-120">Acceso al informe de lista de llamadas</span><span class="sxs-lookup"><span data-stu-id="66cdd-120">Accessing the Call List Report</span></span>

<span data-ttu-id="66cdd-121">Se puede tener acceso al informe de lista de llamadas desde cualquiera de los siguientes informes:</span><span class="sxs-lookup"><span data-stu-id="66cdd-121">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="66cdd-122">El [Informe de ubicación en Lync Server 2013](lync-server-2013-location-report.md) (haciendo clic en el volumen de llamadas o en la métrica de porcentaje de llamadas deficientes)</span><span class="sxs-lookup"><span data-stu-id="66cdd-122">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="66cdd-123">El [Informe de dispositivos en Lync Server 2013](lync-server-2013-device-report.md) (haciendo clic en el volumen de llamadas o en la métrica de porcentaje de llamadas deficientes)</span><span class="sxs-lookup"><span data-stu-id="66cdd-123">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="66cdd-124">El [Informe de Resumen de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (haciendo clic en el volumen de llamadas o en la métrica de porcentaje de llamadas deficientes)</span><span class="sxs-lookup"><span data-stu-id="66cdd-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="66cdd-125">El [Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md) (haciendo clic en el volumen de llamadas o en la métrica de porcentaje de llamadas deficientes)</span><span class="sxs-lookup"><span data-stu-id="66cdd-125">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="66cdd-126">Desde el informe de lista de llamadas puede tener acceso al [Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md) haciendo clic en la métrica detalles.</span><span class="sxs-lookup"><span data-stu-id="66cdd-126">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="66cdd-127">Aprovechar al máximo el informe de lista de llamadas</span><span class="sxs-lookup"><span data-stu-id="66cdd-127">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="66cdd-128">Si no recuerda lo que algunas de las métricas del informe de lista de llamadas (por ejemplo, el tiempo de conmutación de voz de frecuencia) miden, mantenga el mouse sobre la etiqueta de la métrica; a continuación, aparecerá una información sobre herramientas que proporciona una breve descripción de la métrica.</span><span class="sxs-lookup"><span data-stu-id="66cdd-128">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="66cdd-129">Filtros</span><span class="sxs-lookup"><span data-stu-id="66cdd-129">Filters</span></span>

<span data-ttu-id="66cdd-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="66cdd-130">None.</span></span> <span data-ttu-id="66cdd-131">No se puede filtrar el informe de lista de llamadas.</span><span class="sxs-lookup"><span data-stu-id="66cdd-131">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="66cdd-132">Métricas</span><span class="sxs-lookup"><span data-stu-id="66cdd-132">Metrics</span></span>

<span data-ttu-id="66cdd-133">En la siguiente tabla se muestra la información proporcionada en el informe de lista de llamadas para cada llamada.</span><span class="sxs-lookup"><span data-stu-id="66cdd-133">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="66cdd-134">Métricas del informe de lista de llamadas</span><span class="sxs-lookup"><span data-stu-id="66cdd-134">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66cdd-135">Nombre</span><span class="sxs-lookup"><span data-stu-id="66cdd-135">Name</span></span></th>
<th><span data-ttu-id="66cdd-136">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="66cdd-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="66cdd-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="66cdd-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66cdd-138"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-138"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-139">No</span><span class="sxs-lookup"><span data-stu-id="66cdd-139">No</span></span></p></td>
<td><p><span data-ttu-id="66cdd-140">Al hacer clic en este elemento, el informe muestra información adicional sobre la llamada.</span><span class="sxs-lookup"><span data-stu-id="66cdd-140">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66cdd-141"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-141"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-142">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-142">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-143">Dirección SIP de la persona que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="66cdd-143">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66cdd-144"><strong>Destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-144"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-145">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-146">Dirección SIP de la persona a la que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="66cdd-146">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66cdd-147"><strong>Hora de inicio</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-147"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-148">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-148">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-149">Fecha y hora en que se inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="66cdd-149">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66cdd-150"><strong>Hora de finalización</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-150"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-151">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-151">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-152">Fecha y hora en que finalizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="66cdd-152">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66cdd-153"><strong>Agente de usuario de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-153"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-154">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-154">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-155">Software usado por el extremo de la persona que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="66cdd-155">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66cdd-156"><strong>Agente de usuario de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-156"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-157">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-157">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-158">Software usado por el extremo de la persona a la que se llamó.</span><span class="sxs-lookup"><span data-stu-id="66cdd-158">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66cdd-159"><strong>Recorrido de ida y vuelta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-159"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-160">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-160">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-p104">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="66cdd-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="66cdd-p105">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="66cdd-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66cdd-165"><strong>Degradación (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-165"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-166">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-166">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-167">Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="66cdd-167">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="66cdd-168">Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0.</span><span class="sxs-lookup"><span data-stu-id="66cdd-168">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="66cdd-169">Un valor de 0,5 o menos constituye una degradación aceptable.</span><span class="sxs-lookup"><span data-stu-id="66cdd-169">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="66cdd-170">Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5.</span><span class="sxs-lookup"><span data-stu-id="66cdd-170">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="66cdd-171">En Lync Server, Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios calificarían una llamada.</span><span class="sxs-lookup"><span data-stu-id="66cdd-171">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="66cdd-p107">Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="66cdd-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66cdd-174"><strong>Pérdida de paquetes</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-174"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-175">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-p108">Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="66cdd-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66cdd-179"><strong>JIT</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-179"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-180">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-181">Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="66cdd-181">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="66cdd-182">(La vibración es una medida de la &quot; irregularidad &quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="66cdd-182">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66cdd-183"><strong>Tasa de recuperación de muestras ocultas</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-183"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-184">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-p110">Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="66cdd-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66cdd-187"><strong>Tasa de recuperación de muestras extendidas</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-187"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-188">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-188">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-p111">Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="66cdd-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66cdd-191"><strong>Tasa de recuperación de muestras comprimidas</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-191"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-192">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-p112">Tasa media de muestras de audio comprimidas respecto al número total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="66cdd-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66cdd-195"><strong>Conectividad</strong></span><span class="sxs-lookup"><span data-stu-id="66cdd-195"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="66cdd-196">Sí</span><span class="sxs-lookup"><span data-stu-id="66cdd-196">Yes</span></span></p></td>
<td><p><span data-ttu-id="66cdd-197">Tipo de vínculo de comunicación inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="66cdd-197">Type of wireless communication link.</span></span> <span data-ttu-id="66cdd-198">Normalmente, es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="66cdd-198">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="66cdd-199">Emitir</span><span class="sxs-lookup"><span data-stu-id="66cdd-199">Relay</span></span></p></li>
<li><p><span data-ttu-id="66cdd-200">Dirección</span><span class="sxs-lookup"><span data-stu-id="66cdd-200">Direct</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

