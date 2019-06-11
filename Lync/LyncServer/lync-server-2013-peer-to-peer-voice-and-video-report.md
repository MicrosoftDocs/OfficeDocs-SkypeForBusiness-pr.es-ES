---
title: 'Lync Server 2013: informe de voz y vídeo de punto a punto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b938a5281717528143cfc077a42f51bd68f69bae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="1b7cc-102">Informe de voz y vídeo de punto a punto en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b7cc-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b7cc-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="1b7cc-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="1b7cc-p101">El Informe de voz y vídeo punto a punto da una visión detallada de la distribución de las llamadas de voz y de las videollamadas en un período de tiempo especificado (por ejemplo, llamadas por hora o llamadas por día). El informe también da la opción de visualizar todas las llamadas de voz y videollamadas que se efectuaron, o de visualizar únicamente las llamadas correctas o las erróneas. Los informes muestran la información de las llamadas desglosadas en las agrupaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="1b7cc-107">Llamadas por grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="1b7cc-107">Calls per pool</span></span>

  - <span data-ttu-id="1b7cc-108">Llamadas por tipo de llamada (por ejemplo, una llamada de Lync a Lync, una llamada de Lync a una persona en la red RTC)</span><span class="sxs-lookup"><span data-stu-id="1b7cc-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="1b7cc-109">Llamadas por tipo de acceso (los usuarios que iniciaron sesión en la red interna comparados con los usuarios que iniciaron sesión en la red externa)</span><span class="sxs-lookup"><span data-stu-id="1b7cc-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="1b7cc-110">Llamadas por servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="1b7cc-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="1b7cc-111">Para obtener acceso al informe de voz y vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="1b7cc-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="1b7cc-112">Obtenga acceso al informe de voz y vídeo punto a punto abriendo el Informe de resumen de actividad punto a punto y haciendo clic en una de las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="1b7cc-113">Total de sesiones de audio punto a punto</span><span class="sxs-lookup"><span data-stu-id="1b7cc-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="1b7cc-114">Total de minutos de audio punto a punto</span><span class="sxs-lookup"><span data-stu-id="1b7cc-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="1b7cc-115">Total de sesiones de vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="1b7cc-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="1b7cc-116">Total de minutos de vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="1b7cc-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="1b7cc-117">Para sacar el máximo provecho del informe de voz y vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="1b7cc-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="1b7cc-p102">Existen varias formas de filtrar el informe de voz y vídeo punto a punto. No obstante, normalmente esas opciones de filtrado están ocultas a la vista. Para ver las opciones de filtrado que tiene disponibles, haga clic en el botón **Mostrar u ocultar parámetros** en la esquina superior derecha de la ventana del informe.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1b7cc-121">Filtros</span><span class="sxs-lookup"><span data-stu-id="1b7cc-121">Filters</span></span>

