---
title: 'Lync Server 2013: informe de Resumen de calidad de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edeec17bccc4c2084f71d3a052d3a44a34f4ed94
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="2d265-102">Informe de Resumen de calidad de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d265-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d265-103">_**Última modificación del tema:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="2d265-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="2d265-104">El Informe de resumen de calidad de medios es, quizás, la mejor opción para analizar la calidad de las llamadas en su organización: este informe proporciona métricas de llamadas de calidad de la experiencia (QoE) detalladas y desglosadas en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="2d265-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="2d265-105">Llamadas de punto a punto de UC (como una llamada de Microsoft Lync 2013 a Microsoft Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="2d265-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="2d265-106">Sesiones de conferencia de UC</span><span class="sxs-lookup"><span data-stu-id="2d265-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="2d265-107">Sesiones de conferencia de RTC</span><span class="sxs-lookup"><span data-stu-id="2d265-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="2d265-108">Llamadas RTC: desvío de medios</span><span class="sxs-lookup"><span data-stu-id="2d265-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="2d265-109">Llamadas RTC (sin desvío): sección de UC</span><span class="sxs-lookup"><span data-stu-id="2d265-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="2d265-110">Llamadas RTC (sin desvío): sección de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="2d265-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="2d265-111">Otros tipos de llamada</span><span class="sxs-lookup"><span data-stu-id="2d265-111">Other Call Types</span></span>

<span data-ttu-id="2d265-112">Al abrir el informe por primera vez, se ve la información de resumen de cada una de estas categorías.</span><span class="sxs-lookup"><span data-stu-id="2d265-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="2d265-113">Sin salir del informe, puede expandir cada categoría para ver subcategorías como las llamadas realizadas desde Office Communicator 2007 R2 a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2d265-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="2d265-114">A su vez, puede profundizar en esas subcategorías para ver detalles sobre cada llamada realizada dentro de esa subcategoría.</span><span class="sxs-lookup"><span data-stu-id="2d265-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="2d265-115">En Microsoft Lync Server 2013, el informe de Resumen de calidad de medios desglosa los datos en tres tipos de llamada: llamadas de audio, videollamadas y llamadas de uso compartido de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2d265-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="2d265-116">Cada tipo de llamada tiene su propia sección en el informe y su propio conjunto personalizado de métricas de llamada.</span><span class="sxs-lookup"><span data-stu-id="2d265-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="2d265-117">El Informe de resumen de calidad de medios también permite aplicar filtros para poder comparar la calidad de las llamadas: llamadas por cable frente a inalámbricas, llamadas internas frente a externas y llamadas de VPN frente a llamadas distintas de VPN.</span><span class="sxs-lookup"><span data-stu-id="2d265-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="2d265-118">Acceso al Informe de resumen de calidad de medios</span><span class="sxs-lookup"><span data-stu-id="2d265-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="2d265-119">Al Informe de resumen de calidad de medios se obtiene acceso desde la página principal de Informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="2d265-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="2d265-120">Puede explorar en profundidad el [Informe de lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) haciendo clic en cualquiera de las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2d265-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="2d265-121">Volumen de llamadas</span><span class="sxs-lookup"><span data-stu-id="2d265-121">Call volume</span></span>

  - <span data-ttu-id="2d265-122">Porcentaje de llamadas deficientes</span><span class="sxs-lookup"><span data-stu-id="2d265-122">Poor call percentage</span></span>

