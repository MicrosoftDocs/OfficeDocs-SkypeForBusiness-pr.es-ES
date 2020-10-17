---
title: 'Lync Server 2013: informe de voz y vídeo punto a punto'
description: 'Lync Server 2013: informe de voz y vídeo punto a punto.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43041926b3d6b57508b6ee4c53ca9cb055bcb348
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557276"
---
# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="dcce7-103">Informe de voz y vídeo punto a punto en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcce7-103">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcce7-104">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="dcce7-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="dcce7-105">El informe de voz y vídeo punto a punto proporciona una visión detallada de la distribución de llamadas de voz y vídeo durante un período de tiempo específico (por ejemplo, llamadas por hora o llamadas por día).</span><span class="sxs-lookup"><span data-stu-id="dcce7-105">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day).</span></span> <span data-ttu-id="dcce7-106">El informe también le ofrece la opción de ver todas las llamadas de voz y vídeo realizadas o de ver sólo las llamadas correctas o con error.</span><span class="sxs-lookup"><span data-stu-id="dcce7-106">The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls.</span></span> <span data-ttu-id="dcce7-107">Los informes muestran la información de llamadas desglosada en las siguientes agrupaciones:</span><span class="sxs-lookup"><span data-stu-id="dcce7-107">The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="dcce7-108">Llamadas por grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="dcce7-108">Calls per pool</span></span>

  - <span data-ttu-id="dcce7-109">Llamadas por tipo de llamada (por ejemplo, una llamada de Lync a Lync frente a una llamada de Lync a una persona en la red RTC)</span><span class="sxs-lookup"><span data-stu-id="dcce7-109">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="dcce7-110">Llamadas por tipo de acceso (usuarios que han iniciado sesión en la red interna y los usuarios que han iniciado sesión en la red externa)</span><span class="sxs-lookup"><span data-stu-id="dcce7-110">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="dcce7-111">Llamadas por servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="dcce7-111">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="dcce7-112">Para obtener acceso al informe de voz y vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="dcce7-112">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="dcce7-113">Puede obtener acceso al informe de voz y vídeo punto a punto abriendo el informe de Resumen de actividad punto a punto y, a continuación, haciendo clic en cualquiera de las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="dcce7-113">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="dcce7-114">Total de sesiones de audio punto a punto</span><span class="sxs-lookup"><span data-stu-id="dcce7-114">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="dcce7-115">Total de minutos de audio punto a punto</span><span class="sxs-lookup"><span data-stu-id="dcce7-115">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="dcce7-116">Total de sesiones de vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="dcce7-116">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="dcce7-117">Total de minutos de vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="dcce7-117">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="dcce7-118">Para hacer el mejor uso del informe de voz y vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="dcce7-118">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="dcce7-119">Hay varias formas en las que puede filtrar el informe de voz y vídeo punto a punto.</span><span class="sxs-lookup"><span data-stu-id="dcce7-119">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report.</span></span> <span data-ttu-id="dcce7-120">Sin embargo, esas opciones de filtrado están ocultas en la vista de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dcce7-120">However, those filtering options are hidden from view by default.</span></span> <span data-ttu-id="dcce7-121">Para ver las opciones de filtrado disponibles, haga clic en el botón **Mostrar u ocultar parámetros** en la esquina superior derecha de la ventana del informe.</span><span class="sxs-lookup"><span data-stu-id="dcce7-121">To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="dcce7-122">Filtros</span><span class="sxs-lookup"><span data-stu-id="dcce7-122">Filters</span></span>

