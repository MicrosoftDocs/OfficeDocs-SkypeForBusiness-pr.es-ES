---
title: 'Lync Server 2013: informe de voz y vídeo punto a punto'
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
ms.openlocfilehash: 880104d0809b0135c74c72a80eefb7d4bb0ed709
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="314b7-102">Informe de voz y vídeo punto a punto en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="314b7-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="314b7-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="314b7-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="314b7-104">El informe de voz y vídeo punto a punto proporciona una visión detallada de la distribución de llamadas de voz y vídeo durante un período de tiempo específico (por ejemplo, llamadas por hora o llamadas por día).</span><span class="sxs-lookup"><span data-stu-id="314b7-104">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day).</span></span> <span data-ttu-id="314b7-105">El informe también le ofrece la opción de ver todas las llamadas de voz y vídeo realizadas o de ver sólo las llamadas correctas o con error.</span><span class="sxs-lookup"><span data-stu-id="314b7-105">The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls.</span></span> <span data-ttu-id="314b7-106">Los informes muestran la información de llamadas desglosada en las siguientes agrupaciones:</span><span class="sxs-lookup"><span data-stu-id="314b7-106">The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="314b7-107">Llamadas por grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="314b7-107">Calls per pool</span></span>

  - <span data-ttu-id="314b7-108">Llamadas por tipo de llamada (por ejemplo, una llamada de Lync a Lync frente a una llamada de Lync a una persona en la red RTC)</span><span class="sxs-lookup"><span data-stu-id="314b7-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="314b7-109">Llamadas por tipo de acceso (usuarios que han iniciado sesión en la red interna y los usuarios que han iniciado sesión en la red externa)</span><span class="sxs-lookup"><span data-stu-id="314b7-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="314b7-110">Llamadas por servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="314b7-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="314b7-111">Para obtener acceso al informe de voz y vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="314b7-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="314b7-112">Puede obtener acceso al informe de voz y vídeo punto a punto abriendo el informe de Resumen de actividad punto a punto y, a continuación, haciendo clic en cualquiera de las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="314b7-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="314b7-113">Total de sesiones de audio punto a punto</span><span class="sxs-lookup"><span data-stu-id="314b7-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="314b7-114">Total de minutos de audio punto a punto</span><span class="sxs-lookup"><span data-stu-id="314b7-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="314b7-115">Total de sesiones de vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="314b7-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="314b7-116">Total de minutos de vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="314b7-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="314b7-117">Para hacer el mejor uso del informe de voz y vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="314b7-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="314b7-118">Hay varias formas en las que puede filtrar el informe de voz y vídeo punto a punto.</span><span class="sxs-lookup"><span data-stu-id="314b7-118">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report.</span></span> <span data-ttu-id="314b7-119">Sin embargo, esas opciones de filtrado están ocultas en la vista de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="314b7-119">However, those filtering options are hidden from view by default.</span></span> <span data-ttu-id="314b7-120">Para ver las opciones de filtrado disponibles, haga clic en el botón **Mostrar u ocultar parámetros** en la esquina superior derecha de la ventana del informe.</span><span class="sxs-lookup"><span data-stu-id="314b7-120">To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="314b7-121">Filtros</span><span class="sxs-lookup"><span data-stu-id="314b7-121">Filters</span></span>

