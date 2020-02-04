---
title: 'Lync Server 2013: usar detener para el servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 621d7c02530fea62b1601c1db755292c8f819a6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="d174a-102">Usar detener para el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d174a-102">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d174a-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d174a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d174a-p101">Puede detener una sesión de registro que se esté ejecutando actualmente con el cmdlet Stop-CsClsLogging. Por lo general, no hay muchas situaciones en las que tenga que detener una sesión de registro. Por ejemplo, puede buscar en registros y cambiar configuraciones sin tener que detener primero el registro. Si tiene dos escenarios en ejecución, por ejemplo, AlwaysOn y UserReplicator, y tiene que recopilar información relacionada con la autenticación, tendrá que detener uno de los demás escenarios (en un ámbito global, de sitio, de grupo o de equipo) antes de poder empezar a ejecutar en el escenario de autenticación. Para más detalles, consulte [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="d174a-p101">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet. Generally, there aren’t many situations in which you would need to stop a logging session. For example, you can search logs and change configurations without first needing to stop logging. If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario. For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d174a-109">Al determinar qué escenarios puede ejecutar en una implementación, grupo de servidores o equipo determinado, debe recordar que está limitado a ejecutar dos escenarios <STRONG>por equipo</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d174a-109">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="d174a-110">Si está registrando actividad en un grupo, dicho grupo necesita considerarse como una entidad única.</span><span class="sxs-lookup"><span data-stu-id="d174a-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="d174a-111">En la mayoría de los casos, no tendría sentido ejecutar diferentes escenarios en cada equipo de un grupo.</span><span class="sxs-lookup"><span data-stu-id="d174a-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="d174a-112">Parece lógico mirar el problema sobre el que está recopilando datos y considerar qué escenario tiene más sentido en un equipo determinado en la implementación global.</span><span class="sxs-lookup"><span data-stu-id="d174a-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="d174a-113">Por ejemplo, si consideras el escenario UserReplicator, sería muy poco probable que se estuviera ejecutando UserReplicator en un servidor perimetral o un grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="d174a-113">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="d174a-p103">Tras comprender el problema y el ámbito del impacto, es preciso realizar elecciones cuidadosas sobre qué escenarios ejecutar en qué equipos y grupos. A pesar de que el escenario AlwaysOn tiene sentido para una aplicación de amplio ámbito porque recopila información en una gran variedad de proveedores, los escenarios específicos solo tienen valor de aplicación en grupos o equipos específicos. Además, necesita tener cuidado al iniciar de manera aleatoria una sesión de registro sin comprender primero el valor de un escenario determinado. Si usa el escenario incorrecto, o si usa un escenario que es adecuado para la tarea y aplica el escenario en el ámbito equivocado (ya sea global, de sitio, de grupo o de equipo), puede obtener datos cuestionables que no son muy útiles, como si no ejecutara el escenario en absoluto.</span><span class="sxs-lookup"><span data-stu-id="d174a-p103">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="d174a-118">Para controlar las funciones de los servicios de registro centralizado mediante el shell de administración de Lync Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) de CsAdministrator o CsServerAdministrator, o un rol de RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="d174a-118">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="d174a-119">Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el shell de administración de Lync Server o el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d174a-119">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="d174a-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d174a-120">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="d174a-121">Para detener una sesión del servicio de registro centralizado que se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="d174a-121">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="d174a-122">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d174a-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d174a-123">Consulte el servicio de registro centralizado para averiguar qué escenarios se están ejecutando actualmente escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d174a-123">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="d174a-124">![Consola Windows PowerShell después de llamar Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Consola Windows PowerShell después de llamar Show-CsCl")</span><span class="sxs-lookup"><span data-stu-id="d174a-124">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="d174a-p105">El resultado de Show-CsClsLogging es un resumen de los escenarios que se están ejecutando y en qué ámbito se están ejecutando. Para más detalles, consulte [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="d174a-p105">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in. For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="d174a-127">Para detener una sesión de registro actualmente en ejecución con un escenario específico, escriba:</span><span class="sxs-lookup"><span data-stu-id="d174a-127">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="d174a-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d174a-128">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="d174a-129">Este comando detendrá el registro con el escenario de UserReplicatior en pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="d174a-129">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d174a-p106">No se eliminan los registros creados durante esta sesión de registro con el escenario de UserReplicator. El registro todavía está disponible para que ejecute las búsquedas con el comando Search-CsClsLogging. Para más detalles, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="d174a-p106">Logs created during this logging session using the UserReplicator scenario are not deleted. The logging is still available for you to execute searches against using the Search-CsClsLogging command. For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="d174a-p107">Al actuar como el comando complementario para Start-CsClsLogging, el cmdlet Stop-CsClsLogging finaliza la sesión de registro, definida por los escenarios, y conserva los registros creados por la sesión de registro. Puede ejecutar dos escenarios en un equipo determinado en cualquier momento. El método de detener un escenario para recopilar información usando otro escenario es una tarea común que puede llevar a cabo durante la mayor parte de la solución de problemas de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d174a-p107">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d174a-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="d174a-136">See Also</span></span>


[<span data-ttu-id="d174a-137">Uso de iniciar para el servicio de registro centralizado para capturar registros en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d174a-137">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="d174a-138">Información general sobre el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d174a-138">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="d174a-139">Show-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="d174a-139">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="d174a-140">Start-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="d174a-140">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="d174a-141">Stop-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="d174a-141">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

