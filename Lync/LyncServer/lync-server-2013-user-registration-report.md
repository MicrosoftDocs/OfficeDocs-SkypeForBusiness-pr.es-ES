---
title: 'Lync Server 2013: informe de registro de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd7ff808b766d7366e39595a46d1a2d7dfb75996
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="4497f-102">Informe de registro de usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4497f-102">User Registration Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4497f-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="4497f-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="4497f-104">El informe de registro de usuario proporciona una introducción a la actividad de inicio de sesión de usuario, más concretamente información sobre el número de usuarios que iniciaron sesión en Microsoft Lync Server 2013 durante un período de tiempo especificado (cada hora, diariamente, semanalmente, mensualmente).</span><span class="sxs-lookup"><span data-stu-id="4497f-104">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="4497f-105">Tenga en cuenta que el informe solo indica cuántas personas han iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="4497f-105">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="4497f-106">No indica *qué* personas iniciaron sesión.</span><span class="sxs-lookup"><span data-stu-id="4497f-106">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="4497f-107">Los informes de supervisión no proporcionan información sobre qué usuarios específicos usan Lync Server 2013 (y cuáles no).</span><span class="sxs-lookup"><span data-stu-id="4497f-107">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="4497f-108">Sin embargo, puede usar el Informe de actividad de usuario para obtener una estimación de la información de usuarios.</span><span class="sxs-lookup"><span data-stu-id="4497f-108">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="4497f-109">Al proporcionar información sobre el inicio de sesión de los usuarios, el Informe de registro de usuario hace dos distinciones.</span><span class="sxs-lookup"><span data-stu-id="4497f-109">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="4497f-110">En primer lugar, desglosa los inicios de sesión en dos categorías: inicios de sesión internos y externos.</span><span class="sxs-lookup"><span data-stu-id="4497f-110">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="4497f-111">Los inicios de sesión internos corresponden a usuarios que iniciaron sesión desde dentro del firewall de la organización (es decir, mientras estaban conectados a la red corporativa).</span><span class="sxs-lookup"><span data-stu-id="4497f-111">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="4497f-112">Los inicios de sesión externos representan a los usuarios que iniciaron sesión desde fuera del Firewall a través de un servidor perimetral (por ejemplo, un usuario que inició sesión desde una cafetería de Internet cuenta como un inicio de sesión externo).</span><span class="sxs-lookup"><span data-stu-id="4497f-112">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="4497f-113">Puede usar el Informe de registro de usuario para saber cuántos de sus usuarios han iniciado sesión desde fuera del firewall.</span><span class="sxs-lookup"><span data-stu-id="4497f-113">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="4497f-114">Además, el Informe de registro de usuario indica el número de usuarios *activos* presentes en un periodo determinado.</span><span class="sxs-lookup"><span data-stu-id="4497f-114">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="4497f-115">Un usuario activo es un usuario que participó en una sesión de mensajería instantánea (mi), participó en una reunión de Lync, realizó o recibió una llamada telefónica o usó Lync Server de otro modo durante ese período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="4497f-115">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="4497f-116">No debe confundirse este tipo de usuario con los usuarios que hayan iniciado sesión y que nunca hayan usado el sistema.</span><span class="sxs-lookup"><span data-stu-id="4497f-116">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="4497f-117">Acceso al Informe de registro de usuario</span><span class="sxs-lookup"><span data-stu-id="4497f-117">Accessing the User Registration Report</span></span>

