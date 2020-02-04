---
title: 'Lync Server 2013: informe de comparación de calidad multimedia'
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
ms.openlocfilehash: 6bcec69db6154aa346fc4545dc3b50fcfe0f2d6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="3e488-102">Informe de comparación de calidad multimedia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e488-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e488-103">_**Última modificación del tema:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="3e488-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="3e488-104">El informe de comparación de calidad de medios sirve para comparar los valores de calidad de diferentes tipos de llamadas de audio (por ejemplo, de las llamadas realizadas en una red inalámbrica frente a las que usan una conexión cableada).</span><span class="sxs-lookup"><span data-stu-id="3e488-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="3e488-105">Obtener acceso al informe de comparación de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="3e488-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="3e488-106">Al informe de comparación de calidad de medios se obtiene acceso desde la página principal de informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="3e488-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3e488-107">Filtros</span><span class="sxs-lookup"><span data-stu-id="3e488-107">Filters</span></span>

<span data-ttu-id="3e488-p101">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos que se devuelven de distintas formas. En la tabla siguiente se muestran los filtros que puede usar en el informe.</span><span class="sxs-lookup"><span data-stu-id="3e488-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="3e488-110">Filtros del informe de comparación de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="3e488-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e488-111">Nombre</span><span class="sxs-lookup"><span data-stu-id="3e488-111">Name</span></span></th>
<th><span data-ttu-id="3e488-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e488-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e488-113"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-p102">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="3e488-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3e488-116">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="3e488-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3e488-p103">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="3e488-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3e488-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3e488-119">7/7/2012</span></span></p>
<p><span data-ttu-id="3e488-120">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="3e488-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3e488-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3e488-121">7/3/2012</span></span></p>
<p><span data-ttu-id="3e488-122">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="3e488-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e488-123"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-p104">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="3e488-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3e488-126">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="3e488-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3e488-p105">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="3e488-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3e488-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3e488-129">7/7/2012</span></span></p>
<p><span data-ttu-id="3e488-130">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="3e488-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3e488-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3e488-131">7/3/2012</span></span></p>
<p><span data-ttu-id="3e488-132">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="3e488-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e488-133"><strong>Llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-p106">Tipo de llamada que se va a usar como elemento de comparación principal. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="3e488-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e488-136">[Todas]</span><span class="sxs-lookup"><span data-stu-id="3e488-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="3e488-137">Externa</span><span class="sxs-lookup"><span data-stu-id="3e488-137">External</span></span></p></li>
<li><p><span data-ttu-id="3e488-138">Interna</span><span class="sxs-lookup"><span data-stu-id="3e488-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="3e488-139">VPN</span><span class="sxs-lookup"><span data-stu-id="3e488-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="3e488-140">Distinto de VPN</span><span class="sxs-lookup"><span data-stu-id="3e488-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="3e488-141">Cableada</span><span class="sxs-lookup"><span data-stu-id="3e488-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="3e488-142">Inalámbrica</span><span class="sxs-lookup"><span data-stu-id="3e488-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="3e488-143">Externa y cableada</span><span class="sxs-lookup"><span data-stu-id="3e488-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="3e488-144">Externa e inalámbrica</span><span class="sxs-lookup"><span data-stu-id="3e488-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="3e488-145">Externa y VPN</span><span class="sxs-lookup"><span data-stu-id="3e488-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="3e488-146">Externa y distinta de VPN</span><span class="sxs-lookup"><span data-stu-id="3e488-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="3e488-147">Interna y cableada</span><span class="sxs-lookup"><span data-stu-id="3e488-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="3e488-148">Interna e inalámbrica</span><span class="sxs-lookup"><span data-stu-id="3e488-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e488-149"><strong>Comparar con llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-p107">Tipo de llamada que se va a usar como elemento de comparación secundario. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="3e488-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e488-152">[Todas]</span><span class="sxs-lookup"><span data-stu-id="3e488-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="3e488-153">Externa</span><span class="sxs-lookup"><span data-stu-id="3e488-153">External</span></span></p></li>
<li><p><span data-ttu-id="3e488-154">Interna</span><span class="sxs-lookup"><span data-stu-id="3e488-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="3e488-155">VPN</span><span class="sxs-lookup"><span data-stu-id="3e488-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="3e488-156">Distinto de VPN</span><span class="sxs-lookup"><span data-stu-id="3e488-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="3e488-157">Cableada</span><span class="sxs-lookup"><span data-stu-id="3e488-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="3e488-158">Inalámbrica</span><span class="sxs-lookup"><span data-stu-id="3e488-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="3e488-159">Externa y cableada</span><span class="sxs-lookup"><span data-stu-id="3e488-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="3e488-160">Externa e inalámbrica</span><span class="sxs-lookup"><span data-stu-id="3e488-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="3e488-161">Externa y VPN</span><span class="sxs-lookup"><span data-stu-id="3e488-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="3e488-162">Externa y distinta de VPN</span><span class="sxs-lookup"><span data-stu-id="3e488-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="3e488-163">Interna y cableada</span><span class="sxs-lookup"><span data-stu-id="3e488-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="3e488-164">Interna e inalámbrica</span><span class="sxs-lookup"><span data-stu-id="3e488-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e488-165"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-p108">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3e488-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e488-168">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="3e488-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3e488-169">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="3e488-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3e488-170">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="3e488-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="3e488-171">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio).</span><span class="sxs-lookup"><span data-stu-id="3e488-171">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="3e488-172">Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="3e488-172">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="3e488-173">Métricas</span><span class="sxs-lookup"><span data-stu-id="3e488-173">Metrics</span></span>

