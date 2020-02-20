---
title: 'Lync Server 2013: informe de comparación de calidad de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2f32f2f97eb8bb5948a218b05d5718897dd0f58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="7ddb8-102">Informe de comparación de calidad de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ddb8-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ddb8-103">_**Última modificación del tema:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="7ddb8-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="7ddb8-104">El informe de comparación de calidad de medios sirve para comparar los valores de calidad de diferentes tipos de llamadas de audio (por ejemplo, de las llamadas realizadas en una red inalámbrica frente a las que usan una conexión cableada).</span><span class="sxs-lookup"><span data-stu-id="7ddb8-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="7ddb8-105">Obtener acceso al informe de comparación de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="7ddb8-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="7ddb8-106">Al informe de comparación de calidad de medios se obtiene acceso desde la página principal de informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7ddb8-107">Filtros</span><span class="sxs-lookup"><span data-stu-id="7ddb8-107">Filters</span></span>

<span data-ttu-id="7ddb8-p101">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos que se devuelven de distintas formas. En la tabla siguiente se muestran los filtros que puede usar en el informe.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="7ddb8-110">Filtros del informe de comparación de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="7ddb8-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ddb8-111">Nombre</span><span class="sxs-lookup"><span data-stu-id="7ddb8-111">Name</span></span></th>
<th><span data-ttu-id="7ddb8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ddb8-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ddb8-113"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-p102">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7ddb8-116">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="7ddb8-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7ddb8-p103">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7ddb8-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7ddb8-119">7/7/2012</span></span></p>
<p><span data-ttu-id="7ddb8-120">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="7ddb8-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7ddb8-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7ddb8-121">7/3/2012</span></span></p>
<p><span data-ttu-id="7ddb8-122">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ddb8-123"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-p104">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7ddb8-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7ddb8-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7ddb8-p105">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7ddb8-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7ddb8-129">7/7/2012</span></span></p>
<p><span data-ttu-id="7ddb8-130">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="7ddb8-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7ddb8-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7ddb8-131">7/3/2012</span></span></p>
<p><span data-ttu-id="7ddb8-132">Las semanas siempre empiezan el domingo y finalizan el sábado.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ddb8-133"><strong>Llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-p106">Tipo de llamada que se va a usar como elemento de comparación principal. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ddb8-136">Todos</span><span class="sxs-lookup"><span data-stu-id="7ddb8-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-137">External</span><span class="sxs-lookup"><span data-stu-id="7ddb8-137">External</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-138">Interno</span><span class="sxs-lookup"><span data-stu-id="7ddb8-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-139">VPN</span><span class="sxs-lookup"><span data-stu-id="7ddb8-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-140">No VPN</span><span class="sxs-lookup"><span data-stu-id="7ddb8-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-141">Cableada</span><span class="sxs-lookup"><span data-stu-id="7ddb8-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-142">Wireless</span><span class="sxs-lookup"><span data-stu-id="7ddb8-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-143">Externa y cableada</span><span class="sxs-lookup"><span data-stu-id="7ddb8-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-144">Externa e inalámbrica</span><span class="sxs-lookup"><span data-stu-id="7ddb8-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-145">Externa y VPN</span><span class="sxs-lookup"><span data-stu-id="7ddb8-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-146">Externa y distinta de VPN</span><span class="sxs-lookup"><span data-stu-id="7ddb8-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-147">Interna y cableada</span><span class="sxs-lookup"><span data-stu-id="7ddb8-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-148">Interna e inalámbrica</span><span class="sxs-lookup"><span data-stu-id="7ddb8-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ddb8-149"><strong>Comparar con llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-p107">Tipo de llamada que se va a usar como elemento de comparación secundario. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ddb8-152">Todos</span><span class="sxs-lookup"><span data-stu-id="7ddb8-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-153">External</span><span class="sxs-lookup"><span data-stu-id="7ddb8-153">External</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-154">Interno</span><span class="sxs-lookup"><span data-stu-id="7ddb8-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-155">VPN</span><span class="sxs-lookup"><span data-stu-id="7ddb8-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-156">No VPN</span><span class="sxs-lookup"><span data-stu-id="7ddb8-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-157">Cableada</span><span class="sxs-lookup"><span data-stu-id="7ddb8-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-158">Wireless</span><span class="sxs-lookup"><span data-stu-id="7ddb8-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-159">Externa y cableada</span><span class="sxs-lookup"><span data-stu-id="7ddb8-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-160">Externa e inalámbrica</span><span class="sxs-lookup"><span data-stu-id="7ddb8-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-161">Externa y VPN</span><span class="sxs-lookup"><span data-stu-id="7ddb8-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-162">Externa y distinta de VPN</span><span class="sxs-lookup"><span data-stu-id="7ddb8-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-163">Interna y cableada</span><span class="sxs-lookup"><span data-stu-id="7ddb8-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-164">Interna e inalámbrica</span><span class="sxs-lookup"><span data-stu-id="7ddb8-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ddb8-165"><strong>Intervalo de</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-p108">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7ddb8-168">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="7ddb8-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-169">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="7ddb8-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7ddb8-170">Cada semana (se puede ver un máximo de 12 semanas).</span><span class="sxs-lookup"><span data-stu-id="7ddb8-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="7ddb8-p109">Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7ddb8-173">Métricas</span><span class="sxs-lookup"><span data-stu-id="7ddb8-173">Metrics</span></span>

