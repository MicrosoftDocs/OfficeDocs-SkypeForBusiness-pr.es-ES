---
title: 'Lync Server 2013: informe de lista de llamadas de grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abb3a1b13bf7357a0a2ee31180557911fc37ae0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511767"
---
# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="dc930-102">Informe de lista de llamadas de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc930-102">Response Group Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc930-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="dc930-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="dc930-104">La aplicación de grupo de respuesta ofrece una forma de que Microsoft Lync Server 2013 responda y enrute llamadas telefónicas en función del número marcado y, opcionalmente, de las respuestas del autor de la llamada a una serie de preguntas.</span><span class="sxs-lookup"><span data-stu-id="dc930-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="dc930-105">Normalmente, las llamadas de grupo de respuesta no se enrutan a una persona individual pero, en su lugar, se redirigen a un equipo de personas a las que se hace referencia como grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="dc930-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="dc930-106">Por ejemplo, si alguien llama al número de teléfono de su Departamento de soporte técnico, Lync Server 2013 puede enrutar automáticamente esa llamada al primer agente del Departamento de soporte disponible.</span><span class="sxs-lookup"><span data-stu-id="dc930-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="dc930-107">Como alternativa, Lync Server podría formular una serie de preguntas ("Presione 1 si tiene problemas de hardware.</span><span class="sxs-lookup"><span data-stu-id="dc930-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="dc930-108">Presione 2 Si tiene problemas de software.</span><span class="sxs-lookup"><span data-stu-id="dc930-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="dc930-109">Presione 3 Si tiene problemas de red. ") y luego enrutar la llamada al representante del Departamento de soporte técnico más adecuado en función de la respuesta a esas preguntas.</span><span class="sxs-lookup"><span data-stu-id="dc930-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="dc930-110">El informe de lista de llamadas de grupo de respuesta representa una colección de llamadas realizadas para un período de tiempo especificado y para un tipo de llamada especificado.</span><span class="sxs-lookup"><span data-stu-id="dc930-110">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call.</span></span> <span data-ttu-id="dc930-111">El informe de uso del grupo de respuesta (que debe abrirse primero para poder abrir el informe de lista de llamadas de grupo de respuesta) reconoce los siguientes tipos de llamadas:</span><span class="sxs-lookup"><span data-stu-id="dc930-111">The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="dc930-112">**Llamadas recibidas**.</span><span class="sxs-lookup"><span data-stu-id="dc930-112">**Received calls**.</span></span> <span data-ttu-id="dc930-113">Número total de llamadas recibidas por todas las instancias de la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dc930-113">Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="dc930-114">**Llamadas correctas**.</span><span class="sxs-lookup"><span data-stu-id="dc930-114">**Successful calls**.</span></span> <span data-ttu-id="dc930-115">Número total de llamadas que ha seleccionado la aplicación grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dc930-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="dc930-p105">**Llamadas ofrecidas**. Número total de llamadas transferidas a un agente de Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dc930-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="dc930-p106">**Llamadas contestadas**. Número total de llamadas contestadas realmente por un agente de Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dc930-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="dc930-120">Porcentaje de llamadas abandonadas.</span><span class="sxs-lookup"><span data-stu-id="dc930-120">Percentage of abandoned calls.</span></span> <span data-ttu-id="dc930-121">Porcentaje de llamadas recibidas por la aplicación Grupo de respuesta que nunca contestó un agente.</span><span class="sxs-lookup"><span data-stu-id="dc930-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="dc930-122">Este valor se calcula restando las llamadas contestadas a las llamadas recibidas y, a continuación, dividiendo el valor obtenido entre el número de Llamadas recibidas.</span><span class="sxs-lookup"><span data-stu-id="dc930-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="dc930-123">Por ejemplo, si se han recibido 10 llamadas y 7 no se contestaron, debe restar 7 a 10, lo que da un resultado de 3 llamadas no respondidas.</span><span class="sxs-lookup"><span data-stu-id="dc930-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="dc930-124">A continuación, dicho valor se divide entre 10, con lo que obtiene un porcentaje de llamadas abandonadas del 30%.</span><span class="sxs-lookup"><span data-stu-id="dc930-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="dc930-125">**Llamadas transferidas**.</span><span class="sxs-lookup"><span data-stu-id="dc930-125">**Transferred calls**.</span></span> <span data-ttu-id="dc930-126">Número total de llamadas de Grupo de repuesta transferidas porque se agotó un tiempo de espera de cola o porque una cola está desbordada.</span><span class="sxs-lookup"><span data-stu-id="dc930-126">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="dc930-127">Acceso al informe de lista de llamadas de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="dc930-127">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="dc930-128">Solo se puede tener acceso al informe de lista de llamadas de grupo de respuesta haciendo clic en una de las siguientes métricas del [Informe de uso del grupo de respuesta en Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span><span class="sxs-lookup"><span data-stu-id="dc930-128">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="dc930-129">Llamadas recibidas</span><span class="sxs-lookup"><span data-stu-id="dc930-129">Received calls</span></span>

  - <span data-ttu-id="dc930-130">Llamadas correctas</span><span class="sxs-lookup"><span data-stu-id="dc930-130">Successful calls</span></span>

  - <span data-ttu-id="dc930-131">Llamadas ofrecidas</span><span class="sxs-lookup"><span data-stu-id="dc930-131">Offered calls</span></span>

  - <span data-ttu-id="dc930-132">Llamadas contestadas</span><span class="sxs-lookup"><span data-stu-id="dc930-132">Answered calls</span></span>

  - <span data-ttu-id="dc930-133">Llamadas transferidas</span><span class="sxs-lookup"><span data-stu-id="dc930-133">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="dc930-134">Aprovechar al máximo el informe de lista de llamadas de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="dc930-134">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="dc930-135">El informe de lista de llamadas de grupo de respuesta le permite limitar los datos que se muestran a llamadas que impliquen a un flujo de trabajo determinado del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dc930-135">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow.</span></span> <span data-ttu-id="dc930-136">Para ello, debe especificar el URI del flujo de trabajo (dirección SIP del flujo de trabajo) en el cuadro URI del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dc930-136">To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box.</span></span> <span data-ttu-id="dc930-137">Sin embargo, antes de poder hacerlo, debe poder ver el cuadro URI de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dc930-137">Before you can do that, however, you must actually be able to see the Workflow URI box.</span></span> <span data-ttu-id="dc930-138">Para mostrar las opciones de filtrado del informe de lista de llamadas de grupo de respuesta, haga clic en el botón Mostrar u ocultar parámetros en la parte superior izquierda de la ventana del informe.</span><span class="sxs-lookup"><span data-stu-id="dc930-138">To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="dc930-139">Tenga en cuenta que la lista de llamadas de grupo de respuesta no muestra información sobre el código de respuesta o el identificador de diagnóstico si mantiene el mouse sobre cualquiera de esas métricas.</span><span class="sxs-lookup"><span data-stu-id="dc930-139">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="dc930-140">Si necesita más información, puede anotar el código de respuesta o el identificador de diagnóstico y, a continuación, buscar esos valores en el [Informe de errores principales en Lync Server 2013](lync-server-2013-top-failures-report.md).</span><span class="sxs-lookup"><span data-stu-id="dc930-140">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="dc930-141">una pregunta como esta: "¿qué flujo de trabajo individual recibió más llamadas?", puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc930-141">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="dc930-142">En el informe de uso del grupo de respuesta, establezca el período de tiempo deseado y, a continuación, haga clic en la métrica llamadas recibidas.</span><span class="sxs-lookup"><span data-stu-id="dc930-142">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric.</span></span> <span data-ttu-id="dc930-143">Se abrirá el informe de lista de llamadas de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dc930-143">That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="dc930-144">Exportar los datos que se muestran en el informe de lista de llamadas de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dc930-144">Export the data shown on the Response Group Call List Report.</span></span> <span data-ttu-id="dc930-145">Por ejemplo, puede exportar los datos en formato de Microsoft Excel y, a continuación, usar Excel para convertir los datos en un archivo de valores separados por comas.</span><span class="sxs-lookup"><span data-stu-id="dc930-145">For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="dc930-146">Ejecute los análisis con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc930-146">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="dc930-147">Por ejemplo, si ha guardado los datos en un archivo denominado C: \\ \\ \_ lista de llamadas de grupo de respuesta \_ de datos \_ \_Report.csv, puede usar el siguiente comando para devolver el número total de llamadas recibidas para cada flujo de trabajo que aparece en el informe:</span><span class="sxs-lookup"><span data-stu-id="dc930-147">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="dc930-148">Esta información será similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc930-148">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="dc930-149">Filtros</span><span class="sxs-lookup"><span data-stu-id="dc930-149">Filters</span></span>