<span data-ttu-id="2d265-123">Además, puede obtener acceso al Informe de resumen de calidad de medios haciendo clic en cualquiera de las siguientes métricas de llamadas de audio:</span><span class="sxs-lookup"><span data-stu-id="2d265-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="2d265-124">Recorrido de ida y vuelta (ms)</span><span class="sxs-lookup"><span data-stu-id="2d265-124">Round trip (ms)</span></span>

  - <span data-ttu-id="2d265-125">Degradación (MOS)</span><span class="sxs-lookup"><span data-stu-id="2d265-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="2d265-126">Pérdida de paquetes</span><span class="sxs-lookup"><span data-stu-id="2d265-126">Packet loss</span></span>

  - <span data-ttu-id="2d265-127">Vibración (ms)</span><span class="sxs-lookup"><span data-stu-id="2d265-127">Jitter (ms)</span></span>

  - <span data-ttu-id="2d265-128">Tasa de recuperación de muestras ocultas</span><span class="sxs-lookup"><span data-stu-id="2d265-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="2d265-129">Tasa de recuperación de muestras extendidas</span><span class="sxs-lookup"><span data-stu-id="2d265-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="2d265-130">Tasa de recuperación de muestras comprimidas</span><span class="sxs-lookup"><span data-stu-id="2d265-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2d265-131">Filtros</span><span class="sxs-lookup"><span data-stu-id="2d265-131">Filters</span></span>

<span data-ttu-id="2d265-p104">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de resumen de calidad de los medios permite filtrar los datos devueltos por el tipo de acceso (acceso interno o externo) o por tipo de conexión de red (cableada o inalámbrica). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="2d265-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2d265-136">En la tabla siguiente se muestran los filtros que se pueden utilizar en el informe de resumen de calidad de los medios.</span><span class="sxs-lookup"><span data-stu-id="2d265-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="2d265-137">Filtros del informe de resumen de calidad de los medios</span><span class="sxs-lookup"><span data-stu-id="2d265-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d265-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d265-138">Name</span></span></th>
<th><span data-ttu-id="2d265-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d265-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d265-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-p105">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2d265-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2d265-143">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="2d265-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2d265-p106">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="2d265-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2d265-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2d265-146">7/7/2012</span></span></p>
<p><span data-ttu-id="2d265-147">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="2d265-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2d265-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2d265-148">7/3/2012</span></span></p>
<p><span data-ttu-id="2d265-149">Las semanas siempre empiezan en domingo y terminan en sábado.</span><span class="sxs-lookup"><span data-stu-id="2d265-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-p107">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2d265-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2d265-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2d265-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2d265-p108">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="2d265-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2d265-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2d265-156">7/7/2012</span></span></p>
<p><span data-ttu-id="2d265-157">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="2d265-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2d265-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2d265-158">7/3/2012</span></span></p>
<p><span data-ttu-id="2d265-159">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="2d265-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-160"><strong>Tipo de acceso</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-p109">Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2d265-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d265-163">Todos</span><span class="sxs-lookup"><span data-stu-id="2d265-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="2d265-164">Interno</span><span class="sxs-lookup"><span data-stu-id="2d265-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="2d265-165">External</span><span class="sxs-lookup"><span data-stu-id="2d265-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-166"><strong>Tipo de red</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-p110">Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2d265-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d265-169">Todos</span><span class="sxs-lookup"><span data-stu-id="2d265-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="2d265-170">Cableada</span><span class="sxs-lookup"><span data-stu-id="2d265-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="2d265-171">Wireless</span><span class="sxs-lookup"><span data-stu-id="2d265-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-p111">Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2d265-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d265-175">Todos</span><span class="sxs-lookup"><span data-stu-id="2d265-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="2d265-176">VPN</span><span class="sxs-lookup"><span data-stu-id="2d265-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="2d265-177">No VPN</span><span class="sxs-lookup"><span data-stu-id="2d265-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2d265-178">Métricas</span><span class="sxs-lookup"><span data-stu-id="2d265-178">Metrics</span></span>