<span data-ttu-id="4497f-p104">Puede tener acceso al Informe de registros de usuario únicamente desde la página de inicio de los informes de supervisión. El Informe de registro de usuario no está vinculado a ningún otro informe.</span><span class="sxs-lookup"><span data-stu-id="4497f-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="4497f-120">Cómo sacar el máximo partido al Informe de registro de usuario</span><span class="sxs-lookup"><span data-stu-id="4497f-120">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="4497f-121">Una vez que haya implementado Lync Server, una de las preguntas más frecuentes es la siguiente: ¿Cómo sé si los usuarios están usando esta nueva tecnología?</span><span class="sxs-lookup"><span data-stu-id="4497f-121">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="4497f-122">Aunque existen algunas limitaciones al respecto, el Informe de registro de usuario puede ayudarle a encontrar una respuesta para esta pregunta.</span><span class="sxs-lookup"><span data-stu-id="4497f-122">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="4497f-123">Para determinar si los usuarios usan Lync Server, debe hacer dos cosas.</span><span class="sxs-lookup"><span data-stu-id="4497f-123">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="4497f-124">En primer lugar, deberá obtener el valor de la métrica Usuarios de inicios de sesión distintos del Informe de registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="4497f-124">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="4497f-125">Este valor indica el número de personas diferenciadas que han iniciado sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4497f-125">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="4497f-126">En comparación, la métrica de inicios de sesión totales muestra el número de veces total que alguien inició sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4497f-126">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="4497f-127">Por ejemplo, supongamos que Ken Myer inició sesión en Lync Server cinco veces distintas en un solo día.</span><span class="sxs-lookup"><span data-stu-id="4497f-127">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="4497f-128">En ese caso, Ken Myer contará con cinco sesiones de inicio de sesión independientes para la métrica de inicios de sesión totales, pero solo un usuario de inicio de sesión para la métrica de usuarios de inicio de sesión únicos.</span><span class="sxs-lookup"><span data-stu-id="4497f-128">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="4497f-129">Del mismo modo, no es raro que un usuario inicie sesión desde varios dispositivos o en varias ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="4497f-129">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="4497f-130">Por ejemplo, un usuario puede iniciar sesión con su equipo de escritorio, su equipo portátil y puede tener un teléfono IP que inicie sesión automáticamente en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4497f-130">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="4497f-131">En este ejemplo, hay un usuario único con tres inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="4497f-131">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="4497f-132">Para explicar la diferencia entre inicios de sesión únicos y totales, es necesario considerar los inicios de sesión que se producen durante un periodo determinado en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4497f-132">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4497f-133">Usuario</span><span class="sxs-lookup"><span data-stu-id="4497f-133">User</span></span></th>
<th><span data-ttu-id="4497f-134">Hora de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="4497f-134">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4497f-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4497f-135">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="4497f-136">7/7/2012 8:45 am</span><span class="sxs-lookup"><span data-stu-id="4497f-136">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4497f-137">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4497f-137">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="4497f-138">7/7/2012 8:46 am</span><span class="sxs-lookup"><span data-stu-id="4497f-138">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4497f-139">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="4497f-139">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="4497f-140">7/7/2012 9:17 am</span><span class="sxs-lookup"><span data-stu-id="4497f-140">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4497f-141">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4497f-141">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="4497f-142">7/7/2012 9:22 am</span><span class="sxs-lookup"><span data-stu-id="4497f-142">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4497f-143">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="4497f-143">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="4497f-144">7/7/2012 9:31 am</span><span class="sxs-lookup"><span data-stu-id="4497f-144">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4497f-p107">Tenga en cuenta que existe un total de cinco inicios de sesión. Sin embargo, solo hay dos inicios de sesión únicos: Ken Myer (que ha iniciado sesión tres veces) y Pilar Ackerman (que ha iniciado sesión dos veces). Esa es la diferencia entre inicios de sesión y usuario de inicios de sesión distinto.</span><span class="sxs-lookup"><span data-stu-id="4497f-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="4497f-147">Además de conocer el número de inicios de sesión únicos, necesita saber el número total de usuarios que se han habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4497f-147">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="4497f-148">Para recuperar ese valor, abra el shell de administración de Lync Server 2013 y ejecute el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4497f-148">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="4497f-149">Si el comando anterior devuelve un valor de 1.236 y la métrica de usuarios de inicio de sesión únicos devuelve un valor promedio de 667, lo que sugiere que un poco más de la mitad de los usuarios habilitados para Lync realmente inician sesión en el sistema cada día (es decir, 667 dividido por 1.236 , que es aproximadamente 54%.</span><span class="sxs-lookup"><span data-stu-id="4497f-149">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="4497f-150">Es necesario tener en cuenta que las métricas de inicio de sesión registran los usuarios que han iniciado sesión durante el periodo especificado.</span><span class="sxs-lookup"><span data-stu-id="4497f-150">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="4497f-151">Estas métricas no registran los usuarios que ya habían iniciado sesión en el sistema.</span><span class="sxs-lookup"><span data-stu-id="4497f-151">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="4497f-152">Por ejemplo, si la métrica de Usuarios de inicios de sesión distintos muestra 667 inicios de sesión y tiene 1.236 usuarios, quiere decir que aproximadamente la mitad de los usuarios han iniciado sesión en el sistema.</span><span class="sxs-lookup"><span data-stu-id="4497f-152">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="4497f-153">Sin embargo, suponga que 300 usuarios ya habían iniciado sesión en el sistema en el momento en que comenzó a comprobar los datos de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="4497f-153">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="4497f-154">Eso significaría que en realidad tenía casi 1.000 usuarios que iniciaron sesión en Lync Server, lo que significa que más cerca de 80% de los usuarios iniciaron sesión.</span><span class="sxs-lookup"><span data-stu-id="4497f-154">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="4497f-155">También debe comparar el valor de Usuarios de inicios de sesión distintos con el valor de la métrica Usuarios activos distintos.</span><span class="sxs-lookup"><span data-stu-id="4497f-155">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="4497f-156">La métrica usuarios únicos activos indica el número de usuarios únicos que han usado Lync Server realmente: realizaron una llamada telefónica, se unieron a una reunión de Lync o participaron en una sesión de mi.</span><span class="sxs-lookup"><span data-stu-id="4497f-156">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="4497f-157">Esta información es útil porque Microsoft Lync 2013 se puede configurar para que se inicie automáticamente cada vez que un usuario inicie Windows.</span><span class="sxs-lookup"><span data-stu-id="4497f-157">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="4497f-158">Por ello, es posible que tenga un gran número de usuarios que inicien sesión automáticamente en Lync cuando inicien sesión en Windows cada día, pero no use nunca Lync Server en realidad durante ese período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="4497f-158">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="4497f-159">La métrica usuarios únicos activos también proporciona datos más significativos en una organización en la que los usuarios normalmente no cierran la sesión de Windows al final del día.</span><span class="sxs-lookup"><span data-stu-id="4497f-159">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="4497f-160">En su lugar, simplemente bloquean sus equipos y dejan Windows y Lync en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="4497f-160">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="4497f-161">En esta situación, puede registrar muy pocos inicios de sesión al día porque los usuarios simplemente iniciaron sesión hace varios días y aún mantienen la sesión iniciada.</span><span class="sxs-lookup"><span data-stu-id="4497f-161">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="4497f-162">Sin embargo, los usuarios activos únicos le indican si los usuarios están usando activamente Lync u otro cliente de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4497f-162">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4497f-163">Filtros</span><span class="sxs-lookup"><span data-stu-id="4497f-163">Filters</span></span>