<span data-ttu-id="dc930-150">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas.</span><span class="sxs-lookup"><span data-stu-id="dc930-150">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="dc930-151">En la siguiente tabla se enumeran los filtros que se pueden usar con el informe de lista de llamadas de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dc930-151">The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="dc930-152">Filtros del informe de lista de llamadas de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="dc930-152">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc930-153">Nombre</span><span class="sxs-lookup"><span data-stu-id="dc930-153">Name</span></span></th>
<th><span data-ttu-id="dc930-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc930-154">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc930-155"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="dc930-155"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="dc930-p114">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="dc930-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="dc930-158">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dc930-158">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dc930-p115">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="dc930-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dc930-161">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dc930-161">7/7/2012</span></span></p>
<p><span data-ttu-id="dc930-162">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="dc930-162">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dc930-163">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dc930-163">7/3/2012</span></span></p>
<p><span data-ttu-id="dc930-164">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="dc930-164">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc930-165"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="dc930-165"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="dc930-p116">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="dc930-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="dc930-168">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dc930-168">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dc930-p117">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="dc930-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dc930-171">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dc930-171">7/7/2012</span></span></p>
<p><span data-ttu-id="dc930-172">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="dc930-172">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dc930-173">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dc930-173">7/3/2012</span></span></p>
<p><span data-ttu-id="dc930-174">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="dc930-174">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc930-175"><strong>URI de flujo de trabajo</strong></span><span class="sxs-lookup"><span data-stu-id="dc930-175"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="dc930-p118">Permite limitar los datos devueltos al flujo de trabajo de grupo de respuesta especificado. Para usar este filtro, escriba la dirección SIP del grupo de trabajo. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dc930-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="dc930-179">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dc930-179">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc930-180"><strong>Llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="dc930-180"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="dc930-181">Puede seleccionar uno de los siguientes tipos de llamada:</span><span class="sxs-lookup"><span data-stu-id="dc930-181">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc930-182">Llamadas recibidas</span><span class="sxs-lookup"><span data-stu-id="dc930-182">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="dc930-183">Llamadas correctas</span><span class="sxs-lookup"><span data-stu-id="dc930-183">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="dc930-184">Llamadas ofrecidas</span><span class="sxs-lookup"><span data-stu-id="dc930-184">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="dc930-185">Llamadas respondidas</span><span class="sxs-lookup"><span data-stu-id="dc930-185">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="dc930-186">Llamadas transferidas</span><span class="sxs-lookup"><span data-stu-id="dc930-186">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="dc930-187">Métricas</span><span class="sxs-lookup"><span data-stu-id="dc930-187">Metrics</span></span>

