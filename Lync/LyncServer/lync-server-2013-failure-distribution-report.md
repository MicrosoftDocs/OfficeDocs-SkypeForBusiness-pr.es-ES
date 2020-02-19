---
title: 'Lync Server 2013: informe de distribución de errores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73f7b590732b1b6f2c5010382c7c8f61038d756b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="8b739-102">Informe de distribución de errores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b739-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b739-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="8b739-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="8b739-104">El Informe de distribución de errores clasifica las sesiones con error en las categorías siguientes:</span><span class="sxs-lookup"><span data-stu-id="8b739-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="8b739-105">Motivos del diagnóstico principales</span><span class="sxs-lookup"><span data-stu-id="8b739-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="8b739-106">Modalidades principales</span><span class="sxs-lookup"><span data-stu-id="8b739-106">Top modalities</span></span>

  - <span data-ttu-id="8b739-107">Grupos principales</span><span class="sxs-lookup"><span data-stu-id="8b739-107">Top pools</span></span>

  - <span data-ttu-id="8b739-108">Fuentes principales</span><span class="sxs-lookup"><span data-stu-id="8b739-108">Top sources</span></span>

  - <span data-ttu-id="8b739-109">Componentes principales</span><span class="sxs-lookup"><span data-stu-id="8b739-109">Top components</span></span>

  - <span data-ttu-id="8b739-110">Usuarios de origen principales</span><span class="sxs-lookup"><span data-stu-id="8b739-110">Top from users</span></span>

  - <span data-ttu-id="8b739-111">Usuarios de destino principales</span><span class="sxs-lookup"><span data-stu-id="8b739-111">Top to users</span></span>

  - <span data-ttu-id="8b739-112">Agentes de usuarios de origen principales</span><span class="sxs-lookup"><span data-stu-id="8b739-112">Top from user agents</span></span>

<span data-ttu-id="8b739-p101">Puede usar estas categorías para determinar dónde se está produciendo exactamente el problema y, en determinados casos, por qué se está produciendo el problema. Por ejemplo, supongamos que ha registrado 242 sesiones de audio/vídeo con error en un día determinado. El Informe de distribución de errores puede mostrar que 237 de dichas sesiones con error tuvieron lugar en el grupo de Dublín. Esto supone un buen punto de partida para el seguimiento y el diagnóstico de las causas de dichos errores. Si hace clic en el grupo de Dublín en la categoría **Grupos principales**, verá un Informe de distribución de errores solo para dicho grupo. Desde ahí, podrá comenzar a analizar las razones por las que el grupo de Dublín tenía tantos problemas.</span><span class="sxs-lookup"><span data-stu-id="8b739-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="8b739-119">Visualización del Informe de distribución de errores</span><span class="sxs-lookup"><span data-stu-id="8b739-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="8b739-120">Puede tener acceso al Informe de distribución de errores desde cualquiera de los informes siguientes haciendo clic en la métrica **Volumen de errores esperados** o **Volumen de errores inesperados**:</span><span class="sxs-lookup"><span data-stu-id="8b739-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="8b739-121">Informe de errores principales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b739-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="8b739-122">Informe de diagnósticos de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b739-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="8b739-123">Informe de diagnósticos de actividad punto a punto en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b739-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="8b739-124">Desde el informe de distribución de errores, puede hacer clic en cualquiera de las métricas siguientes para ver el [Informe de lista de errores en Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="8b739-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="8b739-125">Motivos del diagnóstico principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="8b739-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="8b739-126">Modalidades principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="8b739-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="8b739-127">Grupos principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="8b739-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="8b739-128">Fuentes principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="8b739-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="8b739-129">Componentes principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="8b739-129">Top components (sessions)</span></span>

  - <span data-ttu-id="8b739-130">Usuarios de origen principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="8b739-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="8b739-131">Usuarios de destino principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="8b739-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="8b739-132">Agentes de usuarios de origen principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="8b739-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="8b739-133">Uso del Informe de distribución de errores</span><span class="sxs-lookup"><span data-stu-id="8b739-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="8b739-p102">Dependiendo del tamaño de su monitor y de la resolución de la pantalla, es posible que algunos de los datos del Informe de distribución de errores aparezcan truncados. Esto se produce, sobre todo, en métricas como, por ejemplo, las de los agentes de usuarios que tienen etiquetas muy largas. Por ejemplo, es posible que un agente de usuario con el nombre "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" solo se muestre de forma parcial en la pantalla:</span><span class="sxs-lookup"><span data-stu-id="8b739-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="8b739-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="8b739-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="8b739-138">Afortunadamente, basta con mantener el mouse sobre el valor truncado para ver la etiqueta completa.</span><span class="sxs-lookup"><span data-stu-id="8b739-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="8b739-p103">Una métrica interesante que puede filtrar con el Informe de distribución de errores es la del Id. de diagnóstico. Si se muestra el mismo Id. de diagnóstico en otros informes, podrá filtrar dicho Id. de diagnóstico en el Informe de distribución de errores y obtener una vista detallada del lugar exacto y la frecuencia con la que se ha informado de dicho Id. en la sesión con errores.</span><span class="sxs-lookup"><span data-stu-id="8b739-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8b739-141">Filtros</span><span class="sxs-lookup"><span data-stu-id="8b739-141">Filters</span></span>