<span data-ttu-id="314b7-122">Los filtros proporcionan una forma de devolver un conjunto de datos más específico o ver los datos de distintas formas.</span><span class="sxs-lookup"><span data-stu-id="314b7-122">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways.</span></span> <span data-ttu-id="314b7-123">En la siguiente tabla se enumeran los filtros que se pueden usar con el informe de voz y vídeo punto a punto.</span><span class="sxs-lookup"><span data-stu-id="314b7-123">The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="314b7-124">Filtros de informe de voz y vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="314b7-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="314b7-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="314b7-125">Name</span></span></th>
<th><span data-ttu-id="314b7-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="314b7-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="314b7-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-p104">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="314b7-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="314b7-130">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="314b7-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="314b7-p105">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="314b7-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="314b7-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="314b7-133">7/7/2012</span></span></p>
<p><span data-ttu-id="314b7-134">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="314b7-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="314b7-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="314b7-135">7/3/2012</span></span></p>
<p><span data-ttu-id="314b7-136">Las semanas siempre empiezan en domingo y terminan en sábado.</span><span class="sxs-lookup"><span data-stu-id="314b7-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="314b7-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-p106">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="314b7-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="314b7-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="314b7-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="314b7-p107">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="314b7-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="314b7-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="314b7-143">7/7/2012</span></span></p>
<p><span data-ttu-id="314b7-144">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="314b7-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="314b7-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="314b7-145">7/3/2012</span></span></p>
<p><span data-ttu-id="314b7-146">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="314b7-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="314b7-147"><strong>Intervalo de</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-p108">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="314b7-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="314b7-150">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="314b7-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="314b7-151">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="314b7-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="314b7-152">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="314b7-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="314b7-153">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="314b7-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="314b7-p109">Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</span><span class="sxs-lookup"><span data-stu-id="314b7-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="314b7-156"><strong>Tipo de medio</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-157">Indica el tipo de medio usado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="314b7-157">Indicates the type of media used in the session.</span></span> <span data-ttu-id="314b7-158">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="314b7-158">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="314b7-159">Ambas</span><span class="sxs-lookup"><span data-stu-id="314b7-159">Both</span></span></p></li>
<li><p><span data-ttu-id="314b7-160">Audio</span><span class="sxs-lookup"><span data-stu-id="314b7-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="314b7-161">Vídeo</span><span class="sxs-lookup"><span data-stu-id="314b7-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="314b7-162"><strong>Disposición de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-163">Indica el éxito o fracaso de la sesión.</span><span class="sxs-lookup"><span data-stu-id="314b7-163">Indicates the success or failure of the session.</span></span> <span data-ttu-id="314b7-164">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="314b7-164">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="314b7-165">Todos</span><span class="sxs-lookup"><span data-stu-id="314b7-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="314b7-166">Llamadas correctas</span><span class="sxs-lookup"><span data-stu-id="314b7-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="314b7-167">Llamadas fallidas</span><span class="sxs-lookup"><span data-stu-id="314b7-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="314b7-168"><strong>Informe por</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-169">Indica los valores a utilizar en el informe.</span><span class="sxs-lookup"><span data-stu-id="314b7-169">Indicates the values to be used in the report.</span></span> <span data-ttu-id="314b7-170">Seleccione una opción de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="314b7-170">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="314b7-171">Recuento de sesiones</span><span class="sxs-lookup"><span data-stu-id="314b7-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="314b7-172">Minutos de llamadas</span><span class="sxs-lookup"><span data-stu-id="314b7-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="314b7-173">Métricas de actividad de voz y vídeo punto a punto por grupo</span><span class="sxs-lookup"><span data-stu-id="314b7-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="314b7-174">En la siguiente tabla se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="314b7-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="314b7-175">Métricas de actividad de voz y vídeo punto a punto por grupo</span><span class="sxs-lookup"><span data-stu-id="314b7-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="314b7-176">Nombre</span><span class="sxs-lookup"><span data-stu-id="314b7-176">Name</span></span></th>
<th><span data-ttu-id="314b7-177">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="314b7-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="314b7-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="314b7-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="314b7-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-180">No</span><span class="sxs-lookup"><span data-stu-id="314b7-180">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-181">Nombre del grupo de registrador o servidor perimetral usado para la llamada.</span><span class="sxs-lookup"><span data-stu-id="314b7-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="314b7-182"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-183">No</span><span class="sxs-lookup"><span data-stu-id="314b7-183">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-184">Fecha y hora en que se ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="314b7-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="314b7-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-186">No</span><span class="sxs-lookup"><span data-stu-id="314b7-186">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-187">Número total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="314b7-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="314b7-188">Métricas de actividad de voz y vídeo punto a punto por tipo de llamada</span><span class="sxs-lookup"><span data-stu-id="314b7-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="314b7-189">En la siguiente tabla se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada tipo de llamada realizada.</span><span class="sxs-lookup"><span data-stu-id="314b7-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="314b7-190">Métricas de actividad de voz y vídeo punto a punto por tipo de llamada</span><span class="sxs-lookup"><span data-stu-id="314b7-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="314b7-191">Nombre</span><span class="sxs-lookup"><span data-stu-id="314b7-191">Name</span></span></th>
<th><span data-ttu-id="314b7-192">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="314b7-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="314b7-193">Descripción</span><span class="sxs-lookup"><span data-stu-id="314b7-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="314b7-194"><strong>Tipo de llamada</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-195">No</span><span class="sxs-lookup"><span data-stu-id="314b7-195">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-196">Indica el tipo de llamada que se realizó.</span><span class="sxs-lookup"><span data-stu-id="314b7-196">Indicates the type of call that was made.</span></span> <span data-ttu-id="314b7-197">Los valores son uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="314b7-197">Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="314b7-198">UC a UC</span><span class="sxs-lookup"><span data-stu-id="314b7-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="314b7-199">UC a RTC</span><span class="sxs-lookup"><span data-stu-id="314b7-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="314b7-200">RTC a UC</span><span class="sxs-lookup"><span data-stu-id="314b7-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="314b7-201">PSTN a PSTN</span><span class="sxs-lookup"><span data-stu-id="314b7-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="314b7-202"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-203">No</span><span class="sxs-lookup"><span data-stu-id="314b7-203">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-204">Fecha y hora en que se ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="314b7-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="314b7-205"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-206">No</span><span class="sxs-lookup"><span data-stu-id="314b7-206">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-207">Número total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="314b7-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="314b7-208">Métricas de actividad de voz y vídeo punto a punto por tipo de acceso</span><span class="sxs-lookup"><span data-stu-id="314b7-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="314b7-209">En la siguiente tabla se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada tipo de acceso de red.</span><span class="sxs-lookup"><span data-stu-id="314b7-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="314b7-210">Métricas de actividad de voz y vídeo punto a punto por tipo de acceso</span><span class="sxs-lookup"><span data-stu-id="314b7-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="314b7-211">Nombre</span><span class="sxs-lookup"><span data-stu-id="314b7-211">Name</span></span></th>
<th><span data-ttu-id="314b7-212">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="314b7-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="314b7-213">Descripción</span><span class="sxs-lookup"><span data-stu-id="314b7-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="314b7-214"><strong>Tipo de actividad</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-215">No</span><span class="sxs-lookup"><span data-stu-id="314b7-215">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-216">Indica si los clientes iniciaron sesión en la red interna o en la red externa cuando se realizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="314b7-216">Indicates whether the clients were logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="314b7-217">Los valores suelen ser los siguientes:</span><span class="sxs-lookup"><span data-stu-id="314b7-217">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="314b7-218">Interno</span><span class="sxs-lookup"><span data-stu-id="314b7-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="314b7-219">External</span><span class="sxs-lookup"><span data-stu-id="314b7-219">External</span></span></p></li>
<li><p><span data-ttu-id="314b7-220">Mixtos</span><span class="sxs-lookup"><span data-stu-id="314b7-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="314b7-221"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-222">No</span><span class="sxs-lookup"><span data-stu-id="314b7-222">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-223">Fecha y hora en que se ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="314b7-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="314b7-224"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-225">No</span><span class="sxs-lookup"><span data-stu-id="314b7-225">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-226">Número total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="314b7-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="314b7-227">Métricas de actividad de voz y vídeo punto a punto por servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="314b7-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="314b7-228">En la siguiente tabla se muestra la información proporcionada en el informe de voz y vídeo punto a punto para cada servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="314b7-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="314b7-229">Métricas de actividad de voz y vídeo punto a punto por servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="314b7-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="314b7-230">Nombre</span><span class="sxs-lookup"><span data-stu-id="314b7-230">Name</span></span></th>
<th><span data-ttu-id="314b7-231">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="314b7-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="314b7-232">Descripción</span><span class="sxs-lookup"><span data-stu-id="314b7-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="314b7-233"><strong>Servidor de mediación</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-234">No</span><span class="sxs-lookup"><span data-stu-id="314b7-234">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-235">Nombre del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="314b7-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="314b7-236"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-237">No</span><span class="sxs-lookup"><span data-stu-id="314b7-237">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-238">Fecha y hora en que se ha realizado la llamada.</span><span class="sxs-lookup"><span data-stu-id="314b7-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="314b7-239"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="314b7-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="314b7-240">No</span><span class="sxs-lookup"><span data-stu-id="314b7-240">No</span></span></p></td>
<td><p><span data-ttu-id="314b7-241">Número total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="314b7-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

