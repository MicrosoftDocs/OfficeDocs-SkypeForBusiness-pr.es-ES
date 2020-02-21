---
title: 'Lync Server 2013: informe de lista de llamadas'
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
ms.openlocfilehash: 06486ddc8d84c165422e7f4ffea9bb62be5dd683
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="83cd3-102">Informe de lista de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83cd3-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83cd3-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="83cd3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="83cd3-104">El informe de lista de llamadas proporciona métricas de la calidad de la experiencia (QoE) para las llamadas individuales realizadas y recibidas en su organización.</span><span class="sxs-lookup"><span data-stu-id="83cd3-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="83cd3-105">Tenga en cuenta que las métricas reales que se notifiquen dependerán de cómo obtenga acceso al informe de lista de llamadas.</span><span class="sxs-lookup"><span data-stu-id="83cd3-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="83cd3-106">Por ejemplo, si abre el informe desde el [Informe de dispositivos en Lync Server 2013](lync-server-2013-device-report.md), verá métricas como las siguientes, métricas que también se notifican en el informe de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="83cd3-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="83cd3-107">Micrófono del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="83cd3-107">Caller's microphone</span></span>

  - <span data-ttu-id="83cd3-108">Altavoz del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="83cd3-108">Caller's speaker</span></span>

  - <span data-ttu-id="83cd3-109">Micrófono del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="83cd3-109">Callee's microphone</span></span>

  - <span data-ttu-id="83cd3-110">Altavoz del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="83cd3-110">Callee's speaker</span></span>

  - <span data-ttu-id="83cd3-111">Relación de tiempo de conmutación de voz</span><span class="sxs-lookup"><span data-stu-id="83cd3-111">Ratio of voice switch time</span></span>

<span data-ttu-id="83cd3-112">Sin embargo, si abre el informe de lista de llamadas desde el [Informe de ubicación en Lync Server 2013](lync-server-2013-location-report.md), no verá ninguna de estas métricas; en su lugar, verá métricas como estas:</span><span class="sxs-lookup"><span data-stu-id="83cd3-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="83cd3-113">Recorrido de ida y vuelta (ms)</span><span class="sxs-lookup"><span data-stu-id="83cd3-113">Round trip (ms)</span></span>

  - <span data-ttu-id="83cd3-114">Degradación (MOS)</span><span class="sxs-lookup"><span data-stu-id="83cd3-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="83cd3-115">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="83cd3-115">Packet loss</span></span>

  - <span data-ttu-id="83cd3-116">Vibración (ms)</span><span class="sxs-lookup"><span data-stu-id="83cd3-116">Jitter (ms)</span></span>

<span data-ttu-id="83cd3-117">Esas son las métricas que se indican en el informe de ubicación.</span><span class="sxs-lookup"><span data-stu-id="83cd3-117">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="83cd3-118">Sin embargo, en el informe de lista de llamadas, siempre puede hacer clic en la métrica de detalles para proporcionar la información completa de QoE para cada llamada.</span><span class="sxs-lookup"><span data-stu-id="83cd3-118">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="83cd3-119">Acceso al informe de lista de llamadas</span><span class="sxs-lookup"><span data-stu-id="83cd3-119">Accessing the Call List Report</span></span>

<span data-ttu-id="83cd3-120">Se puede tener acceso al informe de lista de llamadas desde cualquiera de los siguientes informes:</span><span class="sxs-lookup"><span data-stu-id="83cd3-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="83cd3-121">El [Informe de ubicación en Lync Server 2013](lync-server-2013-location-report.md) (haciendo clic en el volumen de llamadas o en la métrica de porcentaje de llamadas deficientes)</span><span class="sxs-lookup"><span data-stu-id="83cd3-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="83cd3-122">El [Informe de dispositivos en Lync Server 2013](lync-server-2013-device-report.md) (haciendo clic en el volumen de llamadas o en la métrica de porcentaje de llamadas deficientes)</span><span class="sxs-lookup"><span data-stu-id="83cd3-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="83cd3-123">El [Informe de Resumen de calidad de medios en Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (haciendo clic en el volumen de llamadas o en la métrica de porcentaje de llamadas deficientes)</span><span class="sxs-lookup"><span data-stu-id="83cd3-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="83cd3-124">El [Informe de rendimiento del servidor en Lync Server 2013](lync-server-2013-server-performance-report.md) (haciendo clic en el volumen de llamadas o en la métrica de porcentaje de llamadas deficientes)</span><span class="sxs-lookup"><span data-stu-id="83cd3-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="83cd3-125">Desde el informe de lista de llamadas puede tener acceso al [Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md) haciendo clic en la métrica detalles.</span><span class="sxs-lookup"><span data-stu-id="83cd3-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="83cd3-126">Aprovechar al máximo el informe de lista de llamadas</span><span class="sxs-lookup"><span data-stu-id="83cd3-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="83cd3-127">Si no recuerda lo que algunas de las métricas del informe de lista de llamadas (por ejemplo, el tiempo de conmutación de voz de frecuencia) miden, mantenga el mouse sobre la etiqueta de la métrica; a continuación, aparecerá una información sobre herramientas que proporciona una breve descripción de la métrica.</span><span class="sxs-lookup"><span data-stu-id="83cd3-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="83cd3-128">Filtros</span><span class="sxs-lookup"><span data-stu-id="83cd3-128">Filters</span></span>

