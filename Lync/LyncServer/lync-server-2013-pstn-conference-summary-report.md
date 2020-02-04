---
title: 'Lync Server 2013: informe Resumen de conferencia RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8cd36f651a84b25f7e8163a8cfc40aff5162f90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="aad94-102">Informe Resumen de la Conferencia RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aad94-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aad94-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="aad94-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="aad94-104">En Microsoft Lync Server 2013, una conferencia RTC es cualquier conferencia en la que al menos un participante llama a la parte de audio mediante un teléfono con RTC (red de telefonía pública conmutada).</span><span class="sxs-lookup"><span data-stu-id="aad94-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="aad94-105">(Un teléfono PSTN es un "teléfono fijo", un teléfono móvil o cualquier otro teléfono que no use voz por IP). A pesar de que se conocen como conferencias de RTC en los informes de supervisión, es posible que estas conferencias sean más conocidas como conferencias de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="aad94-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="aad94-p102">El informe de resumen de conferencias RTC proporciona información sobre todas las conferencias RTC mantenidas en su organización (es decir, todas las conferencias en las que hubo al menos un usuario de acceso telefónico). El informe incluye información sobre la cantidad total de conferencias RTC, la cantidad total de personas que participaron en dichas conferencias y, quizás lo más importante, la cantidad total de usuarios de acceso telefónico (métrica Total de participantes RTC).</span><span class="sxs-lookup"><span data-stu-id="aad94-p102">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user). The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="aad94-108">Acceso al informe de resumen de conferencias RTC</span><span class="sxs-lookup"><span data-stu-id="aad94-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="aad94-p103">El informe de resumen de conferencias RTC solo es accesible desde la página principal de informes de supervisión. Este informe no está vinculado a ningún otro informe. Tenga en cuenta que no se puede recuperar información detallada sobre llamadas para una conferencia RTC, en parte porque los responsables de enviar esta información son extremos individuales. Los teléfonos RTC no pueden realizar el seguimiento ni enviar información detallada sobre llamadas.</span><span class="sxs-lookup"><span data-stu-id="aad94-p103">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page. This report is not linked to any other reports. Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information. PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="aad94-113">Optimización del uso del informe de resumen de conferencias RTC</span><span class="sxs-lookup"><span data-stu-id="aad94-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="aad94-114">Para determinar el porcentaje de todas las conferencias que incluyen usuarios de acceso telefónico, compare el valor de la métrica total de conferencias RTC con la métrica total de conferencias que se encuentra en el [Informe de Resumen de conferencia en Lync Server 2013](lync-server-2013-conference-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="aad94-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="aad94-115">Si no ve la cantidad de conferencias RTC que esperaba ver, tenga en cuenta que la capacidad para organizar una conferencia que admita usuarios de acceso telefónico depende de la directiva de conferencias que se haya asignado a un usuario; si muy pocos usuarios pueden organizar conferencias RTC, obviamente verá pocas conferencias RTC.</span><span class="sxs-lookup"><span data-stu-id="aad94-115">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences.</span></span> <span data-ttu-id="aad94-116">Puede comprobar rápidamente cuáles de las directivas de conferencia (si las hay) permite a los usuarios programar conferencias RTC ejecutando el siguiente comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="aad94-116">You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="aad94-117">Se devolverán datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="aad94-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="aad94-118">Se devolverán datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="aad94-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="aad94-119">Filtros</span><span class="sxs-lookup"><span data-stu-id="aad94-119">Filters</span></span>

<span data-ttu-id="aad94-120">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas.</span><span class="sxs-lookup"><span data-stu-id="aad94-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="aad94-121">Por ejemplo, el informe Resumen de la Conferencia RTC le permite elegir cómo se deben agrupar los datos.</span><span class="sxs-lookup"><span data-stu-id="aad94-121">For example, the PSTN Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="aad94-122">En este caso, las conferencias se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="aad94-122">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="aad94-123">La siguiente tabla contiene los filtros que se pueden usar con el informe de resumen de conferencia RTC.</span><span class="sxs-lookup"><span data-stu-id="aad94-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="aad94-124">Filtros del informe de resumen de conferencia RTC</span><span class="sxs-lookup"><span data-stu-id="aad94-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aad94-125">Nombre</span><span class="sxs-lookup"><span data-stu-id="aad94-125">Name</span></span></th>
<th><span data-ttu-id="aad94-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="aad94-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aad94-127"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="aad94-p106">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="aad94-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="aad94-130">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="aad94-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="aad94-p107">Si no escribe una hora de inicio, el informe se iniciará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="aad94-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="aad94-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="aad94-133">7/7/2012</span></span></p>
<p><span data-ttu-id="aad94-134">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="aad94-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="aad94-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="aad94-135">7/3/2012</span></span></p>
<p><span data-ttu-id="aad94-136">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="aad94-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aad94-137"><strong>Hasta</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="aad94-p108">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="aad94-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="aad94-140">7/7/2012 1:00 P.M.</span><span class="sxs-lookup"><span data-stu-id="aad94-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="aad94-p109">Si no escribe una hora de finalización, el informe finalizará automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="aad94-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="aad94-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="aad94-143">7/7/2012</span></span></p>
<p><span data-ttu-id="aad94-144">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="aad94-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="aad94-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="aad94-145">7/3/2012</span></span></p>
<p><span data-ttu-id="aad94-146">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="aad94-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aad94-147"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="aad94-p110">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="aad94-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aad94-150">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="aad94-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="aad94-151">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="aad94-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="aad94-152">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="aad94-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="aad94-153">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="aad94-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="aad94-154">Si las fechas de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solo se mostrará la cantidad máxima de valores (comenzando en la fecha de inicio).</span><span class="sxs-lookup"><span data-stu-id="aad94-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="aad94-155">Por ejemplo, si selecciona el intervalo diario con una fecha de inicio de 7/7/2012 y una fecha de finalización de 2/28/2012, los datos se muestran para los días 8/7/2012 12:00 A.M. a 9/7/2012 12:00 A.M. (es decir, un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="aad94-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="aad94-156">Métricas</span><span class="sxs-lookup"><span data-stu-id="aad94-156">Metrics</span></span>