<span data-ttu-id="8b739-p104">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de distribución de errores le permite filtrar por tipo de actividad (sesión de punto a punto o sesión de conferencias) o por el Id. de diagnóstico que contenía cada sesión con errores.</span><span class="sxs-lookup"><span data-stu-id="8b739-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="8b739-144">La siguiente tabla muestra los filtros que puede utilizar con el informe de resumen de conferencia.</span><span class="sxs-lookup"><span data-stu-id="8b739-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="8b739-145">Filtros de informes de distribución de errores</span><span class="sxs-lookup"><span data-stu-id="8b739-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b739-146">Nombre</span><span class="sxs-lookup"><span data-stu-id="8b739-146">Name</span></span></th>
<th><span data-ttu-id="8b739-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b739-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b739-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-p105">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8b739-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8b739-151">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="8b739-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8b739-p106">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="8b739-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8b739-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8b739-154">7/7/2012</span></span></p>
<p><span data-ttu-id="8b739-155">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="8b739-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8b739-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8b739-156">7/3/2012</span></span></p>
<p><span data-ttu-id="8b739-157">Las semanas siempre empiezan en domingo y terminan en sábado.</span><span class="sxs-lookup"><span data-stu-id="8b739-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b739-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-p107">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8b739-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8b739-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8b739-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8b739-p108">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="8b739-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8b739-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8b739-164">7/7/2012</span></span></p>
<p><span data-ttu-id="8b739-165">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="8b739-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8b739-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8b739-166">7/3/2012</span></span></p>
<p><span data-ttu-id="8b739-167">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="8b739-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b739-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-p109">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral. Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos. Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8b739-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b739-172"><strong>Tipo de actividad</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-p110">Tipo de actividad para filtrar. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8b739-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b739-175">Todos</span><span class="sxs-lookup"><span data-stu-id="8b739-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="8b739-176">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="8b739-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="8b739-177">Conversación</span><span class="sxs-lookup"><span data-stu-id="8b739-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b739-178"><strong>Categoría de sesión</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-p111">Indica si la actividad correspondiente se desarrolló correctamente o causó errores. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8b739-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b739-181">Todos</span><span class="sxs-lookup"><span data-stu-id="8b739-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="8b739-182">Success</span><span class="sxs-lookup"><span data-stu-id="8b739-182">Success</span></span></p></li>
<li><p><span data-ttu-id="8b739-183">Error esperado</span><span class="sxs-lookup"><span data-stu-id="8b739-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="8b739-184">Error inesperado</span><span class="sxs-lookup"><span data-stu-id="8b739-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="8b739-185">Un &quot;error esperado&quot; es un error que se espera que suceda.</span><span class="sxs-lookup"><span data-stu-id="8b739-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="8b739-186">Por ejemplo, si un usuario ha establecido su estado en No molestar, se espera que las llamadas a ese usuario no se realicen.</span><span class="sxs-lookup"><span data-stu-id="8b739-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="8b739-187">Un &quot;error&quot; inesperado es un error que se produce en lo que parecería ser un sistema en mal estado.</span><span class="sxs-lookup"><span data-stu-id="8b739-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="8b739-188">Por ejemplo, una llamada no debería finalizarse si el autor de la llamada está en espera.</span><span class="sxs-lookup"><span data-stu-id="8b739-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="8b739-189">De ser así, tal cosa se identificaría como un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="8b739-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b739-190"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-p113">Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</span><span class="sxs-lookup"><span data-stu-id="8b739-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="8b739-193">Métricas para motivos del diagnóstico destacados</span><span class="sxs-lookup"><span data-stu-id="8b739-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="8b739-194">La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en el Id. de diagnóstico que aparece con mayor frecuencia.</span><span class="sxs-lookup"><span data-stu-id="8b739-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="8b739-195">Métricas para motivos del diagnóstico destacados</span><span class="sxs-lookup"><span data-stu-id="8b739-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b739-196">Nombre</span><span class="sxs-lookup"><span data-stu-id="8b739-196">Name</span></span></th>
<th><span data-ttu-id="8b739-197">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="8b739-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8b739-198">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b739-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b739-199"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-200">No</span><span class="sxs-lookup"><span data-stu-id="8b739-200">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-p114">Clasificación relativa de sesiones con errores basándose en los Id. de diagnóstico. El Id. de diagnóstico es un identificador único (con el formato de un encabezado de diagnóstico MS) adjunto a un mensaje SIP que suele proporcionar información útil para resolver errores.</span><span class="sxs-lookup"><span data-stu-id="8b739-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b739-203"><strong>Principales motivos de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-204">No</span><span class="sxs-lookup"><span data-stu-id="8b739-204">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-205">Id. de diagnóstico generado en una sesión.</span><span class="sxs-lookup"><span data-stu-id="8b739-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b739-206"><strong>Sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-207">No</span><span class="sxs-lookup"><span data-stu-id="8b739-207">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-208">Número total de sesiones con errores en las que generó el Id. de diagnóstico especificado.</span><span class="sxs-lookup"><span data-stu-id="8b739-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="8b739-209">Métricas para modalidades destacadas</span><span class="sxs-lookup"><span data-stu-id="8b739-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="8b739-210">La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en las modalidades de sesiones que experimentaron más errores.</span><span class="sxs-lookup"><span data-stu-id="8b739-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="8b739-211">Métricas para modalidades destacadas</span><span class="sxs-lookup"><span data-stu-id="8b739-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b739-212">Nombre</span><span class="sxs-lookup"><span data-stu-id="8b739-212">Name</span></span></th>
<th><span data-ttu-id="8b739-213">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="8b739-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8b739-214">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b739-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b739-215"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-216">No</span><span class="sxs-lookup"><span data-stu-id="8b739-216">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-217">Clasificación relativa de sesiones con errores basándose en los tipos de sesiones (por ejemplo, una conferencia de audio o vídeo o una sesión de transferencia de archivos de punto a punto).</span><span class="sxs-lookup"><span data-stu-id="8b739-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b739-218"><strong>Principales modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-219">No</span><span class="sxs-lookup"><span data-stu-id="8b739-219">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-220">Tipo de sesión.</span><span class="sxs-lookup"><span data-stu-id="8b739-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b739-221"><strong>Sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-222">No</span><span class="sxs-lookup"><span data-stu-id="8b739-222">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-223">Número total de sesiones con errores en las que aparece la modalidad especificada.</span><span class="sxs-lookup"><span data-stu-id="8b739-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="8b739-224">Métricas para grupos destacados</span><span class="sxs-lookup"><span data-stu-id="8b739-224">Metrics for Top Pools</span></span>

