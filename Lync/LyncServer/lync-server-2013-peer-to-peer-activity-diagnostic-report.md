---
title: 'Lync Server 2013: informe de diagnósticos de actividad punto a punto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b72e9caec70a31280001875063cd6b7d233c500
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="6f192-102">Informe de diagnósticos de actividad punto a punto en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f192-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f192-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6f192-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6f192-104">El informe de diagnósticos de actividad punto a punto proporciona información acerca del éxito y error de sus sesiones de comunicación punto a punto.</span><span class="sxs-lookup"><span data-stu-id="6f192-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="6f192-105">Tenga en cuenta que Microsoft Lync Server 2013 distingue entre diferentes tipos de error:</span><span class="sxs-lookup"><span data-stu-id="6f192-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="6f192-106">**Error esperado**.</span><span class="sxs-lookup"><span data-stu-id="6f192-106">**Expected failure**.</span></span> <span data-ttu-id="6f192-107">Un error esperado es normalmente un error solo en el sentido más técnico.</span><span class="sxs-lookup"><span data-stu-id="6f192-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="6f192-108">Por ejemplo, supongamos que llama a alguien, pero que esta persona está fuera de la oficina y no puede responder al teléfono.</span><span class="sxs-lookup"><span data-stu-id="6f192-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="6f192-109">Dado que no se respondió la llamada, esta se considera técnicamente un error.</span><span class="sxs-lookup"><span data-stu-id="6f192-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="6f192-110">Por otra parte, se trataba de un error esperado: Microsoft Lync Server 2013 no espera que responda al teléfono si no está disponible para contestar el teléfono.</span><span class="sxs-lookup"><span data-stu-id="6f192-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="6f192-111">De la misma manera, se producirá un error inesperado si intenta enviar un mensaje instantáneo a un usuario que se encuentra fuera de línea, o ha iniciado sesión, solo en un teléfono que no admite mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="6f192-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="6f192-112">**Error inesperado**.</span><span class="sxs-lookup"><span data-stu-id="6f192-112">**Unexpected failure**.</span></span> <span data-ttu-id="6f192-113">Un error inesperado es exactamente lo que su nombre sugiere: un error que, en las circunstancias actuales, no se espera que ocurra.</span><span class="sxs-lookup"><span data-stu-id="6f192-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="6f192-114">Por ejemplo, supongamos que llama a alguien y que esa persona está disponible para responder a la llamada; sin embargo, cuando Lync Server 2013 intenta enrutar la llamada al correo de voz, se produce un error en la llamada porque se perdió la conectividad a la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="6f192-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="6f192-115">Ese es un error inesperado; esperaría que las llamadas siempre se pudieran enrutar al correo de voz.</span><span class="sxs-lookup"><span data-stu-id="6f192-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="6f192-116">Como regla general, los errores inesperados son errores verdaderos: hay problemas que probablemente no se pueden remediar a través de la capacitación del usuario o medidas similares.</span><span class="sxs-lookup"><span data-stu-id="6f192-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="6f192-p104">Tenga en cuenta que es posible que las métricas de éxito, errores esperados y errores inesperados no se sumen a la métrica de sesiones totales. Por ejemplo, en la ilustración anterior, tenemos los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="6f192-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f192-119">Operaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="6f192-119">Successes</span></span></th>
<th><span data-ttu-id="6f192-120">Errores esperados</span><span class="sxs-lookup"><span data-stu-id="6f192-120">Expected failures</span></span></th>
<th><span data-ttu-id="6f192-121">Errores inesperados</span><span class="sxs-lookup"><span data-stu-id="6f192-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="6f192-122">Total de sesiones</span><span class="sxs-lookup"><span data-stu-id="6f192-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f192-123">2024</span><span class="sxs-lookup"><span data-stu-id="6f192-123">2024</span></span></p></td>
<td><p><span data-ttu-id="6f192-124">469</span><span class="sxs-lookup"><span data-stu-id="6f192-124">469</span></span></p></td>
<td><p><span data-ttu-id="6f192-125">16 </span><span class="sxs-lookup"><span data-stu-id="6f192-125">16</span></span></p></td>
<td><p><span data-ttu-id="6f192-126">2521</span><span class="sxs-lookup"><span data-stu-id="6f192-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6f192-127">Si suma 2024 + 469 + 16, obtiene un total de 2.509 sesiones, aunque la columna Total de sesiones muestra un total de 2.521 sesiones.</span><span class="sxs-lookup"><span data-stu-id="6f192-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="6f192-128">Las 12 sesiones "que faltan" son sesiones que el sistema no puede clasificar como correctas o no correctas.</span><span class="sxs-lookup"><span data-stu-id="6f192-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="6f192-129">Esto es lo que a veces es cuando un producto de terceros presenta un nuevo código de diagnóstico que no está familiarizado con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f192-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="6f192-130">Cuando eso sucede, las llamadas realizadas usando ese producto, y la notificación de ese código de diagnóstico, no siempre se pueden clasificar como correcto, un error esperado o un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="6f192-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="6f192-131">Obtener acceso al informe de diagnósticos de actividad punto a punto</span><span class="sxs-lookup"><span data-stu-id="6f192-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="6f192-132">Al informe de diagnósticos de actividad punto a punto se obtiene acceso desde la página principal de informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="6f192-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="6f192-133">Puede obtener acceso al [Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md) haciendo clic en cualquiera de las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f192-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="6f192-134">Volumen de errores inesperados</span><span class="sxs-lookup"><span data-stu-id="6f192-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="6f192-135">Volumen de errores esperados</span><span class="sxs-lookup"><span data-stu-id="6f192-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="6f192-136">Haciendo el mejor uso del informe de diagnósticos de actividad punto a punto</span><span class="sxs-lookup"><span data-stu-id="6f192-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="6f192-p107">Hay varias maneras para poder filtrar el informe de diagnósticos de actividad punto a punto pero, de manera predeterminada, dichas opciones de filtrado está ocultas para su visión. Para ver las opciones de filtrado disponibles para usted, haga clic en el botón Mostrar u ocultar parámetros de la esquina superior derecha de la ventana de informe. Una vez haga eso, las opciones de filtrado estarán disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="6f192-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6f192-140">Filtros</span><span class="sxs-lookup"><span data-stu-id="6f192-140">Filters</span></span>

