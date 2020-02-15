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
ms.openlocfilehash: 31a75ddd223816c57a69bd0c9e88b48845d4374e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="86b3c-102">Tabla AppSharingStream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b3c-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86b3c-103">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="86b3c-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="86b3c-104">La tabla AppSharingStream contiene métricas de calidad de la experiencia de los flujos de red utilizados para el uso compartido de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="86b3c-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="86b3c-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86b3c-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86b3c-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="86b3c-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="86b3c-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="86b3c-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="86b3c-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="86b3c-112">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="86b3c-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="86b3c-113">Fecha y hora en que se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="86b3c-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-115">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-115">int</span></span></p></td>
<td><p><span data-ttu-id="86b3c-116">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="86b3c-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="86b3c-117">Identificador secuencial usado para distinguir las sesiones que se iniciaron en la misma fecha de las que se iniciaron a la misma hora.</span><span class="sxs-lookup"><span data-stu-id="86b3c-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="86b3c-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="86b3c-120">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="86b3c-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="86b3c-p102">Representa el tipo de línea de vídeo usada en la llamada. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="86b3c-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="86b3c-123">0: audio</span><span class="sxs-lookup"><span data-stu-id="86b3c-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="86b3c-124">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="86b3c-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="86b3c-125">2 – Vídeo panorámico</span><span class="sxs-lookup"><span data-stu-id="86b3c-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="86b3c-126">3 – uso compartido de aplicaciones y escritorios</span><span class="sxs-lookup"><span data-stu-id="86b3c-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-128">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-128">int</span></span></p></td>
<td><p><span data-ttu-id="86b3c-129">Principal</span><span class="sxs-lookup"><span data-stu-id="86b3c-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="86b3c-130">Identificador único del flujo de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="86b3c-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-132">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-133">Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="86b3c-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="86b3c-134">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="86b3c-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-136">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-137">Valor máximo de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="86b3c-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="86b3c-138">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="86b3c-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-139"><strong>Vuelta</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-140">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p105">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="86b3c-p106">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden producirse en el enrutamiento de llamadas internacionales, si la configuración del enrutamiento no es la correcta, o si se produce una sobrecarga en el servidor multimedia, y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-146">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p107">Tiempo máximo (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="86b3c-p108">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-152">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p109">Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-157">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p110">Tasa máxima de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-162">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-163">Número de paquetes enviados.</span><span class="sxs-lookup"><span data-stu-id="86b3c-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-164"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-165">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p111">Ancho de banda unilateral estimado disponible al final de la sesión. Se muestra en bits por segundo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-169">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-170">Descripción de la aplicación que comparte la carga.</span><span class="sxs-lookup"><span data-stu-id="86b3c-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-172">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p112">Cantidad total de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-176">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p113">Cantidad media de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-180">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p114">Cantidad máxima de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-184">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p115">Cantidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-189">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p116">Densidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-194">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p117">Duración total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-199">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p118">Cantidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-204">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p119">Densidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-209">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p120">Duración total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="86b3c-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-215">Rol de aplicación (aplicación que comparte o visualiza) y tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="86b3c-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-217">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p121">Tiempo de procesamiento total de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-221">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p122">Tiempo de procesamiento de promedio de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-225">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p123">Tiempo de procesamiento máximo de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-229">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p124">Repeticiones de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-233">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p125">Densidad de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-237">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p126">Duración de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-241">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-242">Repeticiones de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="86b3c-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-244">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p127">Densidad de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una densidad de intervalos baja indica una experiencia de visualización de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-248">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-p128">Duración de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una duración de intervalos corta indica una experiencia de visualización de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="86b3c-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-252">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-253">Tasa total de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="86b3c-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-255">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-256">Tasa media de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="86b3c-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-258">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-259">Tasa máxima de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="86b3c-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-261">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-262">Repeticiones de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="86b3c-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-264">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-265">Densidad de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="86b3c-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-267">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-268">Duración de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="86b3c-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-270">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-271">Repeticiones de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="86b3c-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-273">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-274">Densidad de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="86b3c-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-276">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-277">Duración de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="86b3c-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-279">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-280">Porcentaje total de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-282">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-283">Porcentaje medio de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-285">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-286">Porcentaje máximo de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-288">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-289">Repeticiones de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-291">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-292">Densidad de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-294">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-295">Duración de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-297">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-298">Repeticiones de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-300">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-301">Densidad de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-303">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-304">Duración de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="86b3c-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-306">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-307">Número total de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-309">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-310">Número medio de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-312">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-313">Número máximo de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-315">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-316">Repeticiones de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-318">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-319">Densidad de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-321">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-322">Duración de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-324">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-325">Intervalos de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-327">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-328">Densidad de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-330">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-331">Duración de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="86b3c-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-333">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-334">Tasa de tramas de entrada total recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-336">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-337">Tasa de tramas de entrada de promedio recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-339">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-340">Tasa de datos de entrada máxima recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-342">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-343">Repeticiones de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-345">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-346">Densidad de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-348">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-349">Duración de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-351">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-352">Repetición de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-354">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-355">Densidad de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-357">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-358">Duración de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-360">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-361">Tasa de tramas de entrada total recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-363">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-364">Tasa de tramas de entrada de promedio recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-366">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-367">Tasa de tramas de entrada máxima recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-369">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-370">Repeticiones de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-372">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-373">Densidad de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-375">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-376">Duración de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-378">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-379">Repeticiones de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-381">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-382">Densidad de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-384">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-385">Duración de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="86b3c-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-387">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-388">Tasa de datos de salida total para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-390">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-391">Tasa de datos de salida de promedio para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-393">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-394">Tasa de datos de salida máxima para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-396">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-397">Repeticiones de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-399">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-400">Densidad de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-402">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-403">Duración de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-405">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-406">Repeticiones de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-408">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-409">Densidad de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-411">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-412">Duración de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-414">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-415">Tasa de tramas de salida total para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-417">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-418">Tasa de tramas de salida de promedio para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-420">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-421">Tasa de tramas de salida máxima para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-423">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-424">Repeticiones de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-426">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-427">Densidad de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-429">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-430">Duración de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-432">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-433">Repeticiones de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-435">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-436">Densidad de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-438">float</span><span class="sxs-lookup"><span data-stu-id="86b3c-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-439">Duración de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="86b3c-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-441">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-442">Promedio de altura de resolución de vídeo en píxeles.</span><span class="sxs-lookup"><span data-stu-id="86b3c-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-444">int</span><span class="sxs-lookup"><span data-stu-id="86b3c-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-445">Promedio de anchura de resolución de vídeo en píxeles.</span><span class="sxs-lookup"><span data-stu-id="86b3c-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-446"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-447">bit</span><span class="sxs-lookup"><span data-stu-id="86b3c-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-448">Tasa de tramas de promedio (en tramas por segundo) para las transmisiones de entrada.</span><span class="sxs-lookup"><span data-stu-id="86b3c-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86b3c-449"><strong>Salida</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-450">bit</span><span class="sxs-lookup"><span data-stu-id="86b3c-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-451">Tasa de tramas de promedio (en tramas por segundo) para las transmisiones de salida.</span><span class="sxs-lookup"><span data-stu-id="86b3c-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b3c-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="86b3c-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="86b3c-453">bit</span><span class="sxs-lookup"><span data-stu-id="86b3c-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86b3c-454">1 significa que la dirección de la secuencia va desde el autor de la llamada hasta el destinatario.</span><span class="sxs-lookup"><span data-stu-id="86b3c-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="86b3c-455">0 indica que la dirección de la secuencia va del destinatario de la llamada al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="86b3c-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