<span data-ttu-id="83cd3-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="83cd3-129">None.</span></span> <span data-ttu-id="83cd3-130">No se puede filtrar el informe de lista de llamadas.</span><span class="sxs-lookup"><span data-stu-id="83cd3-130">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="83cd3-131">Métricas</span><span class="sxs-lookup"><span data-stu-id="83cd3-131">Metrics</span></span>

<span data-ttu-id="83cd3-132">En la siguiente tabla se muestra la información proporcionada en el informe de lista de llamadas para cada llamada.</span><span class="sxs-lookup"><span data-stu-id="83cd3-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="83cd3-133">Métricas del informe de lista de llamadas</span><span class="sxs-lookup"><span data-stu-id="83cd3-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83cd3-134">Nombre</span><span class="sxs-lookup"><span data-stu-id="83cd3-134">Name</span></span></th>
<th><span data-ttu-id="83cd3-135">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="83cd3-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="83cd3-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="83cd3-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83cd3-137"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-138">No</span><span class="sxs-lookup"><span data-stu-id="83cd3-138">No</span></span></p></td>
<td><p><span data-ttu-id="83cd3-139">Al hacer clic en este elemento, el informe muestra información adicional sobre la llamada.</span><span class="sxs-lookup"><span data-stu-id="83cd3-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83cd3-140"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-141">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-142">Dirección SIP de la persona que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="83cd3-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83cd3-143"><strong>Destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-144">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-145">Dirección SIP de la persona a la que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="83cd3-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83cd3-146"><strong>Hora de inicio</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-147">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-148">Fecha y hora en que se inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="83cd3-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83cd3-149"><strong>Hora de finalización</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-150">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-151">Fecha y hora en que finalizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="83cd3-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83cd3-152"><strong>Agente de usuario de autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-153">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-154">Software usado por el extremo de la persona que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="83cd3-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83cd3-155"><strong>Agente de usuario de destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-156">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-157">Software usado por el extremo de la persona a la que se llamó.</span><span class="sxs-lookup"><span data-stu-id="83cd3-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83cd3-158"><strong>Recorrido de ida y vuelta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-159">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-p104">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="83cd3-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="83cd3-p105">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="83cd3-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83cd3-164"><strong>Degradación (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-165">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-166">Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="83cd3-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="83cd3-167">Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0.</span><span class="sxs-lookup"><span data-stu-id="83cd3-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="83cd3-168">Un valor de 0,5 o menos constituye una degradación aceptable.</span><span class="sxs-lookup"><span data-stu-id="83cd3-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="83cd3-169">Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5.</span><span class="sxs-lookup"><span data-stu-id="83cd3-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="83cd3-170">En Lync Server, Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios calificarían una llamada.</span><span class="sxs-lookup"><span data-stu-id="83cd3-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="83cd3-p107">Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="83cd3-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83cd3-173"><strong>Pérdida de paquetes</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-174">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-p108">Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="83cd3-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83cd3-178"><strong>JIT</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-179">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-180">Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="83cd3-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="83cd3-181">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="83cd3-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83cd3-182"><strong>Tasa de recuperación de muestras ocultas</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-183">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-p110">Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="83cd3-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83cd3-186"><strong>Tasa de recuperación de muestras extendidas</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-187">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-p111">Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="83cd3-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83cd3-190"><strong>Tasa de recuperación de muestras comprimidas</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-191">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-p112">Tasa media de muestras de audio comprimidas respecto al número total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="83cd3-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83cd3-194"><strong>Conectividad</strong></span><span class="sxs-lookup"><span data-stu-id="83cd3-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="83cd3-195">Sí</span><span class="sxs-lookup"><span data-stu-id="83cd3-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="83cd3-196">Tipo de vínculo de comunicación inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="83cd3-196">Type of wireless communication link.</span></span> <span data-ttu-id="83cd3-197">Normalmente, es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="83cd3-197">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="83cd3-198">Emitir</span><span class="sxs-lookup"><span data-stu-id="83cd3-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="83cd3-199">Dirección</span><span class="sxs-lookup"><span data-stu-id="83cd3-199">Direct</span></span></p></li>
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