<span data-ttu-id="6f192-p108">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de diagnóstico de actividad punto a punto permite filtrar por la modalidad de sesión (por ejemplo, mensajería instantánea, transferencia de archivos o uso de aplicaciones compartidas). También se puede elegir cómo agrupar los datos. En este caso, las llamadas se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="6f192-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="6f192-145">En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de diagnóstico de actividad punto a punto.</span><span class="sxs-lookup"><span data-stu-id="6f192-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="6f192-146">Filtros del informe de diagnóstico de actividad punto a punto</span><span class="sxs-lookup"><span data-stu-id="6f192-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f192-147">Nombre</span><span class="sxs-lookup"><span data-stu-id="6f192-147">Name</span></span></th>
<th><span data-ttu-id="6f192-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f192-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f192-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-p109">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="6f192-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="6f192-152">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="6f192-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6f192-p110">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="6f192-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6f192-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6f192-155">7/7/2012</span></span></p>
<p><span data-ttu-id="6f192-156">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="6f192-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6f192-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6f192-157">7/3/2012</span></span></p>
<p><span data-ttu-id="6f192-158">Las semanas siempre empiezan en domingo y terminan en sábado.</span><span class="sxs-lookup"><span data-stu-id="6f192-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f192-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-p111">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="6f192-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="6f192-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6f192-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6f192-p112">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="6f192-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6f192-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6f192-165">7/7/2012</span></span></p>
<p><span data-ttu-id="6f192-166">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="6f192-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6f192-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6f192-167">7/3/2012</span></span></p>
<p><span data-ttu-id="6f192-168">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="6f192-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f192-169"><strong>Intervalo de</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-p113">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6f192-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6f192-172">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="6f192-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6f192-173">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="6f192-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6f192-174">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="6f192-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6f192-175">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="6f192-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="6f192-p114">Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/8/2012 y una fecha de finalización del 28/9/2012, aparecerán los datos correspondientes a los días entre el 7/8/2012 a las 12:00 horas y el 7/9/2012 a las 12:00 horas (es decir, datos para un total de 31 días).</span><span class="sxs-lookup"><span data-stu-id="6f192-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f192-178"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-p115">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6f192-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f192-182"><strong>Modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-p116">Indica el tipo de actividad de comunicación que tuvo lugar. Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f192-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6f192-185">Todos</span><span class="sxs-lookup"><span data-stu-id="6f192-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="6f192-186">Mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="6f192-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="6f192-187">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="6f192-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="6f192-188">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="6f192-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="6f192-189">Audio</span><span class="sxs-lookup"><span data-stu-id="6f192-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="6f192-190">Vídeo</span><span class="sxs-lookup"><span data-stu-id="6f192-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="6f192-191">Métricas (por modalidad)</span><span class="sxs-lookup"><span data-stu-id="6f192-191">Metrics (per modality)</span></span>

