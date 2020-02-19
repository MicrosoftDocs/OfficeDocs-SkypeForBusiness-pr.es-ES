---
title: 'Lync Server 2013: tabla AppSharingStream'
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
ms.openlocfilehash: 4454b7fbcaffc1fc302d5c434666cfdfa93ada36
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="5558a-102">Tabla AppSharingStream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5558a-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5558a-103">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="5558a-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="5558a-104">La tabla AppSharingStream contiene métricas de calidad de la experiencia de los flujos de red utilizados para el uso compartido de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5558a-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="5558a-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5558a-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5558a-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5558a-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5558a-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5558a-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5558a-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="5558a-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="5558a-112">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="5558a-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5558a-113">Fecha y hora en que se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="5558a-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-115">int</span><span class="sxs-lookup"><span data-stu-id="5558a-115">int</span></span></p></td>
<td><p><span data-ttu-id="5558a-116">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="5558a-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5558a-117">Identificador secuencial usado para distinguir las sesiones que se iniciaron en la misma fecha de las que se iniciaron a la misma hora.</span><span class="sxs-lookup"><span data-stu-id="5558a-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="5558a-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5558a-120">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="5558a-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5558a-p102">Representa el tipo de línea de vídeo usada en la llamada. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="5558a-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5558a-123">0: audio</span><span class="sxs-lookup"><span data-stu-id="5558a-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="5558a-124">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="5558a-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="5558a-125">2 – Vídeo panorámico</span><span class="sxs-lookup"><span data-stu-id="5558a-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="5558a-126">3 – uso compartido de aplicaciones y escritorios</span><span class="sxs-lookup"><span data-stu-id="5558a-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-128">int</span><span class="sxs-lookup"><span data-stu-id="5558a-128">int</span></span></p></td>
<td><p><span data-ttu-id="5558a-129">Principal</span><span class="sxs-lookup"><span data-stu-id="5558a-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="5558a-130">Identificador único del flujo de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5558a-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-132">int</span><span class="sxs-lookup"><span data-stu-id="5558a-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-133">Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="5558a-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="5558a-134">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="5558a-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-136">int</span><span class="sxs-lookup"><span data-stu-id="5558a-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-137">Valor máximo de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="5558a-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="5558a-138">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="5558a-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-139"><strong>Vuelta</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-140">int</span><span class="sxs-lookup"><span data-stu-id="5558a-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p105">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="5558a-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="5558a-p106">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden producirse en el enrutamiento de llamadas internacionales, si la configuración del enrutamiento no es la correcta, o si se produce una sobrecarga en el servidor multimedia, y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="5558a-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-146">int</span><span class="sxs-lookup"><span data-stu-id="5558a-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p107">Tiempo máximo (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="5558a-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="5558a-p108">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="5558a-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-152">float</span><span class="sxs-lookup"><span data-stu-id="5558a-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p109">Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="5558a-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-157">float</span><span class="sxs-lookup"><span data-stu-id="5558a-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p110">Tasa máxima de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="5558a-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-162">int</span><span class="sxs-lookup"><span data-stu-id="5558a-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-163">Número de paquetes enviados.</span><span class="sxs-lookup"><span data-stu-id="5558a-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-164"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-165">int</span><span class="sxs-lookup"><span data-stu-id="5558a-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p111">Ancho de banda unilateral estimado disponible al final de la sesión. Se muestra en bits por segundo.</span><span class="sxs-lookup"><span data-stu-id="5558a-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-169">int</span><span class="sxs-lookup"><span data-stu-id="5558a-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-170">Descripción de la aplicación que comparte la carga.</span><span class="sxs-lookup"><span data-stu-id="5558a-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-172">float</span><span class="sxs-lookup"><span data-stu-id="5558a-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p112">Cantidad total de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5558a-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-176">float</span><span class="sxs-lookup"><span data-stu-id="5558a-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p113">Cantidad media de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5558a-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-180">float</span><span class="sxs-lookup"><span data-stu-id="5558a-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p114">Cantidad máxima de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5558a-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-184">int</span><span class="sxs-lookup"><span data-stu-id="5558a-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p115">Cantidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5558a-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-189">float</span><span class="sxs-lookup"><span data-stu-id="5558a-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p116">Densidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5558a-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-194">float</span><span class="sxs-lookup"><span data-stu-id="5558a-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p117">Duración total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5558a-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-199">int</span><span class="sxs-lookup"><span data-stu-id="5558a-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p118">Cantidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5558a-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-204">float</span><span class="sxs-lookup"><span data-stu-id="5558a-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p119">Densidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5558a-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-209">float</span><span class="sxs-lookup"><span data-stu-id="5558a-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p120">Duración total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="5558a-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="5558a-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-215">Rol de aplicación (aplicación que comparte o visualiza) y tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="5558a-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-217">float</span><span class="sxs-lookup"><span data-stu-id="5558a-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p121">Tiempo de procesamiento total de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="5558a-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-221">float</span><span class="sxs-lookup"><span data-stu-id="5558a-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p122">Tiempo de procesamiento de promedio de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="5558a-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-225">float</span><span class="sxs-lookup"><span data-stu-id="5558a-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p123">Tiempo de procesamiento máximo de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="5558a-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-229">int</span><span class="sxs-lookup"><span data-stu-id="5558a-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p124">Repeticiones de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="5558a-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-233">float</span><span class="sxs-lookup"><span data-stu-id="5558a-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p125">Densidad de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="5558a-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-237">float</span><span class="sxs-lookup"><span data-stu-id="5558a-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p126">Duración de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="5558a-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-241">int</span><span class="sxs-lookup"><span data-stu-id="5558a-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-242">Repeticiones de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="5558a-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-244">float</span><span class="sxs-lookup"><span data-stu-id="5558a-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p127">Densidad de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una densidad de intervalos baja indica una experiencia de visualización de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="5558a-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-248">float</span><span class="sxs-lookup"><span data-stu-id="5558a-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-p128">Duración de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una duración de intervalos corta indica una experiencia de visualización de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="5558a-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-252">float</span><span class="sxs-lookup"><span data-stu-id="5558a-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-253">Tasa total de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5558a-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-255">float</span><span class="sxs-lookup"><span data-stu-id="5558a-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-256">Tasa media de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5558a-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-258">float</span><span class="sxs-lookup"><span data-stu-id="5558a-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-259">Tasa máxima de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5558a-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-261">int</span><span class="sxs-lookup"><span data-stu-id="5558a-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-262">Repeticiones de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5558a-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-264">float</span><span class="sxs-lookup"><span data-stu-id="5558a-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-265">Densidad de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5558a-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-267">float</span><span class="sxs-lookup"><span data-stu-id="5558a-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-268">Duración de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5558a-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-270">int</span><span class="sxs-lookup"><span data-stu-id="5558a-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-271">Repeticiones de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5558a-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-273">float</span><span class="sxs-lookup"><span data-stu-id="5558a-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-274">Densidad de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5558a-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-276">float</span><span class="sxs-lookup"><span data-stu-id="5558a-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-277">Duración de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="5558a-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-279">float</span><span class="sxs-lookup"><span data-stu-id="5558a-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-280">Porcentaje total de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5558a-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-282">float</span><span class="sxs-lookup"><span data-stu-id="5558a-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-283">Porcentaje medio de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5558a-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-285">float</span><span class="sxs-lookup"><span data-stu-id="5558a-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-286">Porcentaje máximo de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5558a-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-288">int</span><span class="sxs-lookup"><span data-stu-id="5558a-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-289">Repeticiones de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5558a-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-291">float</span><span class="sxs-lookup"><span data-stu-id="5558a-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-292">Densidad de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5558a-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-294">float</span><span class="sxs-lookup"><span data-stu-id="5558a-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-295">Duración de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5558a-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-297">int</span><span class="sxs-lookup"><span data-stu-id="5558a-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-298">Repeticiones de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5558a-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-300">float</span><span class="sxs-lookup"><span data-stu-id="5558a-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-301">Densidad de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5558a-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-303">float</span><span class="sxs-lookup"><span data-stu-id="5558a-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-304">Duración de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="5558a-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-306">float</span><span class="sxs-lookup"><span data-stu-id="5558a-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-307">Número total de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5558a-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-309">float</span><span class="sxs-lookup"><span data-stu-id="5558a-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-310">Número medio de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5558a-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-312">float</span><span class="sxs-lookup"><span data-stu-id="5558a-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-313">Número máximo de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5558a-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-315">int</span><span class="sxs-lookup"><span data-stu-id="5558a-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-316">Repeticiones de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5558a-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-318">float</span><span class="sxs-lookup"><span data-stu-id="5558a-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-319">Densidad de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5558a-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-321">float</span><span class="sxs-lookup"><span data-stu-id="5558a-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-322">Duración de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5558a-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-324">int</span><span class="sxs-lookup"><span data-stu-id="5558a-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-325">Intervalos de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5558a-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-327">float</span><span class="sxs-lookup"><span data-stu-id="5558a-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-328">Densidad de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5558a-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-330">float</span><span class="sxs-lookup"><span data-stu-id="5558a-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-331">Duración de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="5558a-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-333">float</span><span class="sxs-lookup"><span data-stu-id="5558a-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-334">Tasa de tramas de entrada total recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-336">float</span><span class="sxs-lookup"><span data-stu-id="5558a-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-337">Tasa de tramas de entrada de promedio recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-339">float</span><span class="sxs-lookup"><span data-stu-id="5558a-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-340">Tasa de datos de entrada máxima recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-342">int</span><span class="sxs-lookup"><span data-stu-id="5558a-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-343">Repeticiones de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-345">float</span><span class="sxs-lookup"><span data-stu-id="5558a-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-346">Densidad de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-348">float</span><span class="sxs-lookup"><span data-stu-id="5558a-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-349">Duración de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-351">int</span><span class="sxs-lookup"><span data-stu-id="5558a-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-352">Repetición de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-354">float</span><span class="sxs-lookup"><span data-stu-id="5558a-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-355">Densidad de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-357">float</span><span class="sxs-lookup"><span data-stu-id="5558a-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-358">Duración de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-360">float</span><span class="sxs-lookup"><span data-stu-id="5558a-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-361">Tasa de tramas de entrada total recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-363">float</span><span class="sxs-lookup"><span data-stu-id="5558a-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-364">Tasa de tramas de entrada de promedio recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-366">float</span><span class="sxs-lookup"><span data-stu-id="5558a-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-367">Tasa de tramas de entrada máxima recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-369">int</span><span class="sxs-lookup"><span data-stu-id="5558a-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-370">Repeticiones de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-372">float</span><span class="sxs-lookup"><span data-stu-id="5558a-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-373">Densidad de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-375">float</span><span class="sxs-lookup"><span data-stu-id="5558a-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-376">Duración de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-378">int</span><span class="sxs-lookup"><span data-stu-id="5558a-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-379">Repeticiones de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-381">float</span><span class="sxs-lookup"><span data-stu-id="5558a-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-382">Densidad de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-384">float</span><span class="sxs-lookup"><span data-stu-id="5558a-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-385">Duración de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="5558a-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-387">float</span><span class="sxs-lookup"><span data-stu-id="5558a-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-388">Tasa de datos de salida total para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-390">float</span><span class="sxs-lookup"><span data-stu-id="5558a-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-391">Tasa de datos de salida de promedio para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-393">float</span><span class="sxs-lookup"><span data-stu-id="5558a-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-394">Tasa de datos de salida máxima para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-396">int</span><span class="sxs-lookup"><span data-stu-id="5558a-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-397">Repeticiones de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-399">float</span><span class="sxs-lookup"><span data-stu-id="5558a-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-400">Densidad de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-402">float</span><span class="sxs-lookup"><span data-stu-id="5558a-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-403">Duración de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-405">int</span><span class="sxs-lookup"><span data-stu-id="5558a-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-406">Repeticiones de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-408">float</span><span class="sxs-lookup"><span data-stu-id="5558a-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-409">Densidad de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-411">float</span><span class="sxs-lookup"><span data-stu-id="5558a-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-412">Duración de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-414">float</span><span class="sxs-lookup"><span data-stu-id="5558a-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-415">Tasa de tramas de salida total para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-417">float</span><span class="sxs-lookup"><span data-stu-id="5558a-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-418">Tasa de tramas de salida de promedio para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-420">float</span><span class="sxs-lookup"><span data-stu-id="5558a-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-421">Tasa de tramas de salida máxima para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-423">int</span><span class="sxs-lookup"><span data-stu-id="5558a-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-424">Repeticiones de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-426">float</span><span class="sxs-lookup"><span data-stu-id="5558a-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-427">Densidad de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-429">float</span><span class="sxs-lookup"><span data-stu-id="5558a-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-430">Duración de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-432">int</span><span class="sxs-lookup"><span data-stu-id="5558a-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-433">Repeticiones de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-435">float</span><span class="sxs-lookup"><span data-stu-id="5558a-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-436">Densidad de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-438">float</span><span class="sxs-lookup"><span data-stu-id="5558a-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-439">Duración de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="5558a-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-441">int</span><span class="sxs-lookup"><span data-stu-id="5558a-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-442">Promedio de altura de resolución de vídeo en píxeles.</span><span class="sxs-lookup"><span data-stu-id="5558a-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-444">int</span><span class="sxs-lookup"><span data-stu-id="5558a-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-445">Promedio de anchura de resolución de vídeo en píxeles.</span><span class="sxs-lookup"><span data-stu-id="5558a-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-446"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-447">bit</span><span class="sxs-lookup"><span data-stu-id="5558a-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-448">Tasa de tramas de promedio (en tramas por segundo) para las transmisiones de entrada.</span><span class="sxs-lookup"><span data-stu-id="5558a-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5558a-449"><strong>Salida</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-450">bit</span><span class="sxs-lookup"><span data-stu-id="5558a-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-451">Tasa de tramas de promedio (en tramas por segundo) para las transmisiones de salida.</span><span class="sxs-lookup"><span data-stu-id="5558a-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5558a-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="5558a-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="5558a-453">bit</span><span class="sxs-lookup"><span data-stu-id="5558a-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5558a-454">1 significa que la dirección de la secuencia va desde el autor de la llamada hasta el destinatario.</span><span class="sxs-lookup"><span data-stu-id="5558a-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="5558a-455">0 indica que la dirección de la secuencia va del destinatario de la llamada al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5558a-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

