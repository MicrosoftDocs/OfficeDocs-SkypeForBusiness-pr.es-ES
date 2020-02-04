---
title: 'Lync Server 2013: informe de uso de grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 702ab291955ef7c8ec992e3607de581dff52b6a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="c5aab-102">Informe de uso de grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5aab-102">Response Group Usage Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5aab-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c5aab-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c5aab-104">La aplicación de grupo de respuesta proporciona una manera de que Microsoft Lync Server 2013 responda y enrute llamadas telefónicas en función del número que haya marcado y, opcionalmente, de las respuestas de la persona que llama a una serie de preguntas.</span><span class="sxs-lookup"><span data-stu-id="c5aab-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="c5aab-105">Normalmente, las llamadas a grupos de respuesta no se dirigen a una persona individual, sino que se dirigen a un equipo de personas a las que se hace referencia como grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="c5aab-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="c5aab-106">Por ejemplo, si alguien llama al número de teléfono del Departamento de soporte técnico, Lync Server 2013 puede enrutar automáticamente esa llamada al primer agente del servicio de asistencia disponible.</span><span class="sxs-lookup"><span data-stu-id="c5aab-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="c5aab-107">Como alternativa, Lync Server podría formular una serie de preguntas ("Presione 1 si tiene problemas de hardware.</span><span class="sxs-lookup"><span data-stu-id="c5aab-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="c5aab-108">Pulse 2 Si tiene problemas de software.</span><span class="sxs-lookup"><span data-stu-id="c5aab-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="c5aab-109">Pulse 3 Si tiene problemas de red. ") y luego enrutar la llamada al agente del servicio de asistencia al cliente más adecuado, en función de la respuesta a esas preguntas.</span><span class="sxs-lookup"><span data-stu-id="c5aab-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="c5aab-110">El Informe de uso del grupo de respuesta ofrece una perspectiva detallada del número de llamadas de teléfono que se han recibido en todos los flujos de trabajo de grupo de respuesta y, luego, separa dichas llamadas en categorías finitas como, por ejemplo, Llamadas ofrecidas, Llamadas contestadas o Llamadas abandonadas.</span><span class="sxs-lookup"><span data-stu-id="c5aab-110">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="c5aab-111">La clave para trabajar con el Informe de uso del grupo de respuesta está en comprender la diferencia entre los tipos de llamadas incluidas en el informe:</span><span class="sxs-lookup"><span data-stu-id="c5aab-111">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="c5aab-p102">**Llamadas recibidas**. Cantidad total de llamadas recibidas por todas las instancias de la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p102">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="c5aab-p103">**Llamadas correctas**. Cantidad total de llamadas respondidas por la aplicación Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p103">**Successful calls**. Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="c5aab-p104">**Llamadas ofrecidas**. Cantidad total de llamadas transferidas a un agente de Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p104">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="c5aab-p105">**Llamadas contestadas**. Cantidad total de llamadas contestadas realmente por un agente de Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p105">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="c5aab-p106">**Porcentaje de llamadas abandonadas**. Porcentaje de llamadas recibidas por la aplicación Grupo de respuesta que nunca contestó un agente. Este valor se calcula restando las llamadas contestadas a las llamadas recibidas y, luego, dividiendo el valor obtenido entre el número de Llamadas recibidas. Por ejemplo, si se han recibido 10 llamadas y 7 no se contestaron, necesita restar 7 a 10, lo que da un resultado de 3 llamadas no respondidas. Luego, dicho valor se divide entre 10, con lo que obtiene un porcentaje de llamadas abandonadas del 30 %.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p106">**Percentage of abandoned calls**. Percentage of calls that were received by the Response Group application but were never answered by an agent. This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls. For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="c5aab-p107">**Llamadas transferidas**. Cantidad total de llamadas de Grupo de repuesta transferidas porque se agotó un tiempo de espera de cola o porque una cola está desbordada.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p107">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="c5aab-p108">Si no recuerda la definición de los tipos de llamadas del Informe de uso del grupo de respuesta, basta con mantener el mouse sobre la etiqueta del tipo de llamada correspondiente. Aparecerá una información sobre herramientas con una descripción breve del tipo de llamada.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p108">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label. A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="c5aab-p109">El Informe de uso del grupo de respuesta permite filtrar URI de flujos de trabajo (dirección SIP asociada a dicho flujo de trabajo). Pero, los URI de flujos de trabajo no se muestran en el informe. Si desea conocer aspectos como, por ejemplo, qué flujos de trabajo están respondiendo a la mayoría de las llamadas o qué flujos de trabajo están transfiriendo más llamadas, haga clic en la métrica correspondiente para abrir el Informe de lista de llamadas de grupo de respuesta para dicho periodo. Este informe no muestra los URI de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p109">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow). However, workflow URIs do not actually appear on the report itself. If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period. That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="c5aab-133">Acceso al Informe de uso del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="c5aab-133">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="c5aab-134">Es posible tener acceso al Informe de uso del grupo de respuesta desde la página de inicio de informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="c5aab-134">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="c5aab-135">Puede explorar en profundidad el [Informe de la lista de llamadas del grupo de respuesta en Lync Server 2013](lync-server-2013-response-group-call-list-report.md) haciendo clic en cualquiera de las siguientes métricas:</span><span class="sxs-lookup"><span data-stu-id="c5aab-135">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="c5aab-136">Llamadas recibidas</span><span class="sxs-lookup"><span data-stu-id="c5aab-136">Received calls</span></span>

  - <span data-ttu-id="c5aab-137">Llamadas correctas</span><span class="sxs-lookup"><span data-stu-id="c5aab-137">Successful calls</span></span>

  - <span data-ttu-id="c5aab-138">Llamadas ofrecidas</span><span class="sxs-lookup"><span data-stu-id="c5aab-138">Offered calls</span></span>

  - <span data-ttu-id="c5aab-139">Llamadas contestadas</span><span class="sxs-lookup"><span data-stu-id="c5aab-139">Answered calls</span></span>

  - <span data-ttu-id="c5aab-140">Llamadas transferidas</span><span class="sxs-lookup"><span data-stu-id="c5aab-140">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="c5aab-141">Cómo sacar el máximo partido al Informe de uso del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="c5aab-141">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="c5aab-142">Uno de los usos más interesantes del Informe de uso del grupo de respuesta puede no resultar obvio a primera vista: la capacidad para recuperar información sobre el uso de un único flujo de trabajo de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5aab-142">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c5aab-143">Un flujo de trabajo de grupo de respuesta es básicamente un conjunto de instrucciones que determinan qué hace Lync Server cuando un usuario marca un número de teléfono determinado.</span><span class="sxs-lookup"><span data-stu-id="c5aab-143">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="c5aab-144">Para ello, cada flujo de trabajo está asociado a un único número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="c5aab-144">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="c5aab-145">Cuando alguien llama a dicho número, el flujo de trabajo determina cómo se administrará la llamada.</span><span class="sxs-lookup"><span data-stu-id="c5aab-145">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="c5aab-146">Por ejemplo, el flujo de trabajo puede enrutar la llamada a través de una serie de preguntas de respuesta de voz interactiva (IVR) que indican al autor de la llamada que necesita especificar información adicional ("Presione 1 si necesita asistencia para hardware.</span><span class="sxs-lookup"><span data-stu-id="c5aab-146">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="c5aab-147">Presione 2 si necesita asistencia para software").</span><span class="sxs-lookup"><span data-stu-id="c5aab-147">Press 2 for software support.").</span></span> <span data-ttu-id="c5aab-148">De forma alternativa, el flujo de trabajo también puede poner la llamada en cola y mantener al autor de la llamada en espera hasta que haya un agente disponible para atender la llamada.</span><span class="sxs-lookup"><span data-stu-id="c5aab-148">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="c5aab-149">La disponibilidad de los agentes para responder a llamadas también está determinada por el flujo de trabajo: los flujos de trabajo se usan para configurar el horario laboral (días de la semana y horas del día en que los agentes están disponibles para responder a llamadas) y los festivos (días en los que no hay agentes disponibles para responder a llamadas).</span><span class="sxs-lookup"><span data-stu-id="c5aab-149">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="c5aab-150">Cuando realiza llamadas a números de teléfono que pertenecen a una aplicación de grupo de respuesta, básicamente está llamando a un flujo de trabajo de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5aab-150">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="c5aab-p112">Aunque los URI de los flujos de trabajo no se muestran en el Informe de uso del grupo de respuesta, pueden verse las estadísticas de uso de un flujo de trabajo determinado, cosa que a menudo es de gran utilidad. Por ejemplo, supongamos que ha lanzado una nueva campaña publicitaria y tiene curiosidad por saber si se están registrando llamadas para obtener información sobre el producto. Si tiene un flujo de trabajo de grupo de respuesta asociado al número de teléfono de la campaña publicitaria, podrá comprobar fácilmente cuántas personas están llamando a dicho número.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p112">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful. For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product. If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="c5aab-154">Puede utilizar un enfoque similar para evaluar el número de llamadas atendidas por su servicio de asistencia interno o por el departamento de atención al cliente.</span><span class="sxs-lookup"><span data-stu-id="c5aab-154">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="c5aab-155">Para revisar las estadísticas de uso de un flujo de trabajo determinado, escriba el URI del flujo de trabajo en el cuadro URI de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c5aab-155">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="c5aab-156">Tal como se ha mencionado, los URI de flujos de trabajo (dirección SIP asociada a un flujo de trabajo) no se muestran en el informe.</span><span class="sxs-lookup"><span data-stu-id="c5aab-156">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="c5aab-157">Esto implica que necesitará buscar otra forma de determinar el URI de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c5aab-157">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="c5aab-158">Una forma de hacerlo es usar Windows PowerShell y el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5aab-158">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="c5aab-159">Por ejemplo, este comando devuelve los URI de todos los flujos de trabajo de grupo de respuesta:</span><span class="sxs-lookup"><span data-stu-id="c5aab-159">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="c5aab-160">Se devolverán datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="c5aab-160">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="c5aab-161">Este comando devuelve información de un único flujo de trabajo, el flujo de trabajo con el nombre New Ad Campaign:</span><span class="sxs-lookup"><span data-stu-id="c5aab-161">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c5aab-162">Filtros</span><span class="sxs-lookup"><span data-stu-id="c5aab-162">Filters</span></span>