<span data-ttu-id="dc930-188">En la siguiente tabla se muestra la información proporcionada en el informe de lista de llamadas de grupo de respuesta para cada llamada recibida por la aplicación grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dc930-188">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="dc930-189">Métricas del informe de lista de llamadas de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="dc930-189">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc930-190">Nombre</span><span class="sxs-lookup"><span data-stu-id="dc930-190">Name</span></span></th>
<th><span data-ttu-id="dc930-191">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="dc930-191">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dc930-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc930-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc930-193"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="dc930-193"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="dc930-194">No</span><span class="sxs-lookup"><span data-stu-id="dc930-194">No</span></span></p></td>
<td><p><span data-ttu-id="dc930-195">Dirección SIP del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="dc930-195">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc930-196"><strong>Flujo de trabajo</strong></span><span class="sxs-lookup"><span data-stu-id="dc930-196"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="dc930-197">No</span><span class="sxs-lookup"><span data-stu-id="dc930-197">No</span></span></p></td>
<td><p><span data-ttu-id="dc930-198">Dirección SIP del flujo de trabajo del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dc930-198">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc930-199"><strong>Hora de comienzo</strong></span><span class="sxs-lookup"><span data-stu-id="dc930-199"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="dc930-200">No</span><span class="sxs-lookup"><span data-stu-id="dc930-200">No</span></span></p></td>
<td><p><span data-ttu-id="dc930-201">Fecha y hora en que se inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="dc930-201">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc930-202"><strong>Hora de finalización</strong></span><span class="sxs-lookup"><span data-stu-id="dc930-202"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="dc930-203">No</span><span class="sxs-lookup"><span data-stu-id="dc930-203">No</span></span></p></td>
<td><p><span data-ttu-id="dc930-204">Fecha y hora en que finalizó la llamada.</span><span class="sxs-lookup"><span data-stu-id="dc930-204">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc930-205"><strong>Código de respuesta</strong></span><span class="sxs-lookup"><span data-stu-id="dc930-205"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="dc930-206">No</span><span class="sxs-lookup"><span data-stu-id="dc930-206">No</span></span></p></td>
<td><p><span data-ttu-id="dc930-207">Código de respuesta SIP enviado cuando se produjo un error en la sesión.</span><span class="sxs-lookup"><span data-stu-id="dc930-207">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc930-208"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="dc930-208"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="dc930-209">No</span><span class="sxs-lookup"><span data-stu-id="dc930-209">No</span></span></p></td>
<td><p><span data-ttu-id="dc930-210">Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.</span><span class="sxs-lookup"><span data-stu-id="dc930-210">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

