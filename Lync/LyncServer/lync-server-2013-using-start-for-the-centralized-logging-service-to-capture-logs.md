---
title: Uso de inicio para el servicio de registro centralizado para capturar registros
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f43a2c86dcbd88f8e9af4ae54f302b4abc943fc0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529977"
---
# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="63af0-102">Uso de inicio para el servicio de registro centralizado para capturar registros en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63af0-102">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63af0-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="63af0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="63af0-104">Para capturar registros de seguimiento mediante el servicio de registro centralizado, se emite un comando para iniciar el registro en uno o más equipos y grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="63af0-104">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="63af0-105">También se emiten parámetros que definen qué equipos o grupos de servidores, qué escenarios se deben ejecutar (por ejemplo, AlwaysOn, otro escenario predefinido o un escenario creado), qué componentes de Lync Server (por ejemplo, S4, SipStack) se trazarán.</span><span class="sxs-lookup"><span data-stu-id="63af0-105">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="63af0-106">Para capturar la información correcta, asegúrese de que utiliza el escenario correcto para recopilar información relevante al problema.</span><span class="sxs-lookup"><span data-stu-id="63af0-106">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="63af0-107">En el servicio de registro centralizado, un escenario es el concepto de activar el registro en función de una colección de componentes de servidor, niveles de registro e indicadores, que es mucho más eficiente y útil que tener que definir estos elementos por cada servidor.</span><span class="sxs-lookup"><span data-stu-id="63af0-107">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="63af0-108">Debe definir y especificar un escenario para que se ejecute de forma homogénea en todos los servidores y grupos de servidores de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="63af0-108">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="63af0-p103">El escenario predeterminado se denomina **AlwaysOn**. El propósito de este escenario es ejecutarse constantemente, tal como el nombre indica. El escenario AlwaysOn recopila datos de nivel de información (tenga en cuenta que el nivel de registro de información incluye los errores irrecuperables, los errores y las advertencias, además de los mensajes de información) para muchos de los componentes de servidores más comunes. AlwaysOn recopila información antes, durante y después de que se produzca un problema. Esto supone una drástica diferencia con respecto al comportamiento típico de las herramientas de registro anteriores como, por ejemplo, OCSLogger. OCSLogger se ejecutaba después de que se hubiera producido el problema, lo que dificultaba la tarea de resolución de problemas, ya que los datos con los que se trabajaba eran reactivos y no proactivos. En caso de que AlwaysOn no contenga la información que busca para identificar el componente que presenta el problema e indicar la acción que debe llevar a cabo para corregirlo (cosa poco probable dada la amplitud y la profundidad que caracterizan a los proveedores de AlwaysOn), siempre mostrará información razonable que le ayude a determinar qué acción debe llevar a cabo como, por ejemplo, crear un nuevo escenario, recopilar más datos, ejecutar una búsqueda diferente para recopilar detalles más específicos, etc.</span><span class="sxs-lookup"><span data-stu-id="63af0-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="63af0-116">El servicio de registro centralizado ofrece dos maneras de emitir comandos.</span><span class="sxs-lookup"><span data-stu-id="63af0-116">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="63af0-117">Una cantidad de temas se ha centrado en el uso de Windows PowerShell a través del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="63af0-117">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="63af0-118">La capacidad de usar varias configuraciones y comandos complejos favorece el uso del servicio de registro centralizado de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63af0-118">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="63af0-119">Como Windows PowerShell a través del shell de administración de Lync Server es casi omnipresente para todas las funciones de Lync Server, solo se analizan los comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63af0-119">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="63af0-120">Si decide usar el conjunto de comandos limitado disponible en la línea de comandos, puede obtener ayuda con CLSController.exe escribiendo <CODE>ClsController.exe</CODE> .</span><span class="sxs-lookup"><span data-stu-id="63af0-120">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="63af0-121">De forma predeterminada, <STRONG>ClsController.exe</STRONG> se instala en el directorio C:\Archivos de Programa\microsoft Lync Server 2013 \ ClsAgent.</span><span class="sxs-lookup"><span data-stu-id="63af0-121">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="63af0-122">Para ejecutar Start-CsClsLogging con Windows PowerShell con comandos básicos</span><span class="sxs-lookup"><span data-stu-id="63af0-122">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="63af0-123">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="63af0-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="63af0-124">Inicie un escenario de registro con el servicio de registro centralizado; para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="63af0-124">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="63af0-125">Por ejemplo, para iniciar el escenario **AlwaysOn**, escriba:</span><span class="sxs-lookup"><span data-stu-id="63af0-125">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="63af0-126">El escenario AlwaysOn no tiene duración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="63af0-126">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="63af0-127">Este escenario permanecerá en ejecución hasta que lo detenga explícitamente con el cmdlet <STRONG>Stop-CsClsLogging</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="63af0-127">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="63af0-128">Para obtener más detalles, vea <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="63af0-128">For details, see <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="63af0-129">Para el resto de escenarios, la duración predeterminada es de 4 horas.</span><span class="sxs-lookup"><span data-stu-id="63af0-129">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="63af0-130">Presione Entrar para ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="63af0-130">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="63af0-131">La ejecución de los comandos y la recepción de datos de estado de los equipos de su implementación pueden llevar algo de tiempo (de 30 a 60 segundos).</span><span class="sxs-lookup"><span data-stu-id="63af0-131">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="63af0-132">![Ejecutar Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Ejecutar Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="63af0-132">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="63af0-133">Para iniciar otro escenario, use el cmdlet **Start-CsClsLogging** con el nombre del escenario adicional que desee ejecutar tal como se muestra a continuación (por ejemplo, el escenario **Authentication**):</span><span class="sxs-lookup"><span data-stu-id="63af0-133">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="63af0-134">Puede tener un total de hasta dos escenarios en ejecución a la vez en un mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="63af0-134">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="63af0-135">Si el comando tiene un ámbito global, todos los equipos de su implementación ejecutarán el escenario o los escenarios.</span><span class="sxs-lookup"><span data-stu-id="63af0-135">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="63af0-136">Para iniciar un tercer escenario, deberá detener el registro en el equipo, grupo de equipos, sitio o ámbito global en el que desee ejecutar el nuevo escenario.</span><span class="sxs-lookup"><span data-stu-id="63af0-136">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="63af0-137">En caso de que haya iniciado un ámbito global, detenga el registro de uno o ambos escenarios en uno o varios de los equipos o grupos de equipos.</span><span class="sxs-lookup"><span data-stu-id="63af0-137">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="63af0-138">Para obtener más información sobre cómo administrar los escenarios que se están ejecutando, consulte <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">uso de STOP para el servicio de registro centralizado en Lync Server 2013</A> y <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="63af0-138">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="63af0-139">Para ejecutar Start-CsClsLogging con Windows PowerShell con comandos avanzados</span><span class="sxs-lookup"><span data-stu-id="63af0-139">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="63af0-140">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="63af0-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="63af0-141">Puede utilizar parámetros adicionales para administrar los comandos de registro.</span><span class="sxs-lookup"><span data-stu-id="63af0-141">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="63af0-142">Use el parámetro –Duration para ajustar el tiempo que se ejecutará el escenario.</span><span class="sxs-lookup"><span data-stu-id="63af0-142">You can use –Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="63af0-143">También puede definir el parámetro –Computers, que representa una lista de nombres de dominio completo (FQDN) de equipos separados por coma o el parámetros, o el parámetro –Pools, que representa una lista de FQDN separada por comas de grupos de equipos para los que desea ejecutar el registro.</span><span class="sxs-lookup"><span data-stu-id="63af0-143">You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="63af0-144">Inicia una sesión de registro para el escenario de *UserReplicator* en el grupo de servidores "pool01.contoso.net".</span><span class="sxs-lookup"><span data-stu-id="63af0-144">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="63af0-145">Defina también la duración de la sesión de registro en 8 horas.</span><span class="sxs-lookup"><span data-stu-id="63af0-145">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="63af0-146">Para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="63af0-146">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="63af0-147">La correcta ejecución de este escenario devuelve un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="63af0-147">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="63af0-148">![Ejecutar Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Ejecutar Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="63af0-148">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="63af0-149">Tenga en cuenta que en este ejemplo, el escenario AlwaysOn está en ejecución junto con el escenario UserReplicator.</span><span class="sxs-lookup"><span data-stu-id="63af0-149">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="63af0-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63af0-150">See Also</span></span>


[<span data-ttu-id="63af0-151">Información general sobre el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63af0-151">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