<span data-ttu-id="7ddb8-174">En la tabla siguiente se muestra la información que recoge el informe de comparación de calidad de medios.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="7ddb8-175">Métricas del informe de comparación de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="7ddb8-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ddb8-176">Nombre</span><span class="sxs-lookup"><span data-stu-id="7ddb8-176">Name</span></span></th>
<th><span data-ttu-id="7ddb8-177">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="7ddb8-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7ddb8-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ddb8-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ddb8-179"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-180">No</span><span class="sxs-lookup"><span data-stu-id="7ddb8-180">No</span></span></p></td>
<td><p><span data-ttu-id="7ddb8-181">Número total de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ddb8-182"><strong>Degradación (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-183">No</span><span class="sxs-lookup"><span data-stu-id="7ddb8-183">No</span></span></p></td>
<td><p><span data-ttu-id="7ddb8-184">Cantidad media de la degradación de MOS (puntuación media de opinión) experimentada durante una llamada.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="7ddb8-185">Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0; un valor de 0,5 o menos constituye una degradación aceptable.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="7ddb8-186">Históricamente, los resultados de opinión de la media se calcularon haciendo que los usuarios califiquen la calidad de una llamada en una escala de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="7ddb8-187">Lync Server usa un conjunto de algoritmos para predecir la forma en que los usuarios calificarían una llamada.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="7ddb8-p111">Los valores altos de degradación pueden ser producto de la congestión; la falta de ancho de banda; la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o un extremo. Una degradación alta causa la distorsión o la pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ddb8-190"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-191">No</span><span class="sxs-lookup"><span data-stu-id="7ddb8-191">No</span></span></p></td>
<td><p><span data-ttu-id="7ddb8-p112">El número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ddb8-194"><strong>Recorrido de ida y vuelta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-195">No</span><span class="sxs-lookup"><span data-stu-id="7ddb8-195">No</span></span></p></td>
<td><p><span data-ttu-id="7ddb8-p113">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) alcance el otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="7ddb8-p114">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden producirse en el enrutamiento de llamadas internacionales, si la configuración del enrutamiento no es la correcta, o si se produce una sobrecarga en el servidor multimedia, y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ddb8-200"><strong>Pérdida de paquetes</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-201">No</span><span class="sxs-lookup"><span data-stu-id="7ddb8-201">No</span></span></p></td>
<td><p><span data-ttu-id="7ddb8-p115">Tasa media de pérdida de paquetes del Protocolo de transporte en tiempo real (RTP). (Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino.) Una tasa alta de pérdida se suele deber a la congestión; la falta de ancho de banda; la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ddb8-205"><strong>Vibración (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-206">No</span><span class="sxs-lookup"><span data-stu-id="7ddb8-206">No</span></span></p></td>
<td><p><span data-ttu-id="7ddb8-207">Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="7ddb8-208">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ddb8-209"><strong>Tasa de recuperación de muestras ocultas</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-210">No</span><span class="sxs-lookup"><span data-stu-id="7ddb8-210">No</span></span></p></td>
<td><p><span data-ttu-id="7ddb8-p117">Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ddb8-213"><strong>Tasa de recuperación de muestras extendidas</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-214">No</span><span class="sxs-lookup"><span data-stu-id="7ddb8-214">No</span></span></p></td>
<td><p><span data-ttu-id="7ddb8-p118">Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ddb8-217"><strong>Tasa de recuperación de muestras comprimidas</strong></span><span class="sxs-lookup"><span data-stu-id="7ddb8-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="7ddb8-218">No</span><span class="sxs-lookup"><span data-stu-id="7ddb8-218">No</span></span></p></td>
<td><p><span data-ttu-id="7ddb8-p119">Tasa media de muestras de audio comprimidas respecto al número total de muestras. (El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red.) Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones, y esto da lugar a un audio acelerado o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="7ddb8-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