<span data-ttu-id="dcce7-123">Los filtros proporcionan una forma de devolver un conjunto de datos más específico o ver los datos de distintas formas.</span><span class="sxs-lookup"><span data-stu-id="dcce7-123">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways.</span></span> <span data-ttu-id="dcce7-124">En la siguiente tabla se enumeran los filtros que se pueden usar con el informe de voz y vídeo punto a punto.</span><span class="sxs-lookup"><span data-stu-id="dcce7-124">The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="dcce7-125">Filtros de informe de voz y vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="dcce7-125">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dcce7-126">Nombre</span><span class="sxs-lookup"><span data-stu-id="dcce7-126">Name</span></span></th>
<th><span data-ttu-id="dcce7-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcce7-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dcce7-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-p104">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="dcce7-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="dcce7-131">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="dcce7-131">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dcce7-p105">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="dcce7-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dcce7-134">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dcce7-134">7/7/2012</span></span></p>
<p><span data-ttu-id="dcce7-135">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="dcce7-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dcce7-136">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dcce7-136">7/3/2012</span></span></p>
<p><span data-ttu-id="dcce7-137">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="dcce7-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcce7-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-p106">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="dcce7-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="dcce7-141">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dcce7-141">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dcce7-p107">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="dcce7-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dcce7-144">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dcce7-144">7/7/2012</span></span></p>
<p><span data-ttu-id="dcce7-145">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="dcce7-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dcce7-146">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dcce7-146">7/3/2012</span></span></p>
<p><span data-ttu-id="dcce7-147">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="dcce7-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcce7-148"><strong>Intervalo de</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-148"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-p108">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="dcce7-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dcce7-151">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="dcce7-151">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dcce7-152">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="dcce7-152">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dcce7-153">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="dcce7-153">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dcce7-154">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="dcce7-154">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="dcce7-p109">Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</span><span class="sxs-lookup"><span data-stu-id="dcce7-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcce7-157"><strong>Tipo de medio</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-157"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-158">Indica el tipo de medio usado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="dcce7-158">Indicates the type of media used in the session.</span></span> <span data-ttu-id="dcce7-159">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="dcce7-159">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dcce7-160">Ambas</span><span class="sxs-lookup"><span data-stu-id="dcce7-160">Both</span></span></p></li>
<li><p><span data-ttu-id="dcce7-161">Audio</span><span class="sxs-lookup"><span data-stu-id="dcce7-161">Audio</span></span></p></li>
<li><p><span data-ttu-id="dcce7-162">Vídeo</span><span class="sxs-lookup"><span data-stu-id="dcce7-162">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcce7-163"><strong>Disposición de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-163"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-164">Indica el éxito o fracaso de la sesión.</span><span class="sxs-lookup"><span data-stu-id="dcce7-164">Indicates the success or failure of the session.</span></span> <span data-ttu-id="dcce7-165">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="dcce7-165">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dcce7-166">Todos</span><span class="sxs-lookup"><span data-stu-id="dcce7-166">[All]</span></span></p></li>
<li><p><span data-ttu-id="dcce7-167">Llamadas correctas</span><span class="sxs-lookup"><span data-stu-id="dcce7-167">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="dcce7-168">Llamadas fallidas</span><span class="sxs-lookup"><span data-stu-id="dcce7-168">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcce7-169"><strong>Informe por</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-169"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-170">Indica los valores a utilizar en el informe.</span><span class="sxs-lookup"><span data-stu-id="dcce7-170">Indicates the values to be used in the report.</span></span> <span data-ttu-id="dcce7-171">Seleccione una opción de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="dcce7-171">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dcce7-172">Recuento de sesiones</span><span class="sxs-lookup"><span data-stu-id="dcce7-172">Session count</span></span></p></li>
<li><p><span data-ttu-id="dcce7-173">Minutos de llamadas</span><span class="sxs-lookup"><span data-stu-id="dcce7-173">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="dcce7-174">Métricas de actividad de voz y vídeo punto a punto por grupo</span><span class="sxs-lookup"><span data-stu-id="dcce7-174">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="dcce7-175">En la siguiente tabla se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="dcce7-175">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="dcce7-176">Métricas de actividad de voz y vídeo punto a punto por grupo</span><span class="sxs-lookup"><span data-stu-id="dcce7-176">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dcce7-177">Nombre</span><span class="sxs-lookup"><span data-stu-id="dcce7-177">Name</span></span></th>
<th><span data-ttu-id="dcce7-178">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="dcce7-178">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dcce7-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcce7-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dcce7-180"><strong>Grupo</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-180"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-181">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-181">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-182">Nombre del grupo de registrador o servidor perimetral usado para la llamada.</span><span class="sxs-lookup"><span data-stu-id="dcce7-182">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcce7-183"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-183"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-184">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-184">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-185">Fecha y hora en que se ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="dcce7-185">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcce7-186"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-186"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-187">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-187">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-188">Número total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="dcce7-188">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="dcce7-189">Métricas de actividad de voz y vídeo punto a punto por tipo de llamada</span><span class="sxs-lookup"><span data-stu-id="dcce7-189">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="dcce7-190">En la siguiente tabla se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada tipo de llamada realizada.</span><span class="sxs-lookup"><span data-stu-id="dcce7-190">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="dcce7-191">Métricas de actividad de voz y vídeo punto a punto por tipo de llamada</span><span class="sxs-lookup"><span data-stu-id="dcce7-191">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dcce7-192">Nombre</span><span class="sxs-lookup"><span data-stu-id="dcce7-192">Name</span></span></th>
<th><span data-ttu-id="dcce7-193">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="dcce7-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dcce7-194">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcce7-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dcce7-195"><strong>Tipo de llamada</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-195"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-196">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-196">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-197">Indica el tipo de llamada que se realizó.</span><span class="sxs-lookup"><span data-stu-id="dcce7-197">Indicates the type of call that was made.</span></span> <span data-ttu-id="dcce7-198">Los valores son uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="dcce7-198">Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dcce7-199">UC a UC</span><span class="sxs-lookup"><span data-stu-id="dcce7-199">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="dcce7-200">UC a RTC</span><span class="sxs-lookup"><span data-stu-id="dcce7-200">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="dcce7-201">RTC a UC</span><span class="sxs-lookup"><span data-stu-id="dcce7-201">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="dcce7-202">PSTN a PSTN</span><span class="sxs-lookup"><span data-stu-id="dcce7-202">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcce7-203"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-203"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-204">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-204">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-205">Fecha y hora en que se ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="dcce7-205">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcce7-206"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-206"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-207">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-207">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-208">Número total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="dcce7-208">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="dcce7-209">Métricas de actividad de voz y vídeo punto a punto por tipo de acceso</span><span class="sxs-lookup"><span data-stu-id="dcce7-209">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="dcce7-210">En la siguiente tabla se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada tipo de acceso de red.</span><span class="sxs-lookup"><span data-stu-id="dcce7-210">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="dcce7-211">Métricas de actividad de voz y vídeo punto a punto por tipo de acceso</span><span class="sxs-lookup"><span data-stu-id="dcce7-211">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dcce7-212">Nombre</span><span class="sxs-lookup"><span data-stu-id="dcce7-212">Name</span></span></th>
<th><span data-ttu-id="dcce7-213">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="dcce7-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dcce7-214">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcce7-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dcce7-215"><strong>Tipo de actividad</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-215"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-216">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-216">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-217">Indica si los clientes iniciaron sesión en la red interna o en la red externa cuando se realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="dcce7-217">Indicates whether the clients were logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="dcce7-218">Los valores suelen ser los siguientes:</span><span class="sxs-lookup"><span data-stu-id="dcce7-218">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dcce7-219">Interno</span><span class="sxs-lookup"><span data-stu-id="dcce7-219">Internal</span></span></p></li>
<li><p><span data-ttu-id="dcce7-220">Externo</span><span class="sxs-lookup"><span data-stu-id="dcce7-220">External</span></span></p></li>
<li><p><span data-ttu-id="dcce7-221">Mixtos</span><span class="sxs-lookup"><span data-stu-id="dcce7-221">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcce7-222"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-222"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-223">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-223">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-224">Fecha y hora en que se ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="dcce7-224">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcce7-225"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-225"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-226">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-226">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-227">Número total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="dcce7-227">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="dcce7-228">Métricas de actividad de voz y vídeo punto a punto por servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="dcce7-228">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="dcce7-229">En la siguiente tabla se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="dcce7-229">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="dcce7-230">Métricas de actividad de voz y vídeo punto a punto por servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="dcce7-230">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dcce7-231">Nombre</span><span class="sxs-lookup"><span data-stu-id="dcce7-231">Name</span></span></th>
<th><span data-ttu-id="dcce7-232">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="dcce7-232">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dcce7-233">Descripción</span><span class="sxs-lookup"><span data-stu-id="dcce7-233">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dcce7-234"><strong>Servidor de mediación</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-234"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-235">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-235">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-236">Nombre del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="dcce7-236">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcce7-237"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-237"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-238">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-238">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-239">Fecha y hora en que se ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="dcce7-239">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcce7-240"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="dcce7-240"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="dcce7-241">No</span><span class="sxs-lookup"><span data-stu-id="dcce7-241">No</span></span></p></td>
<td><p><span data-ttu-id="dcce7-242">Número total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="dcce7-242">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

