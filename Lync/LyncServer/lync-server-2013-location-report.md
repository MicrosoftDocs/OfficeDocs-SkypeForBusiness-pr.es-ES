---
title: 'Lync Server 2013: informe de ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac5ab1d077acb8f96849b4ac44911a4c90786fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="9f70e-102">Informe de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f70e-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f70e-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9f70e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9f70e-p101">El informe de ubicaciones proporciona información sobre las métricas de calidad de las llamadas agrupadas por ubicación de red (es decir, por subred de red). Si los usuarios tienen problemas con las llamadas, este informe puede ayudarle a determinar si estos problemas se han extendido o se limitan a un segmento de red determinado.</span><span class="sxs-lookup"><span data-stu-id="9f70e-p101">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet). If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="9f70e-106">Acceso al informe de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="9f70e-106">Accessing the Location Report</span></span>

<span data-ttu-id="9f70e-p102">Se obtiene acceso al informe de ubicaciones desde la página principal de informes de supervisión. Para profundizar hasta el informe de lista de llamadas, haga clic en cualquiera de las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="9f70e-p102">The Location Report is accessed from the Monitoring Reports home page. You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="9f70e-109">Volumen de llamadas</span><span class="sxs-lookup"><span data-stu-id="9f70e-109">Call volume</span></span>

  - <span data-ttu-id="9f70e-110">Porcentaje de llamadas deficientes</span><span class="sxs-lookup"><span data-stu-id="9f70e-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9f70e-111">Filtros</span><span class="sxs-lookup"><span data-stu-id="9f70e-111">Filters</span></span>

<span data-ttu-id="9f70e-112">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas.</span><span class="sxs-lookup"><span data-stu-id="9f70e-112">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="9f70e-113">Por ejemplo, el informe de ubicaciones le permite filtrar elementos tales como la ubicación del origen de una llamada o si la llamada se realizó desde una conexión inalámbrica o por cable.</span><span class="sxs-lookup"><span data-stu-id="9f70e-113">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="9f70e-114">También se puede elegir cómo agrupar los datos.</span><span class="sxs-lookup"><span data-stu-id="9f70e-114">You can also choose how data should be grouped.</span></span> <span data-ttu-id="9f70e-115">En este caso, las llamadas se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="9f70e-115">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="9f70e-116">En la tabla siguiente se muestran los filtros que se pueden usar con el informe de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9f70e-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="9f70e-117">Filtros del informe de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="9f70e-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f70e-118">Nombre</span><span class="sxs-lookup"><span data-stu-id="9f70e-118">Name</span></span></th>
<th><span data-ttu-id="9f70e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f70e-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f70e-120"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-p104">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="9f70e-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="9f70e-123">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="9f70e-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9f70e-p105">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="9f70e-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9f70e-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9f70e-126">7/7/2012</span></span></p>
<p><span data-ttu-id="9f70e-127">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="9f70e-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9f70e-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9f70e-128">7/3/2012</span></span></p>
<p><span data-ttu-id="9f70e-129">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="9f70e-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f70e-130"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-p106">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="9f70e-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="9f70e-133">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="9f70e-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9f70e-p107">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="9f70e-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9f70e-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9f70e-136">7/7/2012</span></span></p>
<p><span data-ttu-id="9f70e-137">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="9f70e-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9f70e-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9f70e-138">7/3/2012</span></span></p>
<p><span data-ttu-id="9f70e-139">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="9f70e-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f70e-140"><strong>Ubicación del autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-p108">Subred de IP del usuario que realizó la llamada. Solo puede seleccionar <strong>[Todos]</strong> para indicar todas las subredes.</span><span class="sxs-lookup"><span data-stu-id="9f70e-p108">IP subnet of the user who placed the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f70e-143"><strong>Ubicación del destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-p109">Subred de IP del usuario que recibió la llamada. Solo puede seleccionar <strong>[Todos]</strong> para indicar todas las subredes.</span><span class="sxs-lookup"><span data-stu-id="9f70e-p109">IP subnet of the user who received the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f70e-146"><strong>Tipo de red</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-p110">Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9f70e-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="9f70e-149">[Todas]</span><span class="sxs-lookup"><span data-stu-id="9f70e-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="9f70e-150">Cableada</span><span class="sxs-lookup"><span data-stu-id="9f70e-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="9f70e-151">Inalámbrica</span><span class="sxs-lookup"><span data-stu-id="9f70e-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f70e-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-p111">Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9f70e-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="9f70e-155">[Todas]</span><span class="sxs-lookup"><span data-stu-id="9f70e-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="9f70e-156">VPN</span><span class="sxs-lookup"><span data-stu-id="9f70e-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="9f70e-157">Distinto de VPN</span><span class="sxs-lookup"><span data-stu-id="9f70e-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="9f70e-158">Métricas</span><span class="sxs-lookup"><span data-stu-id="9f70e-158">Metrics</span></span>

