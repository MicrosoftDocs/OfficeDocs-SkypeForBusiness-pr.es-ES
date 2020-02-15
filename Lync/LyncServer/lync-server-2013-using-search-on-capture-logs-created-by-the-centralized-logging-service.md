---
title: Uso de la búsqueda en registros de captura creados por el servicio de registro centralizado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f9571f2efe08eb13091c3d3660e7760a8e805c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="abc79-102">Uso de la búsqueda en registros de captura creados por el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abc79-102">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abc79-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="abc79-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="abc79-104">Las características de búsqueda del servicio de registro centralizado son útiles y eficaces por las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="abc79-104">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="abc79-105">Sus búsquedas y los resultados se ejecutan en un único equipo, un grupo de servidores, un sitio o un ámbito global, según el criterio que defina.</span><span class="sxs-lookup"><span data-stu-id="abc79-105">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="abc79-p101">Sus búsquedas pueden ser inicialmente amplias y luego acotarse a un criterio más específico como hora, componente o equipo. Al realizar sus búsquedas en los mismos registros, no necesita volver a ejecutar una sesión de registro cuando cambian los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="abc79-p101">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer. You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="abc79-p102">Los resultados de su búsqueda se toman de todos los equipos y los grupos de servidores del ámbito, se reúnen y se agregan en un único archivo de salida que representa todos los resultados de los criterios de búsqueda (limitado a los escenarios que se han estado ejecutando y los datos capturados por los escenarios). Utiliza herramientas familiares como **Snooper** o **Notepad** para leer el archivo de salida y los mensajes de seguimiento desde su implementación.</span><span class="sxs-lookup"><span data-stu-id="abc79-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="abc79-p103">El CLSAgent en cada equipo individual crea los registros en función del escenario o los escenarios (es posible ejecutar dos escenarios por equipo en cualquier momento). Los registros y sus archivos de caché e índice asociados son administrados por el CLSAgent. Cuando define y ejecuta una búsqueda, el comando de búsqueda da al CLSAgent la instrucción de qué información debe recuperarse. El CLSAgent ejecuta la consulta en los archivos de registro, los archivos de caché y los archivos de índice y devuelve los resultados de la búsqueda al CLSContoller. El CLSController recibe los resultados de búsqueda de todos los equipos y grupos de servidores en el ámbito de la búsqueda. El CLSController luego agrega (combina) los registros y los coloca en orden delta de tiempo, la entrada más antigua en primer lugar, y avanzando en el tiempo hasta la entrada más reciente en último lugar.</span><span class="sxs-lookup"><span data-stu-id="abc79-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="abc79-116">Después de cada búsqueda, se ejecuta el cmdlet **Sync-CsClsLogging**, que vacía el caché utilizado por búsquedas (que no debe confundirse con los archivos de caché mantenidos por el CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="abc79-116">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="abc79-117">Vaciar el caché ayuda a asegurar que haya un registro limpio y a realizar un seguimiento del búfer de captura de archivos en el CLSController para la próxima operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="abc79-117">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="abc79-118">Para sacar el máximo partido del servicio de registro centralizado, necesita comprender mejor cómo configurar la búsqueda para que devuelva solo los mensajes de seguimiento del equipo y los registros de grupo que son relevantes para el problema que está investigando.</span><span class="sxs-lookup"><span data-stu-id="abc79-118">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="abc79-119">aspectos</span><span class="sxs-lookup"><span data-stu-id="abc79-119">issues</span></span>

<span data-ttu-id="abc79-120">Para ejecutar las funciones de búsqueda del servicio de registro centralizado mediante el shell de administración de Lync Server, debe ser miembro de los grupos de seguridad CsAdministrator o CsServerAdministrator role-based access control (RBAC), o un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="abc79-120">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="abc79-121">Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el shell de administración de Lync Server o el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="abc79-121">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="abc79-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc79-122">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="abc79-123">El resto de este tema se centra en cómo definir una búsqueda para optimizar su resolución de problemas.</span><span class="sxs-lookup"><span data-stu-id="abc79-123">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="abc79-124">Para ejecutar una búsqueda básica mediante el servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="abc79-124">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="abc79-125">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="abc79-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="abc79-126">Asegúrese de que el escenario AlwaysOn se encuentra en ejecución en su implementación en el ámbito global y luego escriba lo siguiente en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="abc79-126">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="abc79-127">Por defecto, Search-CsClsLogging envía los resultados de la búsqueda a la consola.</span><span class="sxs-lookup"><span data-stu-id="abc79-127">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="abc79-128">Si desea guardar los resultados de la búsqueda en un archivo, use la ruta &lt;de acceso&gt;completa del archivo de cadena de OutputFilePath.</span><span class="sxs-lookup"><span data-stu-id="abc79-128">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="abc79-129">Para definir el parámetro –OutputFilePath, suministre una ruta y un nombre de archivo como parte del parámetro en un formato de cadena encerrado entre comillas (por ejemplo; C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="abc79-129">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="abc79-130">En este ejemplo, debe asegurarse de que exista el directorio C:\LogFiles y de que tenga los permisos de lectura y escritura (permiso NTFS Modificar) de archivos de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="abc79-130">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="abc79-131">El resultado se anexa y no se sobreescribe.</span><span class="sxs-lookup"><span data-stu-id="abc79-131">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="abc79-132">Si necesita archivos independientes, defina un nombre de archivo diferente para cada búsqueda.</span><span class="sxs-lookup"><span data-stu-id="abc79-132">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="abc79-133">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc79-133">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="abc79-134">Para ejecutar una búsqueda básica en un grupo o un equipo con el servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="abc79-134">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="abc79-135">Para limitar la búsqueda a un determinado equipo o grupo de servidores, utilice el parámetro –Computers con el equipo definido por un nombre completamente calificado de equipo, encerrado entre comillas y separado por una coma de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="abc79-135">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="abc79-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc79-136">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="abc79-137">Para buscar más de un equipo, escriba varios nombres de equipos encerrados entre comillas y separados por comas, como por ejemplo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="abc79-137">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="abc79-138">Si necesita buscar un grupo de servidores entero en lugar de un único equipo, cambie el parámetro –Computers por –Pools, borre le nombre del equipo y reemplácelo con el grupo o los grupos de servidores entre comillas y separados por comas.</span><span class="sxs-lookup"><span data-stu-id="abc79-138">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="abc79-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc79-139">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="abc79-140">Cuando se usan los comandos de búsqueda, los grupos de servidores pueden ser cualquier grupo de la implementación, como los grupos de servidores front-end, los grupos de servidores perimetrales, los grupos de servidores de chat persistente u otros definidos como grupo en la implementación.</span><span class="sxs-lookup"><span data-stu-id="abc79-140">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="abc79-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc79-141">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="abc79-142">Para ejecutar una búsqueda utilizando los parámetros de hora</span><span class="sxs-lookup"><span data-stu-id="abc79-142">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="abc79-143">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="abc79-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="abc79-p108">Por defecto, la hora de inicio para los parámetros específicos de hora de una búsqueda es de 30 minutos antes de la hora en que inició la búsqueda. En otras palabras, si inicia su búsqueda a las 16:00:00, la búsqueda se hará sobre los registros para los equipos y grupos de servidores que defina desde las 15:30:00 hasta las 16:00:00. Si necesita buscar desde 60 minutos o 3 horas antes de la hora actual, utilice el parámetro –StartTime y defina la cadena de fecha y hora para indicar la hora en la que quiera que empiece la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="abc79-p108">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search. In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM. If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="abc79-147">Por ejemplo, utilizando los parámetros –StartTime y –EndTime para definir un rango de fecha y hora, puede definir una búsqueda you entre las 8 y las 9 del 20/11/2012 en su grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="abc79-147">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="abc79-148">Puede establecer la ruta de acceso de los resultados para escribir los resultados en un archivo\\denominado c: logfile. txt de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="abc79-148">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="abc79-149">La cadena de fecha y hora que especifique puede ser "fecha y hora" o "fecha de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="abc79-149">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="abc79-150">"El comando analizará la cadena y usará los valores apropiados para la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="abc79-150">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="abc79-p111">Si desea recuperar registros que comiencen a las 11:00:00 del 20/11/2012, debe definir el parámetro –StartTime. El rango de hora predeterminado para la búsqueda es de 30 minutos a menos que defina un parámetro –EndTime específico. La búsqueda resultante devolverá registros desde el equipo o los grupos de servidores definidos desde las 11:00:00 hasta las 11:30:00.</span><span class="sxs-lookup"><span data-stu-id="abc79-p111">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime. The default time range for the search is 30 minutes unless you define a specific –EndTime. The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="abc79-154">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc79-154">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="abc79-p112">Para llevar a cabo una búsqueda de registros dentro de un período de tiempo específico, defina un parámetro –StartTime y –EndTime. Necesita registros desde las 13 hasta las 14:45 en el equipo edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="abc79-p112">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime. You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="abc79-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc79-157">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="abc79-158">Para ejecutar una búsqueda avanzada utilizando otros criterios y opciones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="abc79-158">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="abc79-159">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="abc79-159">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="abc79-160">Para ejecutar un comando para reunir seguimientos de determinados componentes, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="abc79-160">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="abc79-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc79-161">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="abc79-162">La búsqueda resultante devuelve todas las entradas de registro que tengan componentes de seguimiento para SIPStack, S4 y UserServices en todos los equipos y grupos de servidores en su implementación para los últimos 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="abc79-162">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="abc79-163">Para limitar la búsqueda con los mismos componentes solo a su grupo de servidores front-end denominado pool01.contoso.net, escriba:</span><span class="sxs-lookup"><span data-stu-id="abc79-163">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="abc79-p113">La lógica de búsqueda predeterminada para los comandos con varios parámetros es utilizar el conector lógico O con cada uno de los parámetros definidos. Puede cambiar este comportamiento especificando el parámetro **–MatchAll**. Para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="abc79-p113">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters. You can change this behavior by specifying the **–MatchAll** parameter. To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="abc79-p114">Si sus escenarios están definidos para que se ejecuten constantemente, como AlwaysOn, o ha definido un escenario de larga ejecución, los registros podrían salir de la máquina local y pasar al recurso compartido de archivos. Define el recurso compartido de archivos utilizando el parámetro CacheFileNetworkFolder utilizando New-CsClsConfiguration para crear una nueva configuración o modificando una configuración existente con Set-CsClsConfiguration. Si no desea que la búsqueda incluya el recurso compartido de archivos en la serie de registros que se buscarán, utilice el parámetro SkipNetworkLogs de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="abc79-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

