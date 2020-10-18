---
title: 'Lync Server 2013: tabla AppSharingStream'
description: 'Lync Server 2013: tabla AppSharingStream.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b530af5b489e090e5d0d00fbb01b2b950bafbe5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574726"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="5d398-103">Tabla AppSharingStream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d398-103">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d398-104">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="5d398-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="5d398-105">La tabla AppSharingStream contiene métricas de calidad de la experiencia de los flujos de red utilizados para el uso compartido de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5d398-105">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="5d398-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d398-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d398-107"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5d398-108"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5d398-109"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5d398-110"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d398-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-112">dateTime</span><span class="sxs-lookup"><span data-stu-id="5d398-112">dateTime</span></span></p></td>
<td><p><span data-ttu-id="5d398-113">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="5d398-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d398-114">Fecha y hora en que se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="5d398-114">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-116">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-116">int</span></span></p></td>
<td><p><span data-ttu-id="5d398-117">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="5d398-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d398-118">Identificador secuencial usado para distinguir las sesiones que se iniciaron en la misma fecha de las que se iniciaron a la misma hora.</span><span class="sxs-lookup"><span data-stu-id="5d398-118">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="5d398-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5d398-121">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="5d398-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5d398-p102">Representa el tipo de línea de vídeo usada en la llamada. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="5d398-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5d398-124">0: audio</span><span class="sxs-lookup"><span data-stu-id="5d398-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="5d398-125">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="5d398-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="5d398-126">2 – Vídeo panorámico</span><span class="sxs-lookup"><span data-stu-id="5d398-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="5d398-127">3 – uso compartido de aplicaciones y escritorios</span><span class="sxs-lookup"><span data-stu-id="5d398-127">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-128"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-128"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-129">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-129">int</span></span></p></td>
<td><p><span data-ttu-id="5d398-130">Principal</span><span class="sxs-lookup"><span data-stu-id="5d398-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="5d398-131">Identificador único del flujo de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5d398-131">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-133">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-134">Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="5d398-134">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="5d398-135">(La vibración es una medida de la &quot; irregularidad &quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="5d398-135">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-136"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-136"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-137">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-138">Valor máximo de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="5d398-138">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="5d398-139">(La vibración es una medida de la &quot; irregularidad &quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="5d398-139">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-140"><strong>Vuelta</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-140"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-141">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p105">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="5d398-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="5d398-p106">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="5d398-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-146"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-146"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-147">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-147">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p107">Tiempo máximo (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="5d398-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="5d398-p108">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="5d398-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-152"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-152"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-153">float</span><span class="sxs-lookup"><span data-stu-id="5d398-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p109">Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="5d398-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-157"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-157"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-158">float</span><span class="sxs-lookup"><span data-stu-id="5d398-158">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p110">Tasa máxima de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="5d398-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-162"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-162"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-163">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-163">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-164">Número de paquetes enviados.</span><span class="sxs-lookup"><span data-stu-id="5d398-164">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-165"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-165"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-166">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-166">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p111">Ancho de banda unilateral estimado disponible al final de la sesión. Se muestra en bits por segundo.</span><span class="sxs-lookup"><span data-stu-id="5d398-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-169"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-169"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-170">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-170">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-171">Descripción de la aplicación que comparte la carga.</span><span class="sxs-lookup"><span data-stu-id="5d398-171">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-172"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-172"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-173">float</span><span class="sxs-lookup"><span data-stu-id="5d398-173">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p112">Cantidad total de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5d398-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-176"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-176"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-177">float</span><span class="sxs-lookup"><span data-stu-id="5d398-177">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p113">Cantidad media de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5d398-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-180"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-180"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-181">float</span><span class="sxs-lookup"><span data-stu-id="5d398-181">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p114">Cantidad máxima de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5d398-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-184"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-184"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-185">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p115">Cantidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5d398-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-189"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-189"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-190">float</span><span class="sxs-lookup"><span data-stu-id="5d398-190">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p116">Densidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5d398-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-194"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-194"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-195">float</span><span class="sxs-lookup"><span data-stu-id="5d398-195">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p117">Duración total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5d398-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-199"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-199"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-200">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-200">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p118">Cantidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5d398-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-204"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-204"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-205">float</span><span class="sxs-lookup"><span data-stu-id="5d398-205">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p119">Densidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5d398-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-209"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-209"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-210">float</span><span class="sxs-lookup"><span data-stu-id="5d398-210">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p120">Duración total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5d398-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-214"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-214"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-215">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="5d398-215">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-216">Rol de aplicación (aplicación que comparte o visualiza) y tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="5d398-216">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-217"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-217"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-218">float</span><span class="sxs-lookup"><span data-stu-id="5d398-218">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p121">Tiempo de procesamiento total de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="5d398-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-221"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-221"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-222">float</span><span class="sxs-lookup"><span data-stu-id="5d398-222">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p122">Tiempo de procesamiento de promedio de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="5d398-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-225"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-225"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-226">float</span><span class="sxs-lookup"><span data-stu-id="5d398-226">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p123">Tiempo de procesamiento máximo de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="5d398-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-230">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-230">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p124">Repeticiones de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="5d398-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-234">float</span><span class="sxs-lookup"><span data-stu-id="5d398-234">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p125">Densidad de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="5d398-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-238">float</span><span class="sxs-lookup"><span data-stu-id="5d398-238">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p126">Duración de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="5d398-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-242">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-243">Repeticiones de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="5d398-243">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-245">float</span><span class="sxs-lookup"><span data-stu-id="5d398-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p127">Densidad de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una densidad de intervalos baja indica una experiencia de visualización de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="5d398-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-249">float</span><span class="sxs-lookup"><span data-stu-id="5d398-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-p128">Duración de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una duración de intervalos corta indica una experiencia de visualización de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="5d398-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-252"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-252"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-253">float</span><span class="sxs-lookup"><span data-stu-id="5d398-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-254">Tasa total de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5d398-254">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-255"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-255"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-256">float</span><span class="sxs-lookup"><span data-stu-id="5d398-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-257">Tasa media de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5d398-257">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-258"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-258"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-259">float</span><span class="sxs-lookup"><span data-stu-id="5d398-259">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-260">Tasa máxima de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5d398-260">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-261"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-261"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-262">int</span><span class="sxs-lookup"><span data-stu-id="5d398-262">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-263">Repeticiones de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5d398-263">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-264"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-264"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-265">float</span><span class="sxs-lookup"><span data-stu-id="5d398-265">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-266">Densidad de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5d398-266">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-267"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-267"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-268">float</span><span class="sxs-lookup"><span data-stu-id="5d398-268">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-269">Duración de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5d398-269">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-270"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-270"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-271">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-271">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-272">Repeticiones de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5d398-272">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-273"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-273"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-274">float</span><span class="sxs-lookup"><span data-stu-id="5d398-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-275">Densidad de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5d398-275">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-276"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-276"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-277">float</span><span class="sxs-lookup"><span data-stu-id="5d398-277">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-278">Duración de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5d398-278">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-279"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-279"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-280">float</span><span class="sxs-lookup"><span data-stu-id="5d398-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-281">Porcentaje total de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d398-281">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-282"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-282"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-283">float</span><span class="sxs-lookup"><span data-stu-id="5d398-283">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-284">Porcentaje medio de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d398-284">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-285"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-285"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-286">float</span><span class="sxs-lookup"><span data-stu-id="5d398-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-287">Porcentaje máximo de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d398-287">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-289">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-289">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-290">Repeticiones de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d398-290">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-291"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-291"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-292">float</span><span class="sxs-lookup"><span data-stu-id="5d398-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-293">Densidad de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d398-293">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-294"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-294"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-295">float</span><span class="sxs-lookup"><span data-stu-id="5d398-295">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-296">Duración de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d398-296">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-297"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-297"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-298">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-298">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-299">Repeticiones de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d398-299">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-300"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-300"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-301">float</span><span class="sxs-lookup"><span data-stu-id="5d398-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-302">Densidad de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d398-302">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-303"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-303"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-304">float</span><span class="sxs-lookup"><span data-stu-id="5d398-304">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-305">Duración de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d398-305">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-306"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-306"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-307">float</span><span class="sxs-lookup"><span data-stu-id="5d398-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-308">Número total de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5d398-308">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-309"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-309"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-310">float</span><span class="sxs-lookup"><span data-stu-id="5d398-310">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-311">Número medio de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5d398-311">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-312"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-312"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-313">float</span><span class="sxs-lookup"><span data-stu-id="5d398-313">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-314">Número máximo de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5d398-314">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-316">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-317">Repeticiones de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5d398-317">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-318"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-318"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-319">float</span><span class="sxs-lookup"><span data-stu-id="5d398-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-320">Densidad de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5d398-320">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-321"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-321"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-322">float</span><span class="sxs-lookup"><span data-stu-id="5d398-322">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-323">Duración de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5d398-323">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-324"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-324"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-325">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-326">Intervalos de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5d398-326">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-327"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-327"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-328">float</span><span class="sxs-lookup"><span data-stu-id="5d398-328">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-329">Densidad de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5d398-329">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-330"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-330"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-331">float</span><span class="sxs-lookup"><span data-stu-id="5d398-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-332">Duración de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5d398-332">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-333"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-333"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-334">float</span><span class="sxs-lookup"><span data-stu-id="5d398-334">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-335">Tasa de tramas de entrada total recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-335">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-336"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-336"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-337">float</span><span class="sxs-lookup"><span data-stu-id="5d398-337">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-338">Tasa de tramas de entrada de promedio recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-338">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-339"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-339"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-340">float</span><span class="sxs-lookup"><span data-stu-id="5d398-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-341">Tasa de datos de entrada máxima recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-341">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-342"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-342"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-343">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-343">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-344">Repeticiones de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-344">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-345"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-345"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-346">float</span><span class="sxs-lookup"><span data-stu-id="5d398-346">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-347">Densidad de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-347">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-348"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-348"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-349">float</span><span class="sxs-lookup"><span data-stu-id="5d398-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-350">Duración de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-350">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-351"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-351"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-352">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-352">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-353">Repetición de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-353">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-354"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-354"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-355">float</span><span class="sxs-lookup"><span data-stu-id="5d398-355">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-356">Densidad de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-356">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-357"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-357"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-358">float</span><span class="sxs-lookup"><span data-stu-id="5d398-358">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-359">Duración de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-359">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-360"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-360"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-361">float</span><span class="sxs-lookup"><span data-stu-id="5d398-361">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-362">Tasa de tramas de entrada total recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-362">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-363"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-363"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-364">float</span><span class="sxs-lookup"><span data-stu-id="5d398-364">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-365">Tasa de tramas de entrada de promedio recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-365">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-366"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-366"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-367">float</span><span class="sxs-lookup"><span data-stu-id="5d398-367">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-368">Tasa de tramas de entrada máxima recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-368">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-369"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-369"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-370">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-371">Repeticiones de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-371">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-372"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-372"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-373">float</span><span class="sxs-lookup"><span data-stu-id="5d398-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-374">Densidad de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-374">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-375"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-375"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-376">float</span><span class="sxs-lookup"><span data-stu-id="5d398-376">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-377">Duración de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-377">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-378"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-378"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-379">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-379">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-380">Repeticiones de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-380">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-381"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-381"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-382">float</span><span class="sxs-lookup"><span data-stu-id="5d398-382">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-383">Densidad de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-383">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-384"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-384"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-385">float</span><span class="sxs-lookup"><span data-stu-id="5d398-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-386">Duración de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5d398-386">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-387"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-387"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-388">float</span><span class="sxs-lookup"><span data-stu-id="5d398-388">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-389">Tasa de datos de salida total para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-389">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-390"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-390"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-391">float</span><span class="sxs-lookup"><span data-stu-id="5d398-391">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-392">Tasa de datos de salida de promedio para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-392">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-393"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-393"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-394">float</span><span class="sxs-lookup"><span data-stu-id="5d398-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-395">Tasa de datos de salida máxima para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-395">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-396"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-396"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-397">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-397">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-398">Repeticiones de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-398">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-399"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-399"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-400">float</span><span class="sxs-lookup"><span data-stu-id="5d398-400">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-401">Densidad de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-401">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-402"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-402"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-403">float</span><span class="sxs-lookup"><span data-stu-id="5d398-403">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-404">Duración de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-404">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-405"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-405"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-406">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-406">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-407">Repeticiones de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-407">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-408"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-408"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-409">float</span><span class="sxs-lookup"><span data-stu-id="5d398-409">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-410">Densidad de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-410">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-411"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-411"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-412">float</span><span class="sxs-lookup"><span data-stu-id="5d398-412">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-413">Duración de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-413">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-414"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-414"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-415">float</span><span class="sxs-lookup"><span data-stu-id="5d398-415">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-416">Tasa de tramas de salida total para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-416">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-417"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-417"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-418">float</span><span class="sxs-lookup"><span data-stu-id="5d398-418">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-419">Tasa de tramas de salida de promedio para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-419">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-420"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-420"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-421">float</span><span class="sxs-lookup"><span data-stu-id="5d398-421">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-422">Tasa de tramas de salida máxima para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-422">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-424">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-424">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-425">Repeticiones de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-425">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-426"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-426"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-427">float</span><span class="sxs-lookup"><span data-stu-id="5d398-427">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-428">Densidad de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-428">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-429"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-429"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-430">float</span><span class="sxs-lookup"><span data-stu-id="5d398-430">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-431">Duración de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-431">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-432"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-432"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-433">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-433">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-434">Repeticiones de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-434">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-435"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-435"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-436">float</span><span class="sxs-lookup"><span data-stu-id="5d398-436">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-437">Densidad de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-437">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-438"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-438"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-439">float</span><span class="sxs-lookup"><span data-stu-id="5d398-439">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-440">Duración de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5d398-440">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-441"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-441"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-442">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-442">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-443">Promedio de altura de resolución de vídeo en píxeles.</span><span class="sxs-lookup"><span data-stu-id="5d398-443">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-444"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-444"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-445">entero</span><span class="sxs-lookup"><span data-stu-id="5d398-445">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-446">Promedio de anchura de resolución de vídeo en píxeles.</span><span class="sxs-lookup"><span data-stu-id="5d398-446">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-447"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-447"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-448">bit</span><span class="sxs-lookup"><span data-stu-id="5d398-448">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-449">Tasa de tramas de promedio (en tramas por segundo) para las transmisiones de entrada.</span><span class="sxs-lookup"><span data-stu-id="5d398-449">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d398-450"><strong>Saliente</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-450"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-451">bit</span><span class="sxs-lookup"><span data-stu-id="5d398-451">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-452">Tasa de tramas de promedio (en tramas por segundo) para las transmisiones de salida.</span><span class="sxs-lookup"><span data-stu-id="5d398-452">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d398-453"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="5d398-453"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="5d398-454">bit</span><span class="sxs-lookup"><span data-stu-id="5d398-454">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d398-455">1 significa que la dirección de la secuencia va desde el autor de la llamada hasta el destinatario.</span><span class="sxs-lookup"><span data-stu-id="5d398-455">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="5d398-456">0 indica que la dirección de la secuencia va del destinatario de la llamada al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5d398-456">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