<span data-ttu-id="9f70e-159">En la tabla siguiente se muestra la información que recoge el informe de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9f70e-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="9f70e-160">Métricas del informe de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="9f70e-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f70e-161">Nombre</span><span class="sxs-lookup"><span data-stu-id="9f70e-161">Name</span></span></th>
<th><span data-ttu-id="9f70e-162">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="9f70e-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9f70e-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f70e-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f70e-164"><strong>Subred del autor de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-165">No</span><span class="sxs-lookup"><span data-stu-id="9f70e-165">No</span></span></p></td>
<td><p><span data-ttu-id="9f70e-166">Subred de IP del usuario que realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f70e-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f70e-167"><strong>Subred del destinatario de la llamada</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-168">No</span><span class="sxs-lookup"><span data-stu-id="9f70e-168">No</span></span></p></td>
<td><p><span data-ttu-id="9f70e-169">Subred de IP del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f70e-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f70e-170"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-171">Sí</span><span class="sxs-lookup"><span data-stu-id="9f70e-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="9f70e-172">Cantidad total de llamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="9f70e-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f70e-173"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-174">Sí</span><span class="sxs-lookup"><span data-stu-id="9f70e-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="9f70e-p112">Porcentaje de llamadas clasificadas como deficientes. Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="9f70e-p112">Percentage of calls classified as poor calls. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f70e-177"><strong>Recorrido de ida y vuelta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-178">Sí</span><span class="sxs-lookup"><span data-stu-id="9f70e-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="9f70e-p113">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="9f70e-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="9f70e-p114">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="9f70e-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f70e-183"><strong>Degradación (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-184">Sí</span><span class="sxs-lookup"><span data-stu-id="9f70e-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="9f70e-185">Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="9f70e-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="9f70e-186">Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0.</span><span class="sxs-lookup"><span data-stu-id="9f70e-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="9f70e-187">Un valor de 0,5 o menos constituye una degradación aceptable.</span><span class="sxs-lookup"><span data-stu-id="9f70e-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="9f70e-188">Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5.</span><span class="sxs-lookup"><span data-stu-id="9f70e-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="9f70e-189">En Lync Server, Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios habrían calificado una llamada.</span><span class="sxs-lookup"><span data-stu-id="9f70e-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="9f70e-p116">Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="9f70e-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f70e-192"><strong>Pérdida de paquetes</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-193">Sí</span><span class="sxs-lookup"><span data-stu-id="9f70e-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="9f70e-p117">Tasa media de pérdida de paquetes RTP. Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino. Una tasa alta de pérdida suele deberse a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="9f70e-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f70e-197"><strong>Vibración</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-198">Sí</span><span class="sxs-lookup"><span data-stu-id="9f70e-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="9f70e-199">Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="9f70e-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="9f70e-200">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="9f70e-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f70e-201"><strong>Tasa de recuperación de muestras ocultas</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-202">Sí</span><span class="sxs-lookup"><span data-stu-id="9f70e-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="9f70e-p119">Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="9f70e-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f70e-205"><strong>Tasa de recuperación de muestras extendidas</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-206">Sí</span><span class="sxs-lookup"><span data-stu-id="9f70e-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="9f70e-p120">Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="9f70e-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f70e-209"><strong>Tasa de recuperación de muestras comprimidas</strong></span><span class="sxs-lookup"><span data-stu-id="9f70e-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9f70e-210">Sí</span><span class="sxs-lookup"><span data-stu-id="9f70e-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="9f70e-p121">Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="9f70e-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