<span data-ttu-id="1b7cc-p103">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos de diferentes formas. En la siguiente tabla se enumeran los filtros que puede utilizar con el informe de voz y vídeo punto a punto.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="1b7cc-124">Filtros del informe de voz y vídeo punto a punto</span><span class="sxs-lookup"><span data-stu-id="1b7cc-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b7cc-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="1b7cc-125">Name</span></span></th>
<th><span data-ttu-id="1b7cc-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b7cc-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b7cc-127"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-p104">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1b7cc-130">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1b7cc-p105">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1b7cc-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1b7cc-133">7/7/2012</span></span></p>
<p><span data-ttu-id="1b7cc-134">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="1b7cc-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1b7cc-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1b7cc-135">7/3/2012</span></span></p>
<p><span data-ttu-id="1b7cc-136">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7cc-137"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-p106">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1b7cc-140">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1b7cc-p107">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1b7cc-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1b7cc-143">7/7/2012</span></span></p>
<p><span data-ttu-id="1b7cc-144">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="1b7cc-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1b7cc-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1b7cc-145">7/3/2012</span></span></p>
<p><span data-ttu-id="1b7cc-146">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7cc-147"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-p108">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b7cc-150">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="1b7cc-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-151">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="1b7cc-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-152">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="1b7cc-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-153">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="1b7cc-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="1b7cc-154">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio).</span><span class="sxs-lookup"><span data-stu-id="1b7cc-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="1b7cc-155">Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="1b7cc-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7cc-156"><strong>Tipo de medio</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-p110">Indica el tipo de medio utilizado en la sesión. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b7cc-159">Both</span><span class="sxs-lookup"><span data-stu-id="1b7cc-159">Both</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-160">Audio</span><span class="sxs-lookup"><span data-stu-id="1b7cc-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-161">Vídeo</span><span class="sxs-lookup"><span data-stu-id="1b7cc-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7cc-162"><strong>Disposición de llamada</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-p111">Indica el resultado de la sesión. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b7cc-165">[Todas]</span><span class="sxs-lookup"><span data-stu-id="1b7cc-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-166">Llamadas correctas</span><span class="sxs-lookup"><span data-stu-id="1b7cc-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-167">Llamadas con error</span><span class="sxs-lookup"><span data-stu-id="1b7cc-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7cc-168"><strong>Informe por</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-p112">Indica los valores a utilizar en el informe. Seleccione una opción de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b7cc-171">Recuento de sesiones</span><span class="sxs-lookup"><span data-stu-id="1b7cc-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-172">Minutos de la llamada</span><span class="sxs-lookup"><span data-stu-id="1b7cc-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="1b7cc-173">Métricas de actividad de voz y vídeo punto a punto por grupo</span><span class="sxs-lookup"><span data-stu-id="1b7cc-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="1b7cc-174">En la siguiente tabla se enumera la información provista en el Informe de voz y vídeo punto a punto para cada grupo.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="1b7cc-175">Métricas de actividad de voz y vídeo punto a punto por grupo</span><span class="sxs-lookup"><span data-stu-id="1b7cc-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b7cc-176">Nombre</span><span class="sxs-lookup"><span data-stu-id="1b7cc-176">Name</span></span></th>
<th><span data-ttu-id="1b7cc-177">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="1b7cc-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1b7cc-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b7cc-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b7cc-179"><strong>Grupo de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-180">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-180">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-181">Nombre del grupo de registradores o del servidor perimetral usado para la llamada.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7cc-182"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-183">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-183">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-184">Fecha/hora en que se produjo la llamada.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7cc-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-186">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-186">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-187">Cantidad total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="1b7cc-188">Métricas de actividad de voz y vídeo punto a punto por tipo de llamada</span><span class="sxs-lookup"><span data-stu-id="1b7cc-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="1b7cc-189">En la siguiente tabla se enumera la información proporcionada en el Informe de voz y vídeo punto a punto para cada tipo de llamada realizada.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="1b7cc-190">Métricas de actividad de voz y vídeo punto a punto por tipo de llamada</span><span class="sxs-lookup"><span data-stu-id="1b7cc-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b7cc-191">Nombre</span><span class="sxs-lookup"><span data-stu-id="1b7cc-191">Name</span></span></th>
<th><span data-ttu-id="1b7cc-192">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="1b7cc-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1b7cc-193">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b7cc-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b7cc-194"><strong>Tipo de llamada</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-195">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-195">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-p113">Indica el tipo de llamada que se realizó. Los valores son uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b7cc-198">UC-a-UC</span><span class="sxs-lookup"><span data-stu-id="1b7cc-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-199">UC-a-PSTN</span><span class="sxs-lookup"><span data-stu-id="1b7cc-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-200">PSTN-a-UC</span><span class="sxs-lookup"><span data-stu-id="1b7cc-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-201">PSTN-a-PSTN</span><span class="sxs-lookup"><span data-stu-id="1b7cc-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7cc-202"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-203">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-203">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-204">Fecha/hora en que se produjo la llamada.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7cc-205"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-206">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-206">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-207">Cantidad total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="1b7cc-208">Métricas de actividad de voz y vídeo punto a punto por tipo de acceso</span><span class="sxs-lookup"><span data-stu-id="1b7cc-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="1b7cc-209">En la siguiente tabla se enumera la información proporcionada en el Informe de voz y vídeo punto a punto para cada tipo de acceso a la red.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="1b7cc-210">Métricas de actividad de voz y vídeo punto a punto por tipo de acceso</span><span class="sxs-lookup"><span data-stu-id="1b7cc-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b7cc-211">Nombre</span><span class="sxs-lookup"><span data-stu-id="1b7cc-211">Name</span></span></th>
<th><span data-ttu-id="1b7cc-212">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="1b7cc-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1b7cc-213">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b7cc-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b7cc-214"><strong>Tipo de actividad</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-215">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-215">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-p114">Indica si los clientes habían iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Generalmente, los valores son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1b7cc-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b7cc-218">Interna</span><span class="sxs-lookup"><span data-stu-id="1b7cc-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-219">Externa</span><span class="sxs-lookup"><span data-stu-id="1b7cc-219">External</span></span></p></li>
<li><p><span data-ttu-id="1b7cc-220">Mixta</span><span class="sxs-lookup"><span data-stu-id="1b7cc-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7cc-221"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-222">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-222">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-223">Fecha/hora en que se produjo la llamada.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7cc-224"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-225">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-225">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-226">Cantidad total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="1b7cc-227">Métricas de actividad de voz y vídeo punto a punto por servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="1b7cc-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="1b7cc-228">En la siguiente tabla se enumera la información proporcionada en el informe de voz y vídeo de punto a punto para cada servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="1b7cc-229">Métricas de actividad de voz y vídeo punto a punto por servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="1b7cc-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b7cc-230">Nombre</span><span class="sxs-lookup"><span data-stu-id="1b7cc-230">Name</span></span></th>
<th><span data-ttu-id="1b7cc-231">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="1b7cc-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1b7cc-232">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b7cc-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b7cc-233"><strong>Servidor de mediación</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-234">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-234">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-235">Nombre del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7cc-236"><strong>Fecha y hora</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-237">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-237">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-238">Fecha/hora en que se produjo la llamada.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7cc-239"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1b7cc-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1b7cc-240">No</span><span class="sxs-lookup"><span data-stu-id="1b7cc-240">No</span></span></p></td>
<td><p><span data-ttu-id="1b7cc-241">Cantidad total de sesiones o recuento total de mensajes.</span><span class="sxs-lookup"><span data-stu-id="1b7cc-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