<span data-ttu-id="8b739-225">La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los grupos de servidores que experimentaron más errores.</span><span class="sxs-lookup"><span data-stu-id="8b739-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="8b739-226">Métricas para grupos destacados</span><span class="sxs-lookup"><span data-stu-id="8b739-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b739-227">Nombre</span><span class="sxs-lookup"><span data-stu-id="8b739-227">Name</span></span></th>
<th><span data-ttu-id="8b739-228">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="8b739-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8b739-229">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b739-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b739-230"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-231">No</span><span class="sxs-lookup"><span data-stu-id="8b739-231">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-232">Clasificación relativa de sesiones con errores basándose en el grupo de registradores o servidor perimetral en el que se realizó la sesión.</span><span class="sxs-lookup"><span data-stu-id="8b739-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b739-233"><strong>Principales grupos de servidores</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-234">No</span><span class="sxs-lookup"><span data-stu-id="8b739-234">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-235">Nombre del grupo de registrador o servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="8b739-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b739-236"><strong>Sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-237">No</span><span class="sxs-lookup"><span data-stu-id="8b739-237">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-238">Número total de sesiones con errores por grupo de registrador o servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="8b739-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="8b739-239">Métricas para fuentes destacadas</span><span class="sxs-lookup"><span data-stu-id="8b739-239">Metrics for Top Sources</span></span>

