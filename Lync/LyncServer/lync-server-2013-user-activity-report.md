---
title: 'Lync Server 2013: informe de actividad de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ad0297451c98851d156f088497db81345520b88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="c4fa2-102">Informe de actividad de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4fa2-102">User Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4fa2-103">_**Última modificación del tema:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="c4fa2-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="c4fa2-p101">El Informe de actividad de usuario proporciona una lista detallada de sesiones de conferencia y de punto a punto realizadas por sus usuarios en un período determinado. A diferencia de muchos de los Informes de supervisión, el Informe de actividad de usuario une cada llamada a usuarios individuales. Por ejemplo, las sesiones de punto a punto especifican los URI del SIP de la persona que inició la llamada (el usuario De) y la persona a la que se realizó la llamada (el usuario Para). Si expande la información de una conferencia, verá una lista de todos los participantes de la conferencia y el rol que desempeñaban en esa conferencia.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="c4fa2-p102">Al Informe de actividad de usuario a veces se lo conoce como "informe de asistencia técnica", debido a que a menudo el personal de asistencia técnica lo utiliza para recuperar información de sesión para un usuario específico. Es posible establecer filtros para llamadas realizadas a o por un usuario particular con tan solo escribir el URI del SIP del usuario en el cuadro de prefijo de URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="c4fa2-111">Si lo hace, el informe de actividad de usuario devolverá información para cualquier usuario cuyo URI de SIP comience con la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="c4fa2-112">Por ejemplo, si escribe **Ken** en el cuadro URI, el informe de actividad de usuario buscará a **Ken**. Myer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="c4fa2-113">Sin embargo, también buscará a estos usuarios:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="c4fa2-114">**ken**AZI@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c4fa2-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="c4fa2-115">**ken**Burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c4fa2-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="c4fa2-116">**Ken**. Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c4fa2-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="c4fa2-117">**Ken**Nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c4fa2-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="c4fa2-118">Para asegurarse de que se devuelve información sólo para Ken Myer, escriba su URI completo (Ken.Myer@litwareinc.com) en el cuadro de búsqueda o, al menos, el tipo de URI de Ken para distinguirlo de otros usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="c4fa2-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-119">For example:</span></span>

<span data-ttu-id="c4fa2-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="c4fa2-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="c4fa2-121">Acceso al informe de actividad de usuario</span><span class="sxs-lookup"><span data-stu-id="c4fa2-121">To access the user activity report</span></span>