<span data-ttu-id="3e488-174">En la tabla siguiente se muestra la información que recoge el informe de comparación de calidad de medios.</span><span class="sxs-lookup"><span data-stu-id="3e488-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="3e488-175">Métricas del informe de comparación de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="3e488-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e488-176">Nombre</span><span class="sxs-lookup"><span data-stu-id="3e488-176">Name</span></span></th>
<th><span data-ttu-id="3e488-177">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="3e488-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3e488-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e488-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e488-179"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-180">No</span><span class="sxs-lookup"><span data-stu-id="3e488-180">No</span></span></p></td>
<td><p><span data-ttu-id="3e488-181">Cantidad total de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3e488-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e488-182"><strong>Degradación (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-183">No</span><span class="sxs-lookup"><span data-stu-id="3e488-183">No</span></span></p></td>
<td><p><span data-ttu-id="3e488-184">Cantidad promedio de la degradación de la media (puntuación de opinión) durante una llamada.</span><span class="sxs-lookup"><span data-stu-id="3e488-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="3e488-185">Los valores de degradación pueden oscilar entre un mínimo de 0,0 y un alto de 5,0. un valor de 0,5 o menos representa una degradación aceptable.</span><span class="sxs-lookup"><span data-stu-id="3e488-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="3e488-186">Históricamente, los resultados de la media se calcularon haciendo que los usuarios calificaran la calidad de una llamada en una escala de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="3e488-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="3e488-187">Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios habrían calificado una llamada.</span><span class="sxs-lookup"><span data-stu-id="3e488-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="3e488-p111">Los valores elevados de degradación pueden ser producto de la congestión, la falta de ancho de banda, la congestión o las interferencias en una conexión inalámbrica, o la sobrecarga de un extremo o servidor multimedia. Una degradación elevada causa la distorsión o la pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="3e488-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e488-190"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-191">No</span><span class="sxs-lookup"><span data-stu-id="3e488-191">No</span></span></p></td>
<td><p><span data-ttu-id="3e488-p112">Cantidad total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella en la que al menos uno de los valores medidos supera el valor permitido (por ejemplo, una llamada con un exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="3e488-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e488-194"><strong>Recorrido de ida y vuelta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-195">No</span><span class="sxs-lookup"><span data-stu-id="3e488-195">No</span></span></p></td>
<td><p><span data-ttu-id="3e488-p113">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="3e488-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="3e488-p114">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="3e488-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e488-200"><strong>Pérdida de paquetes</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-201">No</span><span class="sxs-lookup"><span data-stu-id="3e488-201">No</span></span></p></td>
<td><p><span data-ttu-id="3e488-p115">Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="3e488-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e488-205"><strong>Vibración (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-206">No</span><span class="sxs-lookup"><span data-stu-id="3e488-206">No</span></span></p></td>
<td><p><span data-ttu-id="3e488-207">Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="3e488-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="3e488-208">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="3e488-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e488-209"><strong>Tasa de recuperación de muestras ocultas</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-210">No</span><span class="sxs-lookup"><span data-stu-id="3e488-210">No</span></span></p></td>
<td><p><span data-ttu-id="3e488-p117">Tasa media de muestras de audio ocultas respecto a la cantidad total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="3e488-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e488-213"><strong>Tasa de recuperación de muestras extendidas</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-214">No</span><span class="sxs-lookup"><span data-stu-id="3e488-214">No</span></span></p></td>
<td><p><span data-ttu-id="3e488-p118">Tasa media de muestras de audio extendidas respecto a la cantidad total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="3e488-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e488-217"><strong>Tasa de recuperación de muestras comprimidas</strong></span><span class="sxs-lookup"><span data-stu-id="3e488-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3e488-218">No</span><span class="sxs-lookup"><span data-stu-id="3e488-218">No</span></span></p></td>
<td><p><span data-ttu-id="3e488-p119">Tasa media de muestras de audio comprimidas respecto a la cantidad total de muestras. El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="3e488-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