<span data-ttu-id="2d265-179">En la tabla siguiente se muestra la información que recoge el informe de resumen de calidad de los medios.</span><span class="sxs-lookup"><span data-stu-id="2d265-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="2d265-180">Métricas del Informe de resumen de calidad de medios: resumen de llamadas de audio</span><span class="sxs-lookup"><span data-stu-id="2d265-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d265-181">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d265-181">Name</span></span></th>
<th><span data-ttu-id="2d265-182">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="2d265-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2d265-183">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d265-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d265-184"><strong>Tipo de llamada/tipo de extremo</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-185">No</span><span class="sxs-lookup"><span data-stu-id="2d265-185">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p112">Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="2d265-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d265-188">Llamadas de punto a punto de UC</span><span class="sxs-lookup"><span data-stu-id="2d265-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="2d265-189">Sesiones de conferencia de UC</span><span class="sxs-lookup"><span data-stu-id="2d265-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2d265-190">Sesiones de conferencia de RTC</span><span class="sxs-lookup"><span data-stu-id="2d265-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2d265-191">Llamadas RTC: desvío de medios</span><span class="sxs-lookup"><span data-stu-id="2d265-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="2d265-192">Llamadas RTC (sin desvío): sección de UC</span><span class="sxs-lookup"><span data-stu-id="2d265-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="2d265-193">Llamadas RTC (sin desvío): sección de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="2d265-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="2d265-194">Otros tipos de llamada</span><span class="sxs-lookup"><span data-stu-id="2d265-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-195"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-196">No</span><span class="sxs-lookup"><span data-stu-id="2d265-196">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-197">Número total de llamadas por tipo.</span><span class="sxs-lookup"><span data-stu-id="2d265-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-198"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-199">No</span><span class="sxs-lookup"><span data-stu-id="2d265-199">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p113">Número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="2d265-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-202"><strong>Volumen de llamadas (llamada inalámbrica)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-203">No</span><span class="sxs-lookup"><span data-stu-id="2d265-203">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-204">Número total de llamadas que han empleado una conexión inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="2d265-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-205"><strong>Volumen de llamadas (llamada VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-206">No</span><span class="sxs-lookup"><span data-stu-id="2d265-206">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-207">Número total de llamadas que han empleado una conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="2d265-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-208"><strong>Volumen de llamadas (llamada externa)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-209">No</span><span class="sxs-lookup"><span data-stu-id="2d265-209">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-210">Número de llamadas que ha empleado una conexión externa, es decir, una conexión fuera de la red interna.</span><span class="sxs-lookup"><span data-stu-id="2d265-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-211"><strong>Recorrido de ida y vuelta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-212">No</span><span class="sxs-lookup"><span data-stu-id="2d265-212">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p114">Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y, entonces, vuelva. Los tiempos de ida y vuelta de 100 milisegundos o menos se consideran de calidad aceptable.</span><span class="sxs-lookup"><span data-stu-id="2d265-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="2d265-p115">Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor multimedia y causan dificultades en las conversaciones de audio bidireccionales en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="2d265-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-217"><strong>Degradación (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-218">No</span><span class="sxs-lookup"><span data-stu-id="2d265-218">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-219">Cantidad media de degradación de la puntuación de opinión media (MOS) experimentada durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="2d265-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="2d265-220">Los valores de degradación oscilan entre un mínimo de 0,0 y un máximo de 5,0.</span><span class="sxs-lookup"><span data-stu-id="2d265-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="2d265-221">Un valor de 0,5 o menos constituye una degradación aceptable.</span><span class="sxs-lookup"><span data-stu-id="2d265-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="2d265-222">Históricamente, las puntuaciones de opinión media se calculaban haciendo que los usuarios puntuaran la calidad de una llamada en una escala del 1 al 5.</span><span class="sxs-lookup"><span data-stu-id="2d265-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="2d265-223">En Lync Server, Lync Server usa un conjunto de algoritmos para predecir cómo los usuarios calificarían una llamada.</span><span class="sxs-lookup"><span data-stu-id="2d265-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="2d265-p117">Los valores altos de degradación pueden ser producto de la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica, o la sobrecarga de un servidor multimedia o servidor de extremo. Una degradación alta causa la distorsión o la pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="2d265-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-226"><strong>Pérdida de paquetes</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-227">No</span><span class="sxs-lookup"><span data-stu-id="2d265-227">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p118">Tasa media de pérdida de paquetes RTP. (Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino.) Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="2d265-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-231"><strong>Vibración (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-232">No</span><span class="sxs-lookup"><span data-stu-id="2d265-232">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-233">Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="2d265-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2d265-234">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="2d265-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-235"><strong>Tasa de recuperación de muestras ocultas</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-236">No</span><span class="sxs-lookup"><span data-stu-id="2d265-236">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p120">Tasa media de muestras de audio ocultas respecto al número total de muestras. Una muestra de audio oculta es una técnica que se emplea para suavizar la transición brusca que normalmente supondría la pérdida de paquetes de red. Los valores elevados indican niveles igualmente elevados de aplicación de ocultación de pérdidas a causa de la pérdida de paquetes o de las vibraciones, y dan lugar a la distorsión o pérdida del audio.</span><span class="sxs-lookup"><span data-stu-id="2d265-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-239"><strong>Tasa de recuperación de muestras extendidas</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-240">No</span><span class="sxs-lookup"><span data-stu-id="2d265-240">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p121">Tasa media de muestras de audio extendidas respecto al número total de muestras. El audio extendido es el audio que se expande para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red. Los valores elevados indican un grado igualmente elevado de extensión de las muestras a causa de las vibraciones, y dan lugar a un audio robótico o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="2d265-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-243"><strong>Tasa de recuperación de muestras comprimidas</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-244">No</span><span class="sxs-lookup"><span data-stu-id="2d265-244">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p122">Tasa media de muestras de audio comprimidas respecto al número total de muestras. (El audio comprimido es el audio que se comprime para ayudar a mantener el nivel de calidad de la llamada cuando se detecta la pérdida de paquetes en la red). Los valores altos indican un elevado grado de compresión de las muestras a causa de las vibraciones y las consecuencias son un audio acelerado o distorsionado.</span><span class="sxs-lookup"><span data-stu-id="2d265-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="2d265-247">Métricas del Informe de resumen de calidad de medios: resumen de videollamadas</span><span class="sxs-lookup"><span data-stu-id="2d265-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d265-248">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d265-248">Name</span></span></th>
<th><span data-ttu-id="2d265-249">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="2d265-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2d265-250">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d265-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d265-251"><strong>Tipo de llamada/tipo de extremo</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-252">No</span><span class="sxs-lookup"><span data-stu-id="2d265-252">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p123">Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="2d265-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d265-255">Llamadas de punto a punto de UC</span><span class="sxs-lookup"><span data-stu-id="2d265-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="2d265-256">Sesiones de conferencia de UC</span><span class="sxs-lookup"><span data-stu-id="2d265-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2d265-257">Sesiones de conferencia de RTC</span><span class="sxs-lookup"><span data-stu-id="2d265-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2d265-258">Llamadas RTC: desvío de medios</span><span class="sxs-lookup"><span data-stu-id="2d265-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="2d265-259">Llamadas RTC (sin desvío): sección de UC</span><span class="sxs-lookup"><span data-stu-id="2d265-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="2d265-260">Llamadas RTC (sin desvío): sección de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="2d265-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="2d265-261">Otros tipos de llamada</span><span class="sxs-lookup"><span data-stu-id="2d265-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-262"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-263">No</span><span class="sxs-lookup"><span data-stu-id="2d265-263">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-264">Número total de llamadas por tipo.</span><span class="sxs-lookup"><span data-stu-id="2d265-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-265"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-266">No</span><span class="sxs-lookup"><span data-stu-id="2d265-266">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p124">Número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="2d265-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-269"><strong>Volumen de llamadas (llamada inalámbrica)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-270">No</span><span class="sxs-lookup"><span data-stu-id="2d265-270">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-271">Número total de llamadas que han empleado una conexión inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="2d265-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-272"><strong>Volumen de llamadas (llamada VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-273">No</span><span class="sxs-lookup"><span data-stu-id="2d265-273">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-274">Número total de llamadas que han empleado una conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="2d265-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-275"><strong>Volumen de llamadas (llamada externa)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-276">No</span><span class="sxs-lookup"><span data-stu-id="2d265-276">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-277">Número de llamadas que han empleado una conexión externa (es decir, una conexión fuera de la red interna).</span><span class="sxs-lookup"><span data-stu-id="2d265-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-278"><strong>Velocidad de bits media (Kbits/s)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-279">No</span><span class="sxs-lookup"><span data-stu-id="2d265-279">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-280">Velocidad de bits de vídeo media (en kilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="2d265-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-281"><strong>Porcentaje de velocidad de bits baja</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-282">No</span><span class="sxs-lookup"><span data-stu-id="2d265-282">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-283">Porcentaje de la llamada durante el cual la velocidad de bits era baja.</span><span class="sxs-lookup"><span data-stu-id="2d265-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-284"><strong>Pérdida de paquetes salientes</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-285">No</span><span class="sxs-lookup"><span data-stu-id="2d265-285">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p125">Pérdida de paquetes del Protocolo de transporte en tiempo real (RTP) correspondiente a los paquetes salientes. (Se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo que se usa para transmitir audio y vídeo a través de Internet, no llegan a su destino.) Una tasa alta de pérdida se suele deber a la congestión, la falta de ancho de banda, la congestión o las interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</span><span class="sxs-lookup"><span data-stu-id="2d265-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-289"><strong>Porcentaje de fotogramas inmovilizados</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-290">No</span><span class="sxs-lookup"><span data-stu-id="2d265-290">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p126">Porcentaje de fotogramas "inmovilizados". En un fotograma inmovilizado, el vídeo deja de avanzar mientras la parte de audio de la llamada continúa.</span><span class="sxs-lookup"><span data-stu-id="2d265-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-293"><strong>Velocidad media de fotogramas salientes</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-294">No</span><span class="sxs-lookup"><span data-stu-id="2d265-294">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-295">Velocidad media de los fotogramas en las transmisiones salientes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="2d265-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-296"><strong>Velocidad media de fotogramas entrantes</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-297">No</span><span class="sxs-lookup"><span data-stu-id="2d265-297">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-298">Velocidad media de los fotogramas en las transmisiones entrantes durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="2d265-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-299"><strong>Porcentaje de velocidad de fotogramas entrantes lenta</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-300">No</span><span class="sxs-lookup"><span data-stu-id="2d265-300">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-301">Porcentaje de la llamada durante el cual la velocidad de bits del vídeo entrante era baja.</span><span class="sxs-lookup"><span data-stu-id="2d265-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-302"><strong>Porcentaje de estado del cliente</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2d265-303">Indica el estado relativo del dispositivo cliente durante la llamada.</span><span class="sxs-lookup"><span data-stu-id="2d265-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="2d265-304">Métricas del Informe de resumen de calidad de medios: resumen de llamadas de uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2d265-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d265-305">Nombre</span><span class="sxs-lookup"><span data-stu-id="2d265-305">Name</span></span></th>
<th><span data-ttu-id="2d265-306">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="2d265-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2d265-307">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d265-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d265-308"><strong>Tipo de llamada/tipo de extremo</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-309">No</span><span class="sxs-lookup"><span data-stu-id="2d265-309">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p127">Cuando se hace clic en este elemento, el informe muestra información detallada sobre las llamadas de ese tipo. Los tipos de llamadas son:</span><span class="sxs-lookup"><span data-stu-id="2d265-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d265-312">Llamadas de punto a punto de UC</span><span class="sxs-lookup"><span data-stu-id="2d265-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="2d265-313">Sesiones de conferencia de UC</span><span class="sxs-lookup"><span data-stu-id="2d265-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2d265-314">Sesiones de conferencia de RTC</span><span class="sxs-lookup"><span data-stu-id="2d265-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2d265-315">Llamadas RTC: desvío de medios</span><span class="sxs-lookup"><span data-stu-id="2d265-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="2d265-316">Llamadas RTC (sin desvío): sección de UC</span><span class="sxs-lookup"><span data-stu-id="2d265-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="2d265-317">Llamadas RTC (sin desvío): sección de puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="2d265-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="2d265-318">Otros tipos de llamada</span><span class="sxs-lookup"><span data-stu-id="2d265-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-319"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-320">No</span><span class="sxs-lookup"><span data-stu-id="2d265-320">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-321">Número total de llamadas por tipo.</span><span class="sxs-lookup"><span data-stu-id="2d265-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-322"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-323">No</span><span class="sxs-lookup"><span data-stu-id="2d265-323">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p128">Número total de llamadas clasificadas como deficientes. Una llamada deficiente es aquella durante la cual uno de los valores medidos, como mínimo, supera el valor permitido (por ejemplo, una llamada con exceso de vibraciones).</span><span class="sxs-lookup"><span data-stu-id="2d265-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-326"><strong>Volumen de llamadas (llamada inalámbrica)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-327">No</span><span class="sxs-lookup"><span data-stu-id="2d265-327">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-328">Número total de llamadas que han empleado una conexión inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="2d265-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-329"><strong>Volumen de llamadas (llamada VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-330">No</span><span class="sxs-lookup"><span data-stu-id="2d265-330">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-331">Número total de llamadas que han empleado una conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="2d265-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-332"><strong>Volumen de llamadas (llamada externa)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-333">No</span><span class="sxs-lookup"><span data-stu-id="2d265-333">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-334">Número de llamadas que han empleado una conexión externa (es decir, una conexión fuera de la red interna).</span><span class="sxs-lookup"><span data-stu-id="2d265-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-335"><strong>Vibración (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-336">No</span><span class="sxs-lookup"><span data-stu-id="2d265-336">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-337">Valor medio de las vibraciones detectadas entre las llegadas de paquetes RTP.</span><span class="sxs-lookup"><span data-stu-id="2d265-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2d265-338">(La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevados suelen deberse a la congestión o a un servidor multimedia sobrecargado, lo que da como resultado una distorsión o pérdida de audio.</span><span class="sxs-lookup"><span data-stu-id="2d265-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-339"><strong>Unidireccional relativo medio</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-340">No</span><span class="sxs-lookup"><span data-stu-id="2d265-340">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-p130">Retraso unidireccional relativo medio entre dos extremos de medios. Se trata de una medida de la latencia de un solo salto.</span><span class="sxs-lookup"><span data-stu-id="2d265-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d265-343"><strong>Latencia media de procesamiento de mosaicos de RDP</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-344">No</span><span class="sxs-lookup"><span data-stu-id="2d265-344">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-345">La latencia media de procesamiento de mosaicos de RDP en el servidor de conferencias AS durante el transcurso de la sesión de visualización.</span><span class="sxs-lookup"><span data-stu-id="2d265-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="2d265-346">Una media alta refleja un retraso mayor en la experiencia de visualización e incluye la latencia de la red.</span><span class="sxs-lookup"><span data-stu-id="2d265-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="2d265-347">Cuando el servidor de conferencias está sobrecargado, el retraso medio puede ser mayor.</span><span class="sxs-lookup"><span data-stu-id="2d265-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d265-348"><strong>Porcentaje total de mosaicos estropeados</strong></span><span class="sxs-lookup"><span data-stu-id="2d265-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="2d265-349">No</span><span class="sxs-lookup"><span data-stu-id="2d265-349">No</span></span></p></td>
<td><p><span data-ttu-id="2d265-350">Porcentaje total de mosaicos de RDP estropeados.</span><span class="sxs-lookup"><span data-stu-id="2d265-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

