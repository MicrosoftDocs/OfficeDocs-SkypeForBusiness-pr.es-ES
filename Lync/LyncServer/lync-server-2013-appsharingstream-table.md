---
title: 'Lync Server 2013: tabla AppSharingStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f23e214ffcffad8613d413924a53ffe571883d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="f4c74-102">Tabla AppSharingStream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4c74-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4c74-103">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="f4c74-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="f4c74-104">La tabla AppSharingStream contiene métricas de experiencia de calidad para las secuencias de red que se usan para compartir aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f4c74-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="f4c74-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4c74-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4c74-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f4c74-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f4c74-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f4c74-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-111">Fechas</span><span class="sxs-lookup"><span data-stu-id="f4c74-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="f4c74-112">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="f4c74-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4c74-113">Fecha y hora en que comenzó la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4c74-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-115">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-115">int</span></span></p></td>
<td><p><span data-ttu-id="f4c74-116">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="f4c74-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4c74-117">Identificador secuencial que se usa para diferenciar las sesiones que comenzaron en la misma fecha y al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f4c74-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f4c74-120">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="f4c74-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f4c74-121">Representa el tipo de línea de vídeo que se usa en la llamada.</span><span class="sxs-lookup"><span data-stu-id="f4c74-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="f4c74-122">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="f4c74-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f4c74-123">0: audio</span><span class="sxs-lookup"><span data-stu-id="f4c74-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="f4c74-124">1: vídeo</span><span class="sxs-lookup"><span data-stu-id="f4c74-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="f4c74-125">2-video panorámico</span><span class="sxs-lookup"><span data-stu-id="f4c74-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="f4c74-126">3: uso compartido de aplicaciones y escritorio</span><span class="sxs-lookup"><span data-stu-id="f4c74-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-128">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-128">int</span></span></p></td>
<td><p><span data-ttu-id="f4c74-129">Primary</span><span class="sxs-lookup"><span data-stu-id="f4c74-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="f4c74-130">Identificador único de la secuencia de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f4c74-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-132">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-133">Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="f4c74-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="f4c74-134">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="f4c74-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-136">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-137">Vibración máxima detectada entre las llegadas al paquete RTP.</span><span class="sxs-lookup"><span data-stu-id="f4c74-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="f4c74-138">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="f4c74-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-140">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-p105">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="f4c74-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="f4c74-p106">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="f4c74-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-146">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-147">Cantidad máxima de (en milisegundos) necesaria para que un paquete de protocolo de transporte en tiempo real viaje a otro extremo y después de nuevo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="f4c74-148">Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="f4c74-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="f4c74-p108">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="f4c74-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-152">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-p109">Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="f4c74-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-157">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-158">Tasa máxima de pérdida de paquetes del Protocolo de transporte en tiempo real (RTP).</span><span class="sxs-lookup"><span data-stu-id="f4c74-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="f4c74-159">(La pérdida de paquetes se produce cuando los paquetes RTP, un protocolo usado para transmitir audio y vídeo a través de Internet, no pudo alcanzar su destino). Las tarifas de pérdida elevada suelen ser causadas por la congestión; falta de ancho de banda; disgestión o interferencias inalámbricas; o un servidor multimedia sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="f4c74-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="f4c74-160">Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="f4c74-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-162">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-163">Número de paquetes enviados.</span><span class="sxs-lookup"><span data-stu-id="f4c74-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-164"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-165">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-166">Ancho de banda de unidireccional Estimado disponible al final de la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4c74-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="f4c74-167">Se notifica en bits por segundo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-169">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-170">Descripción de la carga de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f4c74-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-172">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-173">Cantidad total de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="f4c74-173">Total amount of one-way latency.</span></span> <span data-ttu-id="f4c74-174">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-176">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-177">Cantidad promedio de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="f4c74-177">Average amount of one-way latency.</span></span> <span data-ttu-id="f4c74-178">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-180">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-181">Cantidad máxima de latencia unidireccional.</span><span class="sxs-lookup"><span data-stu-id="f4c74-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="f4c74-182">Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-184">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-185">Total de repeticiones de ráfagas unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="f4c74-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="f4c74-186">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="f4c74-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f4c74-187">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-189">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-190">Densidad de ráfaga unidireccional total.</span><span class="sxs-lookup"><span data-stu-id="f4c74-190">Total one-way burst density.</span></span> <span data-ttu-id="f4c74-191">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="f4c74-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f4c74-192">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-194">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-195">Total de duración de ráfaga unidireccional.</span><span class="sxs-lookup"><span data-stu-id="f4c74-195">Total one-way burst duration.</span></span> <span data-ttu-id="f4c74-196">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="f4c74-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f4c74-197">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-199">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-200">Total de repeticiones de intervalos unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="f4c74-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="f4c74-201">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="f4c74-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f4c74-202">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-204">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-205">Densidad de brechas en un camino total.</span><span class="sxs-lookup"><span data-stu-id="f4c74-205">Total one-way gap density.</span></span> <span data-ttu-id="f4c74-206">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="f4c74-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f4c74-207">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-209">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-210">Duración del intervalo unidireccional total.</span><span class="sxs-lookup"><span data-stu-id="f4c74-210">Total one-way gap duration.</span></span> <span data-ttu-id="f4c74-211">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas.</span><span class="sxs-lookup"><span data-stu-id="f4c74-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f4c74-212">Esta medida mide el flujo de datos entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="f4c74-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-215">Función de aplicación (persona que comparte o visor) y tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="f4c74-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-217">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-218">Tiempo total de procesamiento para los mosaicos del Protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="f4c74-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="f4c74-219">Un total más alto iguala a un retraso más largo en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="f4c74-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-221">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-222">Tiempo promedio de procesamiento para los mosaicos del Protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="f4c74-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="f4c74-223">Un total más alto iguala a un retraso más largo en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="f4c74-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-225">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-226">Tiempo máximo de procesamiento para los mosaicos del Protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="f4c74-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="f4c74-227">Un total más alto iguala a un retraso más largo en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="f4c74-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-229">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-230">Repeticiones de ráfagas en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="f4c74-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="f4c74-231">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="f4c74-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-233">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-234">Densidad de ráfaga en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="f4c74-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="f4c74-235">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="f4c74-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-237">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-238">Duración de ráfagas en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="f4c74-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="f4c74-239">Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</span><span class="sxs-lookup"><span data-stu-id="f4c74-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-241">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-242">Repeticiones de huecos en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="f4c74-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-244">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-245">Densidad de brechas en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="f4c74-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="f4c74-246">La densidad de huecos bajos corresponde a una mejor experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="f4c74-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-248">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-249">Duración del hueco en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="f4c74-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="f4c74-250">Las duraciones cortas equivalen a una mejor experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="f4c74-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-252">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-253">Tasa total de mosaicos capturados (en mosaicos por segundo).</span><span class="sxs-lookup"><span data-stu-id="f4c74-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-255">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-256">Velocidad promedio de los mosaicos capturados (en mosaicos por segundo).</span><span class="sxs-lookup"><span data-stu-id="f4c74-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-258">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-259">Frecuencia máxima de mosaicos capturados (en mosaicos por segundo).</span><span class="sxs-lookup"><span data-stu-id="f4c74-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-261">en t</span><span class="sxs-lookup"><span data-stu-id="f4c74-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-262">Repeticiones de ráfaga en la tasa de mosaicos capturados (en mosaicos por segundo).</span><span class="sxs-lookup"><span data-stu-id="f4c74-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-264">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-265">Densidad de ráfaga en la tasa de mosaicos capturados (en mosaicos por segundo).</span><span class="sxs-lookup"><span data-stu-id="f4c74-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-267">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-268">Duración de ráfaga en la tasa de mosaicos capturados (en mosaicos por segundo).</span><span class="sxs-lookup"><span data-stu-id="f4c74-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-270">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-271">Repeticiones de huecos en la tasa de mosaicos capturados (en mosaicos por segundo).</span><span class="sxs-lookup"><span data-stu-id="f4c74-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-273">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-274">Densidad de huecos en la tasa de mosaicos capturados (en mosaicos por segundo).</span><span class="sxs-lookup"><span data-stu-id="f4c74-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-276">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-277">Duración del hueco en la tasa de mosaicos capturados (en mosaicos por segundo).</span><span class="sxs-lookup"><span data-stu-id="f4c74-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-279">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-280">Porcentaje total del contenido que no se ha podido alcanzar con el visor, pero que se ha descartado y ha sido reemplazado por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-282">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-283">Porcentaje medio del contenido que no se ha encontrado en el visor pero que se ha descartado y se ha reemplazado por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-285">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-286">Porcentaje máximo del contenido que no se ha podido alcanzar con el visor, pero que se descartó y se sobrescribió por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-288">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-289">Repeticiones de ráfagas para el contenido que no se ha podido alcanzar con el visor, pero que se han descartado y reemplazado por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-291">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-292">Densidad de ráfaga para el contenido que no se ha podido alcanzar con el visor, pero se ha descartado y ha sido reemplazado por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-294">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-295">Duración de ráfaga para el contenido que no se ha podido alcanzar con el visor, pero se ha descartado y ha sido reemplazado por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-297">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-298">Las repeticiones de huecos para el contenido que no se ha podido alcanzar con el visor pero se han descartado y reemplazado por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-300">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-301">Densidad de brechas para el contenido que no se ha podido alcanzar con el visor, pero que se descartó y sobrescribe por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-303">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-304">El intervalo de tiempo para el contenido que no se ha podido alcanzar con el visor, se ha descartado y ha sido reemplazado por contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="f4c74-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-306">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-307">Número total de fotogramas descartados de la fuente de gráficos.</span><span class="sxs-lookup"><span data-stu-id="f4c74-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-309">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-310">Número promedio de fotogramas descartados del origen de gráficos.</span><span class="sxs-lookup"><span data-stu-id="f4c74-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-312">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-313">Número máximo de fotogramas descartados del origen de gráficos.</span><span class="sxs-lookup"><span data-stu-id="f4c74-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-315">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-316">Repeticiones de ráfagas en los fotogramas descartados de la fuente de gráficos.</span><span class="sxs-lookup"><span data-stu-id="f4c74-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-318">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-319">Densidad de ráfaga en las tramas descartadas de la fuente de gráficos.</span><span class="sxs-lookup"><span data-stu-id="f4c74-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-321">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-322">Duración de ráfaga en las tramas descartadas del origen de gráficos.</span><span class="sxs-lookup"><span data-stu-id="f4c74-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-324">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-325">Repeticiones de huecos en los fotogramas descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="f4c74-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-327">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-328">Densidad de huecos en los fotogramas descartados del origen de gráficos.</span><span class="sxs-lookup"><span data-stu-id="f4c74-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-330">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-331">Duración del hueco en los fotogramas descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="f4c74-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-333">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-334">Total de la velocidad de fotogramas entrantes recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-336">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-337">Promedio de velocidad de fotogramas entrante recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-339">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-340">Cantidad máxima de mosaico entrante recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-342">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-343">Repeticiones de ráfaga en la tasa de mosaico entrante recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-345">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-346">Densidad de ráfaga en la tasa de icono entrante recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-348">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-349">Duración de ráfaga en la tasa de mosaico entrante recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-351">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-352">Las repeticiones de huecos de la velocidad de los mosaicos entrantes recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-354">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-355">Densidad de hueco en la tasa de mosaico entrante recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-357">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-358">Duración del intervalo en la tasa de mosaico entrante recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-360">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-361">Total de la velocidad de fotogramas entrantes recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-363">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-364">Promedio de velocidad de fotogramas entrante recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-366">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-367">Cantidad máxima de fotogramas entrantes recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-369">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-370">Repeticiones de ráfagas en la velocidad de fotogramas entrantes recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-372">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-373">Densidad de ráfaga en la velocidad de fotogramas entrantes recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-375">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-376">La duración de la ráfaga en la velocidad de fotogramas entrante recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-378">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-379">Las repeticiones de huecos de la velocidad de fotogramas entrantes recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-381">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-382">Densidad de huecos en la velocidad de fotogramas entrante recibida por el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-384">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-385">Duración del hueco en la velocidad de fotogramas entrante que recibió el visor.</span><span class="sxs-lookup"><span data-stu-id="f4c74-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-387">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-388">Intervalo total de los mosaicos salientes del remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-390">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-391">Promedio de la velocidad de los iconos salientes del remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-393">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-394">Velocidad máxima de los iconos salientes del remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-396">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-397">Repeticiones de ráfaga en la tasa del mosaico saliente para el remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-399">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-400">Densidad de ráfaga en la tasa del mosaico saliente para el remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-402">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-403">Duración de ráfaga en la tasa del mosaico saliente para el remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-405">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-406">Repeticiones de huecos en la tasa de mosaico saliente para el remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-408">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-409">Densidad de hueco en la tasa de mosaico saliente para el remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-411">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-412">Duración del hueco en la tasa del mosaico saliente para el remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-414">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-415">Total de la velocidad de los fotogramas salientes del remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-417">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-418">promedio de velocidad de fotograma saliente para el remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-420">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-421">Velocidad máxima de los fotogramas salientes del remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-423">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-424">Repeticiones de ráfagas en la velocidad de fotogramas salientes del remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-426">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-427">Densidad de ráfagas en la velocidad de fotogramas salientes del remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-429">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-430">Duración de ráfaga en la velocidad de fotogramas salientes del remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-432">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-433">Repeticiones de huecos en la velocidad de fotogramas salientes del remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-435">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-436">Densidad de huecos en la velocidad de fotogramas salientes del remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-438">float</span><span class="sxs-lookup"><span data-stu-id="f4c74-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-439">Duración del hueco en la velocidad de fotogramas salientes del remitente.</span><span class="sxs-lookup"><span data-stu-id="f4c74-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-441">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-442">Promedio de altura de la resolución de video, en píxeles.</span><span class="sxs-lookup"><span data-stu-id="f4c74-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-444">int</span><span class="sxs-lookup"><span data-stu-id="f4c74-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-445">Promedio de ancho de resolución de video, en píxeles.</span><span class="sxs-lookup"><span data-stu-id="f4c74-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-446"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-447">bit</span><span class="sxs-lookup"><span data-stu-id="f4c74-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-448">Promedio de velocidad de fotogramas (en fotogramas por segundo) para transfronterizas entrantes.</span><span class="sxs-lookup"><span data-stu-id="f4c74-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4c74-449"><strong>Saliente</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-450">bit</span><span class="sxs-lookup"><span data-stu-id="f4c74-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-451">Promedio de velocidad de fotogramas (en fotogramas por segundo) para transfronterizas salientes.</span><span class="sxs-lookup"><span data-stu-id="f4c74-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4c74-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f4c74-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f4c74-453">bit</span><span class="sxs-lookup"><span data-stu-id="f4c74-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f4c74-454">1 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="f4c74-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="f4c74-455">0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="f4c74-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