<span data-ttu-id="8b739-240">La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los equipos que experimentaron más errores.</span><span class="sxs-lookup"><span data-stu-id="8b739-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="8b739-241">Métricas para fuentes destacadas</span><span class="sxs-lookup"><span data-stu-id="8b739-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b739-242">Nombre</span><span class="sxs-lookup"><span data-stu-id="8b739-242">Name</span></span></th>
<th><span data-ttu-id="8b739-243">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="8b739-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8b739-244">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b739-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b739-245"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-246">No</span><span class="sxs-lookup"><span data-stu-id="8b739-246">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-247">Clasificación relativa de sesiones con errores por equipo.</span><span class="sxs-lookup"><span data-stu-id="8b739-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b739-248"><strong>Principales fuentes</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-249">No</span><span class="sxs-lookup"><span data-stu-id="8b739-249">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-250">Nombre del equipo que participó en la sesión con errores.</span><span class="sxs-lookup"><span data-stu-id="8b739-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b739-251"><strong>Sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-252">No</span><span class="sxs-lookup"><span data-stu-id="8b739-252">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-253">Número total de sesiones con errores por equipo.</span><span class="sxs-lookup"><span data-stu-id="8b739-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="8b739-254">Métricas para componentes destacados</span><span class="sxs-lookup"><span data-stu-id="8b739-254">Metrics for Top Components</span></span>

<span data-ttu-id="8b739-255">En la siguiente tabla se muestra la información proporcionada en el informe de distribución de errores en función de los componentes de Microsoft Lync Server 2010 que experimentaron más errores.</span><span class="sxs-lookup"><span data-stu-id="8b739-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="8b739-256">Métricas para componentes destacados</span><span class="sxs-lookup"><span data-stu-id="8b739-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b739-257">Nombre</span><span class="sxs-lookup"><span data-stu-id="8b739-257">Name</span></span></th>
<th><span data-ttu-id="8b739-258">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="8b739-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8b739-259">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b739-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b739-260"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-261">No</span><span class="sxs-lookup"><span data-stu-id="8b739-261">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-262">Clasificación relativa de sesiones con errores basadas en el componente 2010 de Lync Server (por ejemplo, ExumRouting, GroupChat o MediationServer).</span><span class="sxs-lookup"><span data-stu-id="8b739-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b739-263"><strong>Principales componentes</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-264">No</span><span class="sxs-lookup"><span data-stu-id="8b739-264">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-265">Nombre del componente que participó en la sesión con errores.</span><span class="sxs-lookup"><span data-stu-id="8b739-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b739-266"><strong>Sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-267">No</span><span class="sxs-lookup"><span data-stu-id="8b739-267">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-268">Número total de sesiones con errores por componente.</span><span class="sxs-lookup"><span data-stu-id="8b739-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="8b739-269">Métricas para usuarios destacados</span><span class="sxs-lookup"><span data-stu-id="8b739-269">Metrics for Top From Users</span></span>

