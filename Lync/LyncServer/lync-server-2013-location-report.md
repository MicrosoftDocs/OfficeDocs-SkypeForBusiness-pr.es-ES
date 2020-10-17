---
title: 'Lync Server 2013: informe de ubicación'
description: 'Lync Server 2013: informe de ubicaciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b819bcffeee0795cd39d3dde3e38fbd9e4a1b7c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569476"
---
# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="049cc-103">Informe de ubicaciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="049cc-103">Location Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="049cc-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="049cc-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="049cc-p101">El informe de ubicaciones proporciona información sobre las métricas de calidad de las llamadas agrupadas por ubicación de red (es decir, por subred de red). Si los usuarios tienen problemas con las llamadas, este informe puede ayudarle a determinar si estos problemas se han extendido o se limitan a un segmento de red determinado.</span><span class="sxs-lookup"><span data-stu-id="049cc-p101">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet). If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="049cc-107">Acceso al informe de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="049cc-107">Accessing the Location Report</span></span>

<span data-ttu-id="049cc-p102">Se obtiene acceso al informe de ubicaciones desde la página principal de informes de supervisión. Para profundizar hasta el informe de lista de llamadas, haga clic en cualquiera de las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="049cc-p102">The Location Report is accessed from the Monitoring Reports home page. You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="049cc-110">Volumen de llamadas</span><span class="sxs-lookup"><span data-stu-id="049cc-110">Call volume</span></span>

  - <span data-ttu-id="049cc-111">Porcentaje de llamadas deficientes</span><span class="sxs-lookup"><span data-stu-id="049cc-111">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="049cc-112">Filtros</span><span class="sxs-lookup"><span data-stu-id="049cc-112">Filters</span></span>

<span data-ttu-id="049cc-p103">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos que se devuelven de distintas formas. Por ejemplo, el informe de ubicaciones le permite filtrar elementos tales como la ubicación del origen de una llamada o si la llamada se realizó desde una conexión inalámbrica o por cable. También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="049cc-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="049cc-117">En la tabla siguiente se muestran los filtros que se pueden usar con el informe de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="049cc-117">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="049cc-118">Filtros del informe de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="049cc-118">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="049cc-119">Nombre</span><span class="sxs-lookup"><span data-stu-id="049cc-119">Name</span></span></th>
<th><span data-ttu-id="049cc-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="049cc-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="049cc-121"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-121"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-p104">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="049cc-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="049cc-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="049cc-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="049cc-p105">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="049cc-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="049cc-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="049cc-127">7/7/2012</span></span></p>
<p><span data-ttu-id="049cc-128">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="049cc-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="049cc-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="049cc-129">7/3/2012</span></span></p>
<p><span data-ttu-id="049cc-130">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="049cc-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049cc-131"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-131"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-p106">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="049cc-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="049cc-134">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="049cc-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="049cc-p107">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="049cc-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="049cc-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="049cc-137">7/7/2012</span></span></p>
<p><span data-ttu-id="049cc-138">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="049cc-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="049cc-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="049cc-139">7/3/2012</span></span></p>
<p><span data-ttu-id="049cc-140">Las semanas siempre empiezan en domingo y terminan en sábado.</span><span class="sxs-lookup"><span data-stu-id="049cc-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049cc-141"><strong>Ubicación del autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-141"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-p108">Subred de IP del usuario que realizó la llamada. Solo puede seleccionar <strong>[Todos]</strong> para indicar todas las subredes.</span><span class="sxs-lookup"><span data-stu-id="049cc-p108">IP subnet of the user who placed the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049cc-144"><strong>Ubicación del destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-144"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-p109">Subred de IP del usuario que recibió la llamada. Solo puede seleccionar <strong>[Todos]</strong> para indicar todas las subredes.</span><span class="sxs-lookup"><span data-stu-id="049cc-p109">IP subnet of the user who received the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049cc-147"><strong>Tipo de red</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-147"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-p110">Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="049cc-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="049cc-150">Todos</span><span class="sxs-lookup"><span data-stu-id="049cc-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="049cc-151">Cableada</span><span class="sxs-lookup"><span data-stu-id="049cc-151">Wired</span></span></p></li>
<li><p><span data-ttu-id="049cc-152">Wireless</span><span class="sxs-lookup"><span data-stu-id="049cc-152">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049cc-153"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-153"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-p111">Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="049cc-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="049cc-156">Todos</span><span class="sxs-lookup"><span data-stu-id="049cc-156">[All]</span></span></p></li>
<li><p><span data-ttu-id="049cc-157">VPN</span><span class="sxs-lookup"><span data-stu-id="049cc-157">VPN</span></span></p></li>
<li><p><span data-ttu-id="049cc-158">No VPN</span><span class="sxs-lookup"><span data-stu-id="049cc-158">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="049cc-159">Métricas</span><span class="sxs-lookup"><span data-stu-id="049cc-159">Metrics</span></span>