<span data-ttu-id="c5aab-p114">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de uso del grupo de respuesta le permite ver datos de todos los flujos de trabajo del grupo de respuesta o ver datos de un flujo de trabajo concreto. También se puede elegir cómo agrupar los datos. En este caso, los usos se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p114">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="c5aab-167">En la tabla siguiente se muestran los filtros que se pueden utilizar en el informe de uso del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5aab-167">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="c5aab-168">Filtros del informe de uso del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="c5aab-168">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5aab-169">Nombre</span><span class="sxs-lookup"><span data-stu-id="c5aab-169">Name</span></span></th>
<th><span data-ttu-id="c5aab-170">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5aab-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5aab-171"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-171"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-p115">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c5aab-p115">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c5aab-174">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="c5aab-174">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c5aab-p116">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="c5aab-p116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c5aab-177">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c5aab-177">7/7/2012</span></span></p>
<p><span data-ttu-id="c5aab-178">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="c5aab-178">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c5aab-179">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c5aab-179">7/3/2012</span></span></p>
<p><span data-ttu-id="c5aab-180">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="c5aab-180">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5aab-181"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-181"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-p117">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c5aab-p117">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c5aab-184">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="c5aab-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c5aab-p118">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="c5aab-p118">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c5aab-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c5aab-187">7/7/2012</span></span></p>
<p><span data-ttu-id="c5aab-188">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="c5aab-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c5aab-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c5aab-189">7/3/2012</span></span></p>
<p><span data-ttu-id="c5aab-190">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="c5aab-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5aab-191"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-191"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-p119">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c5aab-p119">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c5aab-194">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="c5aab-194">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c5aab-195">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="c5aab-195">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c5aab-196">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="c5aab-196">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c5aab-197">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="c5aab-197">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="c5aab-198">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio).</span><span class="sxs-lookup"><span data-stu-id="c5aab-198">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="c5aab-199">Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="c5aab-199">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5aab-200"><strong>URI de flujo de trabajo</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-200"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-p121">Permite limitar los datos devueltos al flujo de trabajo de grupo de respuesta especificado. Para usar este filtro, escriba la dirección SIP del grupo de trabajo. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c5aab-p121">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="c5aab-204">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c5aab-204">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c5aab-205">Métricas</span><span class="sxs-lookup"><span data-stu-id="c5aab-205">Metrics</span></span>