<span data-ttu-id="6f192-192">En la tabla siguiente, se muestra la información proporcionada en el informe de diagnóstico de actividad punto a punto para cada modalidad.</span><span class="sxs-lookup"><span data-stu-id="6f192-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="6f192-193">Métricas (por modalidad)</span><span class="sxs-lookup"><span data-stu-id="6f192-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f192-194">Nombre</span><span class="sxs-lookup"><span data-stu-id="6f192-194">Name</span></span></th>
<th><span data-ttu-id="6f192-195">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="6f192-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6f192-196">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f192-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f192-197"><strong>Volumen de corrección</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-198">No</span><span class="sxs-lookup"><span data-stu-id="6f192-198">No</span></span></p></td>
<td><p><span data-ttu-id="6f192-199">Número total de sesiones punto a punto correctas.</span><span class="sxs-lookup"><span data-stu-id="6f192-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f192-200"><strong>Porcentaje de corrección</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-201">No</span><span class="sxs-lookup"><span data-stu-id="6f192-201">No</span></span></p></td>
<td><p><span data-ttu-id="6f192-p117">Porcentaje de sesiones punto a punto que se completaron con problemas importantes. Se calcula dividiendo el volumen de corrección por el total de sesiones.</span><span class="sxs-lookup"><span data-stu-id="6f192-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f192-204"><strong>Volumen de errores esperados</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-205">No</span><span class="sxs-lookup"><span data-stu-id="6f192-205">No</span></span></p></td>
<td><p><span data-ttu-id="6f192-206">Número total de sesiones en las &quot;que se&quot; produjo un error esperado.</span><span class="sxs-lookup"><span data-stu-id="6f192-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="6f192-p118">Un error esperado es aquel que se prevé que vaya a producirse. Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen.</span><span class="sxs-lookup"><span data-stu-id="6f192-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f192-209"><strong>Porcentaje de errores esperados</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-210">No</span><span class="sxs-lookup"><span data-stu-id="6f192-210">No</span></span></p></td>
<td><p><span data-ttu-id="6f192-p119">Porcentaje de sesiones punto a punto que experimentaron un error esperado. Se calcula dividiendo el volumen de errores esperados por el total de sesiones.</span><span class="sxs-lookup"><span data-stu-id="6f192-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f192-213"><strong>Volumen de errores inesperados</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-214">No</span><span class="sxs-lookup"><span data-stu-id="6f192-214">No</span></span></p></td>
<td><p><span data-ttu-id="6f192-215">Número total de sesiones en las &quot;que se&quot; produjo un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="6f192-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="6f192-p120">Un error inesperado es aquel que se produce en un sistema que está aparentemente en buen estado. Por ejemplo, una llamada no debería finalizarse si el autor de la llamada está en espera. De ser así, dicha situación se identificaría como un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="6f192-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f192-219"><strong>Porcentaje de errores inesperados</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-220">No</span><span class="sxs-lookup"><span data-stu-id="6f192-220">No</span></span></p></td>
<td><p><span data-ttu-id="6f192-p121">Porcentaje de sesiones punto a punto que experimentaron un error inesperado. Se calcula dividiendo el volumen de errores inesperados por el total de sesiones.</span><span class="sxs-lookup"><span data-stu-id="6f192-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f192-223"><strong>Total de sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="6f192-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="6f192-224">No</span><span class="sxs-lookup"><span data-stu-id="6f192-224">No</span></span></p></td>
<td><p><span data-ttu-id="6f192-225">Número total de sesiones, incluidas las sesiones correctas, las sesiones con errores (tanto esperados como inesperados) y las sesiones sin categoría.</span><span class="sxs-lookup"><span data-stu-id="6f192-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