<span data-ttu-id="aad94-157">La siguiente tabla contiene la información que recoge el informe de resumen de conferencia RTC.</span><span class="sxs-lookup"><span data-stu-id="aad94-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="aad94-158">Métricas del informe de resumen de conferencia RTC</span><span class="sxs-lookup"><span data-stu-id="aad94-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aad94-159">Nombre</span><span class="sxs-lookup"><span data-stu-id="aad94-159">Name</span></span></th>
<th><span data-ttu-id="aad94-160">¿Se pueden ordenar los datos por este elemento?</span><span class="sxs-lookup"><span data-stu-id="aad94-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="aad94-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="aad94-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aad94-162"><strong>Cada hora</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="aad94-163"><strong>Cada día</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="aad94-164"><strong>Cada semana</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="aad94-165"><strong>Cada mes</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="aad94-166">No</span><span class="sxs-lookup"><span data-stu-id="aad94-166">No</span></span></p></td>
<td><p><span data-ttu-id="aad94-167">Indica el intervalo temporal seleccionado.</span><span class="sxs-lookup"><span data-stu-id="aad94-167">Indicates the selected time interval.</span></span> <span data-ttu-id="aad94-168">Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo.</span><span class="sxs-lookup"><span data-stu-id="aad94-168">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="aad94-169">Por ejemplo, si está usando el intervalo diario y hace clic en 7/7/2012, verá un desglose por hora de actividad de registro de usuario para esa fecha.</span><span class="sxs-lookup"><span data-stu-id="aad94-169">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aad94-170"><strong>Total de conferencias RTC</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="aad94-171">No</span><span class="sxs-lookup"><span data-stu-id="aad94-171">No</span></span></p></td>
<td><p><span data-ttu-id="aad94-172">Cantidad total de conferencias donde se permitió el acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="aad94-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aad94-173"><strong>Total de participantes</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="aad94-174">No</span><span class="sxs-lookup"><span data-stu-id="aad94-174">No</span></span></p></td>
<td><p><span data-ttu-id="aad94-175">Cantidad total de personas que participaron en conferencias donde se permitió el acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="aad94-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aad94-176"><strong>Total de minutos de conferencia A/V</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="aad94-177">No</span><span class="sxs-lookup"><span data-stu-id="aad94-177">No</span></span></p></td>
<td><p><span data-ttu-id="aad94-178">Tiempo total de la conferencia audiovisual.</span><span class="sxs-lookup"><span data-stu-id="aad94-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aad94-179"><strong>Total de minutos de participantes en conferencia A/V</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="aad94-180">No</span><span class="sxs-lookup"><span data-stu-id="aad94-180">No</span></span></p></td>
<td><p><span data-ttu-id="aad94-p113">Tiempo total de participación en la conferencia audiovisual. Por ejemplo, si un participante invirtió cinco minutos en una conferencia A/V y otro, tres minutos en la misma conferencia, el tiempo total de participantes en dicha conferencia será de ocho minutos.</span><span class="sxs-lookup"><span data-stu-id="aad94-p113">Total amount of audio/visual participant time. For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aad94-183"><strong>Total de participantes RTC</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="aad94-184">No</span><span class="sxs-lookup"><span data-stu-id="aad94-184">No</span></span></p></td>
<td><p><span data-ttu-id="aad94-185">Cantidad total de usuarios que obtuvo acceso telefónicamente en conferencias donde se permitió el acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="aad94-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aad94-186"><strong>Total de minutos de participantes RTC</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="aad94-187">No</span><span class="sxs-lookup"><span data-stu-id="aad94-187">No</span></span></p></td>
<td><p><span data-ttu-id="aad94-p114">Tiempo total que los usuarios de acceso telefónico dedicaron a la conferencia. Por ejemplo, si un participante de acceso telefónico invirtió cinco minutos en una conferencia A/V y otro, tres minutos en la misma conferencia, el tiempo total de participantes RTC será de ocho minutos.</span><span class="sxs-lookup"><span data-stu-id="aad94-p114">Total amount of conference time spent by dial-in users. For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aad94-190"><strong>Organizadores de conferencia únicos</strong></span><span class="sxs-lookup"><span data-stu-id="aad94-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="aad94-191">No</span><span class="sxs-lookup"><span data-stu-id="aad94-191">No</span></span></p></td>
<td><p><span data-ttu-id="aad94-p115">Cantidad total de usuarios que organizaron al menos una conferencia donde se permitió el acceso telefónico. Los usuarios que hayan organizado más de una conferencia se consideran como un único organizador, igual que los que solo han organizado una conferencia.</span><span class="sxs-lookup"><span data-stu-id="aad94-p115">Total number of users who organized at least one conference that allowed dial-in access. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