<span data-ttu-id="c4fa2-122">Para acceder al Informe de actividad de usuario hay que ir a la página de inicio de Informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="c4fa2-123">También puede obtener acceso al informe de actividad de usuario haciendo clic en la métrica de URI de usuario en el [Informe de inventario de teléfono IP en Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span><span class="sxs-lookup"><span data-stu-id="c4fa2-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="c4fa2-124">Desde el Informe de actividad de usuario, puede hacer clic en el URI de conferencia (para una conferencia) para acceder al Informe de detalles de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="c4fa2-125">De forma similar, al hacer clic en la métrica de detalle para una llamada punto a punto, se obtiene el [Informe de detalles de sesiones punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="c4fa2-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="c4fa2-126">Aprovechar al máximo el informe de actividad de usuario</span><span class="sxs-lookup"><span data-stu-id="c4fa2-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="c4fa2-127">Aunque hay mucha información buena en el Informe de actividad de usuario, esa información puede a veces ser difícil de encontrar.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="c4fa2-128">Por ejemplo, toda la actividad de usuario que se realiza en la organización durante un período especificado se incluye en el informe de actividad de usuario; Esto significa que, en el informe, la información sobre qué usuarios usaron en realidad Microsoft Lync Server 2013 de alguna manera.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c4fa2-129">Técnicamente, es posible que algunas actividades de usuario no se registren: Si bien Lync Server se esfuerza por mantener la información sobre todas las llamadas telefónicas, es posible que se haya realizado una llamada sin que la información sobre la llamada se escriba en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="c4fa2-130">Lync Server está diseñado para proporcionar un aspecto extremadamente preciso, pero no necesariamente perfecto, a la forma en que se usa Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="c4fa2-131">(El hecho de que no hay ninguna garantía de que el 100% de todas las llamadas se registren explica por qué no se debe usar la supervisión de Lync Server como sistema de facturación).</span><span class="sxs-lookup"><span data-stu-id="c4fa2-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="c4fa2-p108">En segundo lugar, un Informe de supervisión solo puede mostrar, como máximo, 1000 registros. Según la cantidad de actividad de usuario que tenga y según el período de tiempo con el que trabaje, eso significa que su consulta podría no devolverle todos los datos realmente almacenados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p108">Second, a Monitoring Report report can only display, at most, 1,000 records. Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="c4fa2-134">¿Qué usuarios utilizaron en realidad el sistema durante este período?</span><span class="sxs-lookup"><span data-stu-id="c4fa2-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="c4fa2-135">¿Cuáles de mis usuarios fueron los más activos durante este período?</span><span class="sxs-lookup"><span data-stu-id="c4fa2-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="c4fa2-136">¿Los usuarios que realizan la mayor cantidad de llamadas telefónicas también son los usuarios que participan en la mayoría de las sesiones de mensajería instantánea?</span><span class="sxs-lookup"><span data-stu-id="c4fa2-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="c4fa2-137">Si necesita responder preguntas como estas, puede exportar los datos recuperados por los Informes de supervisión a una hoja de cálculos de Excel.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="c4fa2-138">Luego utiliza esa hoja de cálculos y/o un archivo de valores separados por comas para analizar los datos del modo en que no permite el Informe de actividad de usuario.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="c4fa2-139">Por ejemplo, imaginemos que ha exportado los datos del informe a Excel y luego a un archivo de valores separados por comas.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="c4fa2-140">En ese momento, puede importar los datos desde el. Archivo CSV a Windows PowerShell mediante un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="c4fa2-141">Una vez importados los datos, puede usar comandos sencillos de Windows PowerShell para ayudar a responder sus preguntas.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="c4fa2-142">Por ejemplo, este comando devuelve una lista de usuarios únicos que han tenido el rol de "usuario De" en al menos una sesión:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="c4fa2-143">En otras palabras:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="c4fa2-144">Este comando enumera los usuarios únicos (en función del número total de sesiones en las que participaron):</span><span class="sxs-lookup"><span data-stu-id="c4fa2-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="c4fa2-145">Eso devuelve datos similares a esto:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="c4fa2-146">Este comando limita las sesiones informadas a aquellas que incluyeron audio como modalidad:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="c4fa2-147">Si mantiene el cursor del mouse sobre cualquier identificador de diagnóstico mostrado en el informe, aparecerá una información sobre herramientas que describirá ese identificador.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c4fa2-148">Filtros</span><span class="sxs-lookup"><span data-stu-id="c4fa2-148">Filters</span></span>

<span data-ttu-id="c4fa2-p111">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el informe de actividad de usuario le permite filtrar los datos devueltos en función de aspectos tales como el tipo de actividad (es decir, sesiones punto a punto o sesiones de conferencia) o por la dirección SIP del usuario (permitiéndole ver las actividades de un usuario). Es posible también elegir la forma en la que deben agruparse los datos. En este caso, los usos se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="c4fa2-153">La siguiente tabla muestra los filtros que puede utilizar con el informe de actividad de usuario.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="c4fa2-154">Filtros del informe de actividad de usuario</span><span class="sxs-lookup"><span data-stu-id="c4fa2-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4fa2-155">Nombre</span><span class="sxs-lookup"><span data-stu-id="c4fa2-155">Name</span></span></th>
<th><span data-ttu-id="c4fa2-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4fa2-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-157"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-p112">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c4fa2-160">17/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c4fa2-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="c4fa2-p113">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c4fa2-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="c4fa2-163">7/17/12012</span></span></p>
<p><span data-ttu-id="c4fa2-164">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="c4fa2-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c4fa2-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="c4fa2-165">7/13/2012</span></span></p>
<p><span data-ttu-id="c4fa2-166">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-167"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-p114">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c4fa2-170">17/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="c4fa2-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="c4fa2-p115">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c4fa2-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="c4fa2-173">7/17/12012</span></span></p>
<p><span data-ttu-id="c4fa2-174">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="c4fa2-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c4fa2-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="c4fa2-175">7/13/2012</span></span></p>
<p><span data-ttu-id="c4fa2-176">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-177"><strong>Tipo de actividad</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-p116">Tipo de actividad. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c4fa2-180">Todos</span><span class="sxs-lookup"><span data-stu-id="c4fa2-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="c4fa2-181">Punto a punto</span><span class="sxs-lookup"><span data-stu-id="c4fa2-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="c4fa2-182">Conversación</span><span class="sxs-lookup"><span data-stu-id="c4fa2-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-183"><strong>Modalidad</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-184">La modalidad disponible para el usuario varía en función del tipo de actividad de selección.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="c4fa2-185">Si el tipo de actividad es de punto a punto, puede seleccionar mi; Transferencia de archivos; Uso compartido de aplicaciones; Mensaje o el vídeo como modalidad.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="c4fa2-186">Si el tipo de actividad es Conferencia, puede seleccionar conferencia telefónica de mensajería instantánea; Conferencia Web; Uso compartido de aplicaciones; Conferencia de voz y vídeo; o conferencia de telefonía.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-187"><strong>Categoría de sesión</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-p118">Indica si la actividad correspondiente se desarrolló correctamente o causó errores. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c4fa2-190">Todos</span><span class="sxs-lookup"><span data-stu-id="c4fa2-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="c4fa2-191">Success</span><span class="sxs-lookup"><span data-stu-id="c4fa2-191">Success</span></span></p></li>
<li><p><span data-ttu-id="c4fa2-192">Error esperado</span><span class="sxs-lookup"><span data-stu-id="c4fa2-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="c4fa2-193">Error inesperado</span><span class="sxs-lookup"><span data-stu-id="c4fa2-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="c4fa2-194">Un &quot;error esperado&quot; es un error que se espera que suceda; por ejemplo, si un usuario ha establecido su estado en no molestar, se espera que se produzca un error en cualquier llamada a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="c4fa2-195">Un &quot;error&quot; inesperado es un error que se produce en lo que parecería ser un sistema en mal estado.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="c4fa2-196">Por ejemplo, una llamada no debería finalizarse si el autor de la llamada está en espera.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="c4fa2-197">De ser así, dicha situación se identificaría como un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-198"><strong>Prefijo de URI de usuario</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-p120">Dirección SIP del usuario. Para ver únicamente registros del usuario Ken Myer debe introducir la dirección SIP de Ken Myer. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="c4fa2-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c4fa2-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="c4fa2-203">Métricas de las sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="c4fa2-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="c4fa2-204">En la siguiente tabla se muestra la información proporcionada en el informe de actividad de usuario correspondiente a sesiones punto a punto (es decir, sesiones con solo dos participantes).</span><span class="sxs-lookup"><span data-stu-id="c4fa2-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="c4fa2-205">Métricas de las sesiones punto a punto</span><span class="sxs-lookup"><span data-stu-id="c4fa2-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4fa2-206">Nombre</span><span class="sxs-lookup"><span data-stu-id="c4fa2-206">Name</span></span></th>
<th><span data-ttu-id="c4fa2-207">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="c4fa2-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c4fa2-208">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4fa2-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-209"><strong>Detalle</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-210">No</span><span class="sxs-lookup"><span data-stu-id="c4fa2-210">No</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-211">Al hacer clic en este elemento, el informe le muestra el informe de detalles de sesiones punto a punto correspondiente a la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-212"><strong>Remitente</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-213">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-214">Dirección SIP del usuario que inició la sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-215"><strong>Destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-216">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-217">Dirección SIP del usuario que se unió a la sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-218"><strong>Modalidades</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-219">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-p121">Tipo de comunicación usado en la sesión. Por ejemplo, mensajería instantánea, sonido o transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-222"><strong>Hora de invitación</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-223">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-224">Fecha y hora en las que se envió la invitación inicial a unirse a la sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-225"><strong>Tiempo de respuesta</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-226">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-227">Fecha y hora en las &quot;que&quot; el usuario aceptó la invitación a la sesión.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-228"><strong>Hora de finalización</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-229">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-230">Fecha y hora en las que finalizó la sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-231"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-232">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-p122">Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="c4fa2-235">Métricas de las sesiones de conferencia</span><span class="sxs-lookup"><span data-stu-id="c4fa2-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="c4fa2-236">En la siguiente tabla se muestra la información proporcionada en el informe de actividad de usuario correspondiente a sesiones de conferencia (es decir, sesiones con tres o más participantes).</span><span class="sxs-lookup"><span data-stu-id="c4fa2-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="c4fa2-237">Métricas de las sesiones de conferencia</span><span class="sxs-lookup"><span data-stu-id="c4fa2-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4fa2-238">Nombre</span><span class="sxs-lookup"><span data-stu-id="c4fa2-238">Name</span></span></th>
<th><span data-ttu-id="c4fa2-239">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="c4fa2-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c4fa2-240">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4fa2-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-241"><strong>URI de conferencia</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-242">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-243">Identificador único de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-243">Unique conference identifier.</span></span> <span data-ttu-id="c4fa2-244">Al hacer clic en este elemento, el informe le muestra el informe de detalles de conferencia de la sesión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="c4fa2-245">Al desplegar este elemento, el informe le muestra información sobre los participantes en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="c4fa2-246">Para obtener más información, &quot;vea la sección métricas&quot; de los participantes de la Conferencia más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-247"><strong>Organizador</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-248">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-249">Dirección SIP del usuario que organizó la conferencia</span><span class="sxs-lookup"><span data-stu-id="c4fa2-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-251">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-252">Nombre del servidor perimetral (si lo hay) usado en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-253"><strong>Hora de inicio</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-254">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-255">Fecha y hora en las que comenzó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-256"><strong>Hora de finalización</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-257">Sí</span><span class="sxs-lookup"><span data-stu-id="c4fa2-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-258">Fecha y hora en que la conferencia finalizó.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="c4fa2-259">Métricas de los participantes en conferencias</span><span class="sxs-lookup"><span data-stu-id="c4fa2-259">Metrics for conference participants</span></span>

<span data-ttu-id="c4fa2-260">En la tabla siguiente se muestra la información que recoge el informe de actividad de usuario sobre cada participante en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="c4fa2-261">Métricas de los participantes en conferencias</span><span class="sxs-lookup"><span data-stu-id="c4fa2-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4fa2-262">Nombre</span><span class="sxs-lookup"><span data-stu-id="c4fa2-262">Name</span></span></th>
<th><span data-ttu-id="c4fa2-263">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="c4fa2-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c4fa2-264">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4fa2-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-265"><strong>Rol</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-266">No</span><span class="sxs-lookup"><span data-stu-id="c4fa2-266">No</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-267">Rol del usuario en la conferencia (por ejemplo, moderador).</span><span class="sxs-lookup"><span data-stu-id="c4fa2-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-268"><strong>Participante</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-269">No</span><span class="sxs-lookup"><span data-stu-id="c4fa2-269">No</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-270">Dirección SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-271"><strong>Conectividad</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-272">No</span><span class="sxs-lookup"><span data-stu-id="c4fa2-272">No</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-273">Tipo de conexión de red.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-273">Network connection type.</span></span> <span data-ttu-id="c4fa2-274">Por ejemplo &quot;, desde&quot; Internal para la conexión &quot;interna o&quot; desde RTC para usuarios de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-275"><strong>Hora de conexión</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-276">No</span><span class="sxs-lookup"><span data-stu-id="c4fa2-276">No</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-277">Fecha y hora en las que el usuario se unió a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fa2-278"><strong>Hora de desconexión</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-279">No</span><span class="sxs-lookup"><span data-stu-id="c4fa2-279">No</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-280">Fecha y hora en las que el usuario dejó la conferencia.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fa2-281"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="c4fa2-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c4fa2-282">No</span><span class="sxs-lookup"><span data-stu-id="c4fa2-282">No</span></span></p></td>
<td><p><span data-ttu-id="c4fa2-p125">Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores. Los encabezados de diagnóstico son opcionales (es posible que haya sesiones SIP que no incluyan estos encabezados) y los identificadores de diagnóstico se notifican únicamente para las sesiones que tienen problemas de algún tipo.</span><span class="sxs-lookup"><span data-stu-id="c4fa2-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