<span data-ttu-id="4497f-164">Los filtros ofrecen el medio para devolver un conjunto de datos más específico o para ver los datos devueltos de diferentes formas.</span><span class="sxs-lookup"><span data-stu-id="4497f-164">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="4497f-165">Por ejemplo, el informe de registro de usuario permite ver los datos de todos los servidores del registrador y del servidor perimetral, o bien para ver los datos de un grupo individual.</span><span class="sxs-lookup"><span data-stu-id="4497f-165">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="4497f-166">También se puede elegir cómo agrupar los datos.</span><span class="sxs-lookup"><span data-stu-id="4497f-166">You can also choose how data should be grouped.</span></span> <span data-ttu-id="4497f-167">En este caso, los registros se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="4497f-167">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4497f-168">En la tabla siguiente, se muestran los filtros que se pueden utilizar en el informe de registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="4497f-168">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="4497f-169">Filtros del informe de registro de usuario</span><span class="sxs-lookup"><span data-stu-id="4497f-169">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4497f-170">Nombre</span><span class="sxs-lookup"><span data-stu-id="4497f-170">Name</span></span></th>
<th><span data-ttu-id="4497f-171">Descripción</span><span class="sxs-lookup"><span data-stu-id="4497f-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4497f-172"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4497f-p113">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="4497f-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4497f-175">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="4497f-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4497f-p114">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="4497f-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4497f-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4497f-178">7/7/2012</span></span></p>
<p><span data-ttu-id="4497f-179">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="4497f-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4497f-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4497f-180">7/3/2012</span></span></p>
<p><span data-ttu-id="4497f-181">Las semanas siempre empiezan en domingo y terminan en sábado.</span><span class="sxs-lookup"><span data-stu-id="4497f-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4497f-182"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4497f-p115">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="4497f-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4497f-185">7/7/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="4497f-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4497f-p116">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="4497f-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4497f-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4497f-188">7/7/2012</span></span></p>
<p><span data-ttu-id="4497f-189">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="4497f-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4497f-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4497f-190">7/3/2012</span></span></p>
<p><span data-ttu-id="4497f-191">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="4497f-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4497f-192"><strong>Intervalo de</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="4497f-p117">Intervalo de tiempo. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4497f-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4497f-195">Cada hora (se puede ver un máximo de 25 horas)</span><span class="sxs-lookup"><span data-stu-id="4497f-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4497f-196">Cada día (se puede ver un máximo de 31 días)</span><span class="sxs-lookup"><span data-stu-id="4497f-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4497f-197">Cada semana (se puede ver un máximo de 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="4497f-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4497f-198">Cada mes (se puede ver un máximo de 12 meses)</span><span class="sxs-lookup"><span data-stu-id="4497f-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="4497f-p118">Si las fecha de inicio y finalización superan la cantidad máxima de valores permitidos para el intervalo seleccionado, solamente se mostrará la cantidad máxima de valores (el principio será la fecha de inicio). Por ejemplo, si selecciona el intervalo Cada día con una fecha de inicio del 7/7/2012 y una fecha de finalización del 28/2/2012, aparecerán los datos correspondientes a los días entre el 8/7/2012 a las 12:00 am y el 9/7/2012 a las 12:00 am (es decir un total de 31 días de datos).</span><span class="sxs-lookup"><span data-stu-id="4497f-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4497f-201"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-201"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4497f-202">Nombre de dominio completo (FQDN) del grupo de registradores o servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="4497f-202">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="4497f-203">Puede seleccionar un grupo individual o hacer clic en <strong>[Todo]</strong> para ver los datos de todos los grupos.</span><span class="sxs-lookup"><span data-stu-id="4497f-203">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="4497f-204">Esta lista desplegable se rellena automáticamente en función de los registros de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4497f-204">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4497f-205">Métricas</span><span class="sxs-lookup"><span data-stu-id="4497f-205">Metrics</span></span>