<span data-ttu-id="049cc-160">En la tabla siguiente se muestra la información que recoge el informe de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="049cc-160">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="049cc-161">Métricas del informe de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="049cc-161">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="049cc-162">Nombre</span><span class="sxs-lookup"><span data-stu-id="049cc-162">Name</span></span></th>
<th><span data-ttu-id="049cc-163">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="049cc-163">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="049cc-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="049cc-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="049cc-165"><strong>Subred del autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-165"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-166">No</span><span class="sxs-lookup"><span data-stu-id="049cc-166">No</span></span></p></td>
<td><p><span data-ttu-id="049cc-167">Subred de IP del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="049cc-167">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049cc-168"><strong>Subred del destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-168"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-169">No</span><span class="sxs-lookup"><span data-stu-id="049cc-169">No</span></span></p></td>
<td><p><span data-ttu-id="049cc-170">Subred de IP del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="049cc-170">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049cc-171"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-171"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-172">Sí</span><span class="sxs-lookup"><span data-stu-id="049cc-172">Yes</span></span></p></td>
<td><p><span data-ttu-id="049cc-173">Número total de llamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="049cc-173">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049cc-174"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-174"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-175">Sí</span><span class="sxs-lookup"><span data-stu-id="049cc-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="049cc-p112">Porcentaje de llamadas clasificadas como deficientes. Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="049cc-p112">Percentage of calls classified as poor calls. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049cc-178"><strong>Recorrido de ida y vuelta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-178"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-179">Sí</span><span class="sxs-lookup"><span data-stu-id="049cc-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="049cc-p113">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="049cc-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="049cc-p114">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="049cc-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049cc-184"><strong>Degradación (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-184"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-185">Sí</span><span class="sxs-lookup"><span data-stu-id="049cc-185">Yes</span></span></p></td>
<td><p><span data-ttu-id="049cc-186">Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="049cc-186">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="049cc-187">Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0.</span><span class="sxs-lookup"><span data-stu-id="049cc-187">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="049cc-188">Un valor de 0,5 o menos constituye una degradación aceptable.</span><span class="sxs-lookup"><span data-stu-id="049cc-188">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="049cc-189">Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5.</span><span class="sxs-lookup"><span data-stu-id="049cc-189">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="049cc-190">En Lync Server, Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios calificarían una llamada.</span><span class="sxs-lookup"><span data-stu-id="049cc-190">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="049cc-p116">Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="049cc-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049cc-193"><strong>Pérdida de paquetes</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-193"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-194">Sí</span><span class="sxs-lookup"><span data-stu-id="049cc-194">Yes</span></span></p></td>
<td><p><span data-ttu-id="049cc-p117">Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="049cc-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049cc-198"><strong>JIT</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-198"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-199">Sí</span><span class="sxs-lookup"><span data-stu-id="049cc-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="049cc-200">Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="049cc-200">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="049cc-201">(La vibración es una medida de la &quot; irregularidad &quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="049cc-201">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049cc-202"><strong>Tasa de recuperación de muestras ocultas</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-202"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-203">Sí</span><span class="sxs-lookup"><span data-stu-id="049cc-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="049cc-p119">Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="049cc-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="049cc-206"><strong>Tasa de recuperación de muestras extendidas</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-206"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-207">Sí</span><span class="sxs-lookup"><span data-stu-id="049cc-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="049cc-p120">Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="049cc-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="049cc-210"><strong>Tasa de recuperación de muestras comprimidas</strong></span><span class="sxs-lookup"><span data-stu-id="049cc-210"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="049cc-211">Sí</span><span class="sxs-lookup"><span data-stu-id="049cc-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="049cc-p121">Tasa media de muestras de audio comprimidas respecto al número total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="049cc-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

