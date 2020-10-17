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
ms.openlocfilehash: 9b729112aa0fb064a518c50212a6a041a6661be3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499507"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="59d57-102">Tabla AppSharingStream en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59d57-102">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59d57-103">_**Última modificación del tema:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="59d57-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="59d57-104">La tabla AppSharingStream contiene métricas de calidad de la experiencia de los flujos de red utilizados para el uso compartido de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="59d57-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="59d57-105">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59d57-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59d57-106"><strong>Columna</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="59d57-107"><strong>Tipo de datos</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="59d57-108"><strong>Clave o índice</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="59d57-109"><strong>Detalles</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59d57-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="59d57-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="59d57-112">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="59d57-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d57-113">Fecha y hora en que se inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="59d57-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-115">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-115">int</span></span></p></td>
<td><p><span data-ttu-id="59d57-116">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="59d57-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d57-117">Identificador secuencial usado para distinguir las sesiones que se iniciaron en la misma fecha de las que se iniciaron a la misma hora.</span><span class="sxs-lookup"><span data-stu-id="59d57-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="59d57-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="59d57-120">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="59d57-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="59d57-p102">Representa el tipo de línea de vídeo usada en la llamada. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="59d57-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="59d57-123">0: audio</span><span class="sxs-lookup"><span data-stu-id="59d57-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="59d57-124">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="59d57-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="59d57-125">2 – Vídeo panorámico</span><span class="sxs-lookup"><span data-stu-id="59d57-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="59d57-126">3 – uso compartido de aplicaciones y escritorios</span><span class="sxs-lookup"><span data-stu-id="59d57-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-128">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-128">int</span></span></p></td>
<td><p><span data-ttu-id="59d57-129">Principal</span><span class="sxs-lookup"><span data-stu-id="59d57-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="59d57-130">Identificador único del flujo de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="59d57-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-132">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-133">Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="59d57-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="59d57-134">(La vibración es una medida de la &quot; irregularidad &quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="59d57-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-136">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-137">Valor máximo de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="59d57-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="59d57-138">(La vibración es una medida de la &quot; irregularidad &quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="59d57-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-139"><strong>Vuelta</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-140">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p105">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="59d57-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="59d57-p106">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="59d57-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-146">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p107">Tiempo máximo (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="59d57-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="59d57-p108">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="59d57-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-152">float</span><span class="sxs-lookup"><span data-stu-id="59d57-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p109">Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="59d57-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-157">float</span><span class="sxs-lookup"><span data-stu-id="59d57-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p110">Tasa máxima de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="59d57-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-162">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-163">Número de paquetes enviados.</span><span class="sxs-lookup"><span data-stu-id="59d57-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-164"><strong>Ancho de banda más</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-165">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p111">Ancho de banda unilateral estimado disponible al final de la sesión. Se muestra en bits por segundo.</span><span class="sxs-lookup"><span data-stu-id="59d57-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-169">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-170">Descripción de la aplicación que comparte la carga.</span><span class="sxs-lookup"><span data-stu-id="59d57-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-172">float</span><span class="sxs-lookup"><span data-stu-id="59d57-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p112">Cantidad total de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="59d57-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-176">float</span><span class="sxs-lookup"><span data-stu-id="59d57-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p113">Cantidad media de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="59d57-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-180">float</span><span class="sxs-lookup"><span data-stu-id="59d57-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p114">Cantidad máxima de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="59d57-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-184">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p115">Cantidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="59d57-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-189">float</span><span class="sxs-lookup"><span data-stu-id="59d57-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p116">Densidad total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="59d57-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-194">float</span><span class="sxs-lookup"><span data-stu-id="59d57-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p117">Duración total de ráfagas unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="59d57-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-199">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p118">Cantidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="59d57-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-204">float</span><span class="sxs-lookup"><span data-stu-id="59d57-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p119">Densidad total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="59d57-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-209">float</span><span class="sxs-lookup"><span data-stu-id="59d57-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p120">Duración total de intervalos unidireccionales. Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="59d57-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="59d57-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-215">Rol de aplicación (aplicación que comparte o visualiza) y tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="59d57-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-217">float</span><span class="sxs-lookup"><span data-stu-id="59d57-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p121">Tiempo de procesamiento total de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="59d57-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-221">float</span><span class="sxs-lookup"><span data-stu-id="59d57-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p122">Tiempo de procesamiento de promedio de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="59d57-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-225">float</span><span class="sxs-lookup"><span data-stu-id="59d57-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p123">Tiempo de procesamiento máximo de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.</span><span class="sxs-lookup"><span data-stu-id="59d57-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-229">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p124">Repeticiones de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="59d57-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-233">float</span><span class="sxs-lookup"><span data-stu-id="59d57-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p125">Densidad de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="59d57-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-237">float</span><span class="sxs-lookup"><span data-stu-id="59d57-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p126">Duración de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión “con ráfagas” es una transmisión en la que los datos fluyen con ráfagas impredecibles de forma totalmente opuesta a los flujos estables.</span><span class="sxs-lookup"><span data-stu-id="59d57-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-241">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-242">Repeticiones de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP).</span><span class="sxs-lookup"><span data-stu-id="59d57-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-244">float</span><span class="sxs-lookup"><span data-stu-id="59d57-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p127">Densidad de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una densidad de intervalos baja indica una experiencia de visualización de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="59d57-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-248">float</span><span class="sxs-lookup"><span data-stu-id="59d57-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-p128">Duración de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una duración de intervalos corta indica una experiencia de visualización de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="59d57-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-252">float</span><span class="sxs-lookup"><span data-stu-id="59d57-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-253">Tasa total de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="59d57-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-255">float</span><span class="sxs-lookup"><span data-stu-id="59d57-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-256">Tasa media de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="59d57-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-258">float</span><span class="sxs-lookup"><span data-stu-id="59d57-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-259">Tasa máxima de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="59d57-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-261">int</span><span class="sxs-lookup"><span data-stu-id="59d57-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-262">Repeticiones de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="59d57-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-264">float</span><span class="sxs-lookup"><span data-stu-id="59d57-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-265">Densidad de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="59d57-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-267">float</span><span class="sxs-lookup"><span data-stu-id="59d57-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-268">Duración de ráfagas en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="59d57-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-270">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-271">Repeticiones de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="59d57-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-273">float</span><span class="sxs-lookup"><span data-stu-id="59d57-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-274">Densidad de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="59d57-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-276">float</span><span class="sxs-lookup"><span data-stu-id="59d57-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-277">Duración de intervalos en la tasa de datos capturados (en datos por segundo).</span><span class="sxs-lookup"><span data-stu-id="59d57-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-279">float</span><span class="sxs-lookup"><span data-stu-id="59d57-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-280">Porcentaje total de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="59d57-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-282">float</span><span class="sxs-lookup"><span data-stu-id="59d57-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-283">Porcentaje medio de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="59d57-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-285">float</span><span class="sxs-lookup"><span data-stu-id="59d57-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-286">Porcentaje máximo de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="59d57-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-288">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-289">Repeticiones de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="59d57-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-291">float</span><span class="sxs-lookup"><span data-stu-id="59d57-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-292">Densidad de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="59d57-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-294">float</span><span class="sxs-lookup"><span data-stu-id="59d57-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-295">Duración de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="59d57-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-297">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-298">Repeticiones de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="59d57-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-300">float</span><span class="sxs-lookup"><span data-stu-id="59d57-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-301">Densidad de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="59d57-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-303">float</span><span class="sxs-lookup"><span data-stu-id="59d57-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-304">Duración de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.</span><span class="sxs-lookup"><span data-stu-id="59d57-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-306">float</span><span class="sxs-lookup"><span data-stu-id="59d57-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-307">Número total de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="59d57-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-309">float</span><span class="sxs-lookup"><span data-stu-id="59d57-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-310">Número medio de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="59d57-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-312">float</span><span class="sxs-lookup"><span data-stu-id="59d57-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-313">Número máximo de marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="59d57-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-315">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-316">Repeticiones de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="59d57-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-318">float</span><span class="sxs-lookup"><span data-stu-id="59d57-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-319">Densidad de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="59d57-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-321">float</span><span class="sxs-lookup"><span data-stu-id="59d57-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-322">Duración de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="59d57-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-324">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-325">Intervalos de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="59d57-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-327">float</span><span class="sxs-lookup"><span data-stu-id="59d57-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-328">Densidad de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="59d57-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-330">float</span><span class="sxs-lookup"><span data-stu-id="59d57-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-331">Duración de ráfagas en los marcos descartados del origen de los gráficos.</span><span class="sxs-lookup"><span data-stu-id="59d57-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-333">float</span><span class="sxs-lookup"><span data-stu-id="59d57-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-334">Tasa de tramas de entrada total recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-336">float</span><span class="sxs-lookup"><span data-stu-id="59d57-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-337">Tasa de tramas de entrada de promedio recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-339">float</span><span class="sxs-lookup"><span data-stu-id="59d57-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-340">Tasa de datos de entrada máxima recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-342">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-343">Repeticiones de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-345">float</span><span class="sxs-lookup"><span data-stu-id="59d57-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-346">Densidad de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-348">float</span><span class="sxs-lookup"><span data-stu-id="59d57-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-349">Duración de ráfagas de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-351">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-352">Repetición de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-354">float</span><span class="sxs-lookup"><span data-stu-id="59d57-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-355">Densidad de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-357">float</span><span class="sxs-lookup"><span data-stu-id="59d57-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-358">Duración de intervalos de la tasa de datos de entrada recibidos por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-360">float</span><span class="sxs-lookup"><span data-stu-id="59d57-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-361">Tasa de tramas de entrada total recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-363">float</span><span class="sxs-lookup"><span data-stu-id="59d57-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-364">Tasa de tramas de entrada de promedio recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-366">float</span><span class="sxs-lookup"><span data-stu-id="59d57-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-367">Tasa de tramas de entrada máxima recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-369">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-370">Repeticiones de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-372">float</span><span class="sxs-lookup"><span data-stu-id="59d57-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-373">Densidad de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-375">float</span><span class="sxs-lookup"><span data-stu-id="59d57-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-376">Duración de ráfagas de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-378">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-379">Repeticiones de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-381">float</span><span class="sxs-lookup"><span data-stu-id="59d57-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-382">Densidad de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-384">float</span><span class="sxs-lookup"><span data-stu-id="59d57-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-385">Duración de intervalos de la tasa de tramas de entrada recibidas por el visor.</span><span class="sxs-lookup"><span data-stu-id="59d57-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-387">float</span><span class="sxs-lookup"><span data-stu-id="59d57-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-388">Tasa de datos de salida total para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-390">float</span><span class="sxs-lookup"><span data-stu-id="59d57-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-391">Tasa de datos de salida de promedio para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-393">float</span><span class="sxs-lookup"><span data-stu-id="59d57-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-394">Tasa de datos de salida máxima para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-396">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-397">Repeticiones de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-399">float</span><span class="sxs-lookup"><span data-stu-id="59d57-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-400">Densidad de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-402">float</span><span class="sxs-lookup"><span data-stu-id="59d57-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-403">Duración de ráfagas en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-405">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-406">Repeticiones de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-408">float</span><span class="sxs-lookup"><span data-stu-id="59d57-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-409">Densidad de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-411">float</span><span class="sxs-lookup"><span data-stu-id="59d57-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-412">Duración de intervalos en la tasa de datos de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-414">float</span><span class="sxs-lookup"><span data-stu-id="59d57-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-415">Tasa de tramas de salida total para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-417">float</span><span class="sxs-lookup"><span data-stu-id="59d57-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-418">Tasa de tramas de salida de promedio para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-420">float</span><span class="sxs-lookup"><span data-stu-id="59d57-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-421">Tasa de tramas de salida máxima para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-423">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-424">Repeticiones de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-426">float</span><span class="sxs-lookup"><span data-stu-id="59d57-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-427">Densidad de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-429">float</span><span class="sxs-lookup"><span data-stu-id="59d57-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-430">Duración de ráfagas en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-432">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-433">Repeticiones de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-435">float</span><span class="sxs-lookup"><span data-stu-id="59d57-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-436">Densidad de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-438">float</span><span class="sxs-lookup"><span data-stu-id="59d57-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-439">Duración de intervalos en la tasa de tramas de salida para el remitente.</span><span class="sxs-lookup"><span data-stu-id="59d57-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-441">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-442">Promedio de altura de resolución de vídeo en píxeles.</span><span class="sxs-lookup"><span data-stu-id="59d57-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-444">entero</span><span class="sxs-lookup"><span data-stu-id="59d57-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-445">Promedio de anchura de resolución de vídeo en píxeles.</span><span class="sxs-lookup"><span data-stu-id="59d57-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-446"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-447">bit</span><span class="sxs-lookup"><span data-stu-id="59d57-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-448">Tasa de tramas de promedio (en tramas por segundo) para las transmisiones de entrada.</span><span class="sxs-lookup"><span data-stu-id="59d57-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59d57-449"><strong>Saliente</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-450">bit</span><span class="sxs-lookup"><span data-stu-id="59d57-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-451">Tasa de tramas de promedio (en tramas por segundo) para las transmisiones de salida.</span><span class="sxs-lookup"><span data-stu-id="59d57-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59d57-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="59d57-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="59d57-453">bit</span><span class="sxs-lookup"><span data-stu-id="59d57-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59d57-454">1 significa que la dirección de la secuencia va desde el autor de la llamada hasta el destinatario.</span><span class="sxs-lookup"><span data-stu-id="59d57-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="59d57-455">0 indica que la dirección de la secuencia va del destinatario de la llamada al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="59d57-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