<span data-ttu-id="4497f-206">En la tabla siguiente, se muestra la información proporcionada en el informe de registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="4497f-206">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="4497f-207">Métricas del informe de registro de usuario</span><span class="sxs-lookup"><span data-stu-id="4497f-207">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4497f-208">Nombre</span><span class="sxs-lookup"><span data-stu-id="4497f-208">Name</span></span></th>
<th><span data-ttu-id="4497f-209">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="4497f-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4497f-210">Descripción</span><span class="sxs-lookup"><span data-stu-id="4497f-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4497f-211"><strong>Cada hora</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="4497f-212"><strong>Diario</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="4497f-213"><strong>Semanal</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="4497f-214"><strong>Mensualmente</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="4497f-215">No</span><span class="sxs-lookup"><span data-stu-id="4497f-215">No</span></span></p></td>
<td><p><span data-ttu-id="4497f-p120">Indica el intervalo temporal que ha seleccionado en la barra de herramientas para filtros. Cuando corresponda, podrá hacer clic en un intervalo temporal determinado para ver información detallada para dicho intervalo. Por ejemplo, si está usando el intervalo de Cada día y hace clic en 7/7/2012, verá un desglose por horas de la actividad de registro del usuario correspondiente para esa fecha.</span><span class="sxs-lookup"><span data-stu-id="4497f-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4497f-219"><strong>Total de inicios de sesión</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-219"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="4497f-220">No</span><span class="sxs-lookup"><span data-stu-id="4497f-220">No</span></span></p></td>
<td><p><span data-ttu-id="4497f-221">Número total de sesiones de inicio correctas.</span><span class="sxs-lookup"><span data-stu-id="4497f-221">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4497f-222"><strong>Inicios de sesión internos</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-222"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="4497f-223">No</span><span class="sxs-lookup"><span data-stu-id="4497f-223">No</span></span></p></td>
<td><p><span data-ttu-id="4497f-224">Número total de inicios de sesión en la red interna.</span><span class="sxs-lookup"><span data-stu-id="4497f-224">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4497f-225"><strong>Inicios de sesión externos</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-225"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="4497f-226">No</span><span class="sxs-lookup"><span data-stu-id="4497f-226">No</span></span></p></td>
<td><p><span data-ttu-id="4497f-227">Número total de inicios de sesión realizados desde fuera de la red interna, por medio del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="4497f-227">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4497f-228"><strong>Usuarios de inicios de sesión distintos</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-228"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="4497f-229">No</span><span class="sxs-lookup"><span data-stu-id="4497f-229">No</span></span></p></td>
<td><p><span data-ttu-id="4497f-p121">Número total de usuarios con al menos una sesión de inicio. Un usuario con varias sesiones de inicio se considera un usuario, al igual que una persona con una sola sesión de inicio.</span><span class="sxs-lookup"><span data-stu-id="4497f-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4497f-232"><strong>Usuarios activos distintos</strong></span><span class="sxs-lookup"><span data-stu-id="4497f-232"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="4497f-233">No</span><span class="sxs-lookup"><span data-stu-id="4497f-233">No</span></span></p></td>
<td><p><span data-ttu-id="4497f-p122">Número total de usuarios que participaron en una sesión punto a punto o de conferencia. Un usuario con varias sesiones se considera un usuario, al igual que una persona con una sola sesión.</span><span class="sxs-lookup"><span data-stu-id="4497f-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