<span data-ttu-id="c5aab-206">En la tabla siguiente se muestra la información que recoge el informe de uso del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5aab-206">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="c5aab-207">Métricas del informe de uso del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="c5aab-207">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5aab-208">Nombre</span><span class="sxs-lookup"><span data-stu-id="c5aab-208">Name</span></span></th>
<th><span data-ttu-id="c5aab-209">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="c5aab-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c5aab-210">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5aab-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5aab-211"><strong>Cada hora</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="c5aab-212"><strong>Cada día</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="c5aab-213"><strong>Cada semana</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="c5aab-214"><strong>Cada mes</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-215">No</span><span class="sxs-lookup"><span data-stu-id="c5aab-215">No</span></span></p></td>
<td><p><span data-ttu-id="c5aab-216">Indica el intervalo temporal seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c5aab-216">Indicates the selected time interval.</span></span> <span data-ttu-id="c5aab-217">Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo.</span><span class="sxs-lookup"><span data-stu-id="c5aab-217">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="c5aab-218">Por ejemplo, si está usando el intervalo diario y hace clic en 7/7/2012, verá un desglose por hora de actividad de registro de usuario para esa fecha.</span><span class="sxs-lookup"><span data-stu-id="c5aab-218">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5aab-219"><strong>Llamadas recibidas</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-219"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-220">No</span><span class="sxs-lookup"><span data-stu-id="c5aab-220">No</span></span></p></td>
<td><p><span data-ttu-id="c5aab-p123">Cantidad total de llamadas recibidas por todas las instancias de la aplicación Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p123">Total number of calls received by all instances of the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5aab-223"><strong>Llamadas correctas</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-223"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-224">No</span><span class="sxs-lookup"><span data-stu-id="c5aab-224">No</span></span></p></td>
<td><p><span data-ttu-id="c5aab-p124">Cantidad total de llamadas respondidas por la aplicación Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p124">Total number of calls that were picked up the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5aab-227"><strong>Llamadas ofrecidas</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-227"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-228">No</span><span class="sxs-lookup"><span data-stu-id="c5aab-228">No</span></span></p></td>
<td><p><span data-ttu-id="c5aab-p125">Cantidad total de llamadas transferidas a un agente de Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p125">Total number of calls that were transferred to a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5aab-231"><strong>Llamadas contestadas</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-231"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-232">No</span><span class="sxs-lookup"><span data-stu-id="c5aab-232">No</span></span></p></td>
<td><p><span data-ttu-id="c5aab-p126">Cantidad total de llamadas contestadas realmente por un agente de Grupo de respuesta. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p126">Total number of calls that were actually answered by a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5aab-235"><strong>Porcentaje de llamadas abandonadas</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-235"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-236">No</span><span class="sxs-lookup"><span data-stu-id="c5aab-236">No</span></span></p></td>
<td><p><span data-ttu-id="c5aab-p127">Cantidad total de llamadas recibidas por la aplicación Grupo de respuesta que nunca contestó un agente. Este número se calcula restando las llamadas contestadas a las llamadas recibidas y, a continuación, dividiendo el valor obtenido entre el número de llamadas recibidas. Por ejemplo, si tiene 10 llamadas recibidas y siete no se contestaron, resta siete a 10, lo que da un resultado de tres llamadas no respondidas. A continuación, dicho valor se divide entre 10, con lo que obtiene un porcentaje de llamadas abandonadas del 30 %.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p127">Total number of calls that were received by the Response Group application but were never answered by an agent. This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls. For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5aab-241"><strong>Media de minutos de llamada por agente</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-241"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-242">No</span><span class="sxs-lookup"><span data-stu-id="c5aab-242">No</span></span></p></td>
<td><p><span data-ttu-id="c5aab-243">Media de tiempo que dedica cada agente de Grupo de respuesta a una llamada.</span><span class="sxs-lookup"><span data-stu-id="c5aab-243">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5aab-244"><strong>Llamadas transferidas</strong></span><span class="sxs-lookup"><span data-stu-id="c5aab-244"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="c5aab-245">No</span><span class="sxs-lookup"><span data-stu-id="c5aab-245">No</span></span></p></td>
<td><p><span data-ttu-id="c5aab-p128">Cantidad total de llamadas de Grupo de repuesta transferidas porque se agotó un tiempo de espera de cola o porque una cola está desbordada. Al hacer clic en este elemento, el informe le muestra el informe Lista de llamadas del grupo de respuesta correspondiente al periodo de tiempo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c5aab-p128">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