<span data-ttu-id="8b739-270">La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los usuarios que experimentaron más errores al intentar llamar a otra persona (denominados remitentes).</span><span class="sxs-lookup"><span data-stu-id="8b739-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="8b739-271">Métricas para usuarios destacados</span><span class="sxs-lookup"><span data-stu-id="8b739-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b739-272">Nombre</span><span class="sxs-lookup"><span data-stu-id="8b739-272">Name</span></span></th>
<th><span data-ttu-id="8b739-273">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="8b739-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8b739-274">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b739-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b739-275"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-276">No</span><span class="sxs-lookup"><span data-stu-id="8b739-276">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-277">Clasificación relativa de sesiones con errores basándose en el usuario invitado a unirse a la sesión.</span><span class="sxs-lookup"><span data-stu-id="8b739-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b739-278"><strong>Principales remitentes</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-279">No</span><span class="sxs-lookup"><span data-stu-id="8b739-279">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-280">Dirección SIP del usuario invitado a unirse a la sesión.</span><span class="sxs-lookup"><span data-stu-id="8b739-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b739-281"><strong>Sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-282">No</span><span class="sxs-lookup"><span data-stu-id="8b739-282">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-283">Cantidad total de sesiones con error por usuario.</span><span class="sxs-lookup"><span data-stu-id="8b739-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="8b739-284">Métricas para principales destinatarios</span><span class="sxs-lookup"><span data-stu-id="8b739-284">Metrics for Top To Users</span></span>

<span data-ttu-id="8b739-285">La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en los usuarios que experimentaron más errores cuando otro usuario intentó llamarlos (denominados destinatarios).</span><span class="sxs-lookup"><span data-stu-id="8b739-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b739-286">Nombre</span><span class="sxs-lookup"><span data-stu-id="8b739-286">Name</span></span></th>
<th><span data-ttu-id="8b739-287">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="8b739-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8b739-288">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b739-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b739-289"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-290">No</span><span class="sxs-lookup"><span data-stu-id="8b739-290">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-291">Clasificación relativa de sesiones con errores basándose en el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="8b739-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b739-292"><strong>Principales destinatarios</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-293">No</span><span class="sxs-lookup"><span data-stu-id="8b739-293">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-294">Dirección SIP del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="8b739-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b739-295"><strong>Sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-296">No</span><span class="sxs-lookup"><span data-stu-id="8b739-296">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-297">Cantidad total de sesiones con error por usuario.</span><span class="sxs-lookup"><span data-stu-id="8b739-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="8b739-298">Métricas para agentes de usuario destacados</span><span class="sxs-lookup"><span data-stu-id="8b739-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="8b739-299">La siguiente tabla enumera la información proporcionada en el informe de distribución de errores basándose en el software extremo que experimentó más errores.</span><span class="sxs-lookup"><span data-stu-id="8b739-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="8b739-300">Métricas para agentes de usuario destacados</span><span class="sxs-lookup"><span data-stu-id="8b739-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b739-301">Nombre</span><span class="sxs-lookup"><span data-stu-id="8b739-301">Name</span></span></th>
<th><span data-ttu-id="8b739-302">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="8b739-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8b739-303">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b739-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b739-304"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-305">No</span><span class="sxs-lookup"><span data-stu-id="8b739-305">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-p115">Clasificación relativa de sesiones con errores basándose en el agente de usuario (software) que participa en la sesión. Por ejemplo: RTCC/4.0.0.0 Enrutamiento de entrada/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="8b739-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b739-308"><strong>Principales agentes de usuario</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-309">No</span><span class="sxs-lookup"><span data-stu-id="8b739-309">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-310">Nombre del agente de usuario que participó en la sesión con errores.</span><span class="sxs-lookup"><span data-stu-id="8b739-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b739-311"><strong>Sesiones</strong></span><span class="sxs-lookup"><span data-stu-id="8b739-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b739-312">No</span><span class="sxs-lookup"><span data-stu-id="8b739-312">No</span></span></p></td>
<td><p><span data-ttu-id="8b739-313">Número total de sesiones con errores por agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="8b739-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

