---
title: Buscar registros de captura creados por el servicio de registro centralizado en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Resumen: Aprenda a buscar y leer registros de captura del servicio de registro centralizado en Skype empresarial Server 2015.'
ms.openlocfilehash: 81bf539c6a06c52354db23bbeea97fb9525cbbd5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274376"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="211bc-103">Buscar registros de captura creados por el servicio de registro centralizado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="211bc-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="211bc-104">**Resumen:** Aprenda a buscar y leer registros de captura del servicio de registro centralizado en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="211bc-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="211bc-105">Las características de búsqueda del servicio de registro centralizado son útiles y eficaces por los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="211bc-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="211bc-106">Sus búsquedas y los resultados se ejecutan en un único equipo, un grupo de servidores, un sitio o un ámbito global, según el criterio que defina.</span><span class="sxs-lookup"><span data-stu-id="211bc-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="211bc-107">Sus búsquedas pueden ser inicialmente amplias y, luego, acotarse a un criterio más específico, como la hora, el componente o el equipo.</span><span class="sxs-lookup"><span data-stu-id="211bc-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="211bc-108">Puede buscar en los mismos registros y no es necesario volver a ejecutar una sesión de registro cuando cambien los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="211bc-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="211bc-p102">Los resultados de su búsqueda se toman de todos los equipos y los grupos de servidores del ámbito, se reúnen y se agregan en un único archivo de salida que representa todos los resultados de los criterios de búsqueda (limitados a los escenarios que se han estado ejecutando y los datos capturados por los escenarios). Es posible utilizar herramientas familiares, como **Snooper** o el **Bloc de notas** para leer el archivo de salida y los mensajes de seguimiento desde la implementación.</span><span class="sxs-lookup"><span data-stu-id="211bc-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="211bc-p103">El CLSAgent en cada equipo individual crea los registros en función del escenario o los escenarios (es posible ejecutar dos escenarios por equipo en cualquier momento). El CLSAgent administra los registros y sus archivos caché e índice asociados. Cuando define y ejecuta una búsqueda, el comando de búsqueda da al CLSAgent la instrucción de qué información necesita recuperarse. El CLSAgent ejecuta la consulta en los archivos de registro, los archivos caché y los archivos de índice y devuelve los resultados de la búsqueda al CLSContoller. El CLSController recibe los resultados de búsqueda de todos los equipos y grupos de servidores en el ámbito de la búsqueda. El CLSController, luego, agrega (combina) los registros y los coloca en orden delta de tiempo, la entrada más antigua en primer lugar, y avanzando en el tiempo hasta la entrada más reciente en último lugar.</span><span class="sxs-lookup"><span data-stu-id="211bc-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="211bc-117">Después de cada búsqueda, se ejecuta el cmdlet **Sync-CsClsLogging**, que vacía la memoria caché utilizada por las búsquedas (tenga presente que no hay que confundirse con los archivos caché que mantienen CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="211bc-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="211bc-118">Vaciar la memoria caché ayuda a asegurar de que haya un registro limpio y a realizar un seguimiento del búfer de captura de archivos en el CLSController para la próxima operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="211bc-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="211bc-119">Para sacar el máximo partido del servicio de registro centralizado, necesita comprender mejor cómo configurar la búsqueda para que devuelva solo los mensajes de seguimiento del equipo y los registros de pools relacionados con el problema que está investigando.</span><span class="sxs-lookup"><span data-stu-id="211bc-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="211bc-120">problemas</span><span class="sxs-lookup"><span data-stu-id="211bc-120">issues</span></span>
  
<span data-ttu-id="211bc-121">Para ejecutar las funciones de búsqueda del servicio de registro centralizado mediante el shell de administración de Skype empresarial Server, debe ser miembro de los grupos de seguridad CsAdministrator o CsServerAdministrator de acceso basado en roles (RBAC), o un rol de RBAC personalizado. que contiene cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="211bc-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="211bc-122">Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el shell de administración de Skype empresarial Server o el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="211bc-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="211bc-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="211bc-123">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="211bc-124">El resto de este tema se centra en cómo definir una búsqueda para optimizar la resolución de problemas.</span><span class="sxs-lookup"><span data-stu-id="211bc-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="211bc-125">Para ejecutar una búsqueda básica mediante el servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="211bc-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="211bc-126">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="211bc-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="211bc-127">Asegúrese de que el escenario AlwaysOn se encuentra en ejecución en la implementación en el ámbito global y, luego, escriba lo siguiente en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="211bc-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="211bc-128">De manera predeterminada, Search-CsClsLogging envía los resultados de la búsqueda a la consola.</span><span class="sxs-lookup"><span data-stu-id="211bc-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="211bc-129">Si desea guardar los resultados de la búsqueda en un archivo, use la _ \<ruta de acceso\>_ completa del archivo-OutputFilePath.</span><span class="sxs-lookup"><span data-stu-id="211bc-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="211bc-130">Para definir el parámetro-OutputFilePath, proporcione una ruta y un nombre de archivo como parte del parámetro en un formato de cadena entre comillas (por ejemplo; C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="211bc-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="211bc-131">En este ejemplo, es preciso asegurarse de que exista el directorio C:\LogFiles y de que tenga los permisos de lectura y escritura (permiso NTFS de modificación) de archivos de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="211bc-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="211bc-132">El resultado se anexa y no se sobrescribe.</span><span class="sxs-lookup"><span data-stu-id="211bc-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="211bc-133">Si necesita archivos independientes, defina un nombre de archivo diferente para cada búsqueda.</span><span class="sxs-lookup"><span data-stu-id="211bc-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="211bc-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="211bc-134">For example:</span></span>
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="211bc-135">Para ejecutar una búsqueda básica en un grupo o equipo con el servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="211bc-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="211bc-136">Para limitar la búsqueda a un equipo o grupo de servidores específico, use el parámetro-Computers con el equipo definido por un nombre completo de equipo, entre comillas y separados por una coma de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="211bc-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="211bc-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="211bc-137">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="211bc-138">Para buscar en más de un equipo, escriba varios nombres de equipos entre comillas y separados por comas, como, por ejemplo, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="211bc-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="211bc-139">Si necesita buscar en todo el grupo en lugar de en un solo equipo, cambie el parámetro-Computers a-Pools, quite el nombre del equipo y reemplácelo por el grupo o grupos entre comillas, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="211bc-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="211bc-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="211bc-140">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="211bc-141">Al usar los comandos de búsqueda, los grupos pueden ser cualquier grupo de la implementación, como grupos front-end, grupos de servidores perimetrales, grupos de servidores de chat persistentes o cualquier otro que se defina como un grupo en su implementación.</span><span class="sxs-lookup"><span data-stu-id="211bc-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="211bc-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="211bc-142">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="211bc-143">Para ejecutar una búsqueda utilizando los parámetros de hora</span><span class="sxs-lookup"><span data-stu-id="211bc-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="211bc-144">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="211bc-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="211bc-145">De manera predeterminada, la hora de inicio para los parámetros específicos de hora de una búsqueda es de 25 minutos antes hasta cinco minutos después de la hora en que inició la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="211bc-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="211bc-146">En otras palabras, si la búsqueda se hace a las 16:00:00, la hora de inicio de la búsqueda se mostrará desde las 15:35:00 hasta las 16:05:00.</span><span class="sxs-lookup"><span data-stu-id="211bc-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="211bc-147">Si necesita buscar 60 minutos o 3 horas antes de la hora actual, use el parámetro-StartTime y establezca la cadena de fecha y hora para indicar la hora en que desea que se inicie la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="211bc-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="211bc-148">Por ejemplo, si usa-StartTime y-EndTime para definir un intervalo de fechas y horas, puede definir una búsqueda entre 8 A.M. y 9 AM en 11/20/2012 en el grupo.</span><span class="sxs-lookup"><span data-stu-id="211bc-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="211bc-149">Puede definir la ruta de salida para que escriba los resultados en un archivo llamado c:\logfile.txt de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="211bc-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="211bc-150">La cadena de fecha y hora que especifique puede ser "fecha hora" u "hora fecha".</span><span class="sxs-lookup"><span data-stu-id="211bc-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="211bc-151">"El comando analizará la cadena y usará los valores apropiados para la fecha y hora y la configuración regional y de referencia cultural en el equipo desde el que se ejecuta el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="211bc-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="211bc-152">Si desea recuperar registros a partir de 11:00:00 AM en 11/20/2012, defina el-StartTime.</span><span class="sxs-lookup"><span data-stu-id="211bc-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="211bc-153">El intervalo de tiempo predeterminado para la búsqueda es de 30 minutos, a menos que se defina un-EndTime específico.</span><span class="sxs-lookup"><span data-stu-id="211bc-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="211bc-154">La búsqueda resultante devolverá registros desde el equipo o los grupos de servidores definidos desde las 11:00:00 hasta las 11:30:00.</span><span class="sxs-lookup"><span data-stu-id="211bc-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="211bc-155">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="211bc-155">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="211bc-156">Para realizar una búsqueda de registros dentro de un período de tiempo específico, defina a-StartTime y a-EndTime.</span><span class="sxs-lookup"><span data-stu-id="211bc-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="211bc-157">Necesita registros desde las 13 hasta las 14:45 en el equipo edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="211bc-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="211bc-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="211bc-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="211bc-159">Para ejecutar una búsqueda avanzada utilizando otros criterios y opciones de resultados</span><span class="sxs-lookup"><span data-stu-id="211bc-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="211bc-160">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="211bc-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="211bc-161">Para ejecutar un comando a fin de recopilar seguimientos de determinados componentes, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="211bc-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="211bc-162">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="211bc-162">For example:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="211bc-163">La búsqueda resultante devuelve todas las entradas de registro que tengan componentes de seguimiento para SIPStack, S4 y UserServices en todos los equipos y grupos de servidores en su implementación para los últimos 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="211bc-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="211bc-164">Para limitar la búsqueda con los mismos componentes solo a su grupo de servidores front-end denominado pool01.contoso.net, escriba:</span><span class="sxs-lookup"><span data-stu-id="211bc-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="211bc-165">La lógica de búsqueda predeterminada para los comandos con varios parámetros es utilizar el conector lógico O con cada uno de los parámetros definidos.</span><span class="sxs-lookup"><span data-stu-id="211bc-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="211bc-166">Puede cambiar este comportamiento especificando el parámetro **-MatchAll** .</span><span class="sxs-lookup"><span data-stu-id="211bc-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="211bc-167">Para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="211bc-167">To do this, type the following:</span></span>
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="211bc-p114">Si sus escenarios están definidos para que se ejecuten constantemente, como AlwaysOn, o ha definido un escenario de larga ejecución, los registros podrían salir de la máquina local y pasar al recurso compartido de archivos. Define el recurso compartido de archivos utilizando el parámetro CacheFileNetworkFolder, al utilizar New-CsClsConfiguration para crear una nueva configuración o al modificar una configuración existente con Set-CsClsConfiguration. Si no desea que la búsqueda incluya el recurso compartido de archivos en la colección de registros que se buscará, utilice el parámetro SkipNetworkLogs de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="211bc-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="211bc-171">Leer los registros de captura desde el servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="211bc-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="211bc-172">Usted se da cuenta de la ventaja real del servicio de registro centralizado después de ejecutar la búsqueda y tiene un archivo que puede usar para realizar un seguimiento de un problema que se ha notificado.</span><span class="sxs-lookup"><span data-stu-id="211bc-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="211bc-173">Hay varias formas de leer el archivo.</span><span class="sxs-lookup"><span data-stu-id="211bc-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="211bc-174">El archivo de salida tiene un formato de texto estándar y puede usar Notepad.exe o cualquier otro programa que permita abrir y leer un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="211bc-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="211bc-175">En el caso de archivos más grandes y problemas más complejos, puede usar una herramienta como Snoop. exe, que está diseñada para leer y analizar los resultados del registro desde el servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="211bc-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="211bc-176">Snooper forma parte de las herramientas de depuración disponibles como una descarga independiente.</span><span class="sxs-lookup"><span data-stu-id="211bc-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="211bc-177">Puede descargar las herramientas de depuración [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)aquí:.</span><span class="sxs-lookup"><span data-stu-id="211bc-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="211bc-178">Al instalar las herramientas de depuración, los puntos cortos y los elementos de menú no se crean.</span><span class="sxs-lookup"><span data-stu-id="211bc-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="211bc-179">Después de instalar las herramientas de depuración, abra el explorador de Windows, una ventana de línea de comandos o el shell de administración de Skype empresarial para ir al directorio (ubicación predeterminada) C:\Archivos de Files\Skype para las herramientas de depuración de Business Server 2015 \.</span><span class="sxs-lookup"><span data-stu-id="211bc-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="211bc-180">Haga doble clic en Snoop. exe o escriba Snoop. exe y, a continuación, presione Entrar si está usando la línea de comandos o el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="211bc-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="211bc-181">La finalidad de este tema no es dar información detallada ni tratar las técnicas de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="211bc-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="211bc-182">La solución de problemas y los procesos relacionados con esta son un tema muy complejo.</span><span class="sxs-lookup"><span data-stu-id="211bc-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="211bc-183">Para obtener detalles sobre la solución de problemas básicos y la solución de problemas de cargas de trabajo específicas, consulte el libro del [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)kit de recursos de 2010 de Microsoft Lync Server en.</span><span class="sxs-lookup"><span data-stu-id="211bc-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="211bc-184">Los procesos y procedimientos siguen aplicándose a Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="211bc-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="211bc-185">Para abrir un archivo de registro en Snooper</span><span class="sxs-lookup"><span data-stu-id="211bc-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="211bc-p117">Para usar Snooper y abrir archivos de registro, necesita tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro tiene que ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="211bc-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="211bc-188">Tras la instalación de las herramientas de depuración de (LyncDebugTools.msi), vaya al directorio donde se encuentra Snooper.exe con el Explorador de Windows o desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="211bc-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="211bc-189">De forma predeterminada, las herramientas de depuración se encuentran en C:\Archivos de Files\Skype para Business Server 2015 \ herramientas de depuración.</span><span class="sxs-lookup"><span data-stu-id="211bc-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="211bc-190">Haga doble clic en Snooper.exe o ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="211bc-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="211bc-191">Tras abrir Snooper, haga clic con el botón secundario en **Archivo**, haga clic en **Abrir archivo**, localice los archivos de registro, seleccione un archivo en el cuadro de diálogo **Abrir** y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="211bc-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="211bc-192">Los mensajes de **seguimiento** del archivo de registro se muestran en la pestaña **seguimiento** . Haga clic en la pestaña **mensajes** para ver el contenido del mensaje de las trazas recopiladas.</span><span class="sxs-lookup"><span data-stu-id="211bc-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="211bc-193">Para mostrar un diagrama de flujo de llamada</span><span class="sxs-lookup"><span data-stu-id="211bc-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="211bc-p119">Para usar Snooper y abrir archivos de registro, necesita tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro es preciso ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="211bc-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="211bc-196">Abra el archivo de registro y haga clic en la pestaña **Mensajes**, seleccione una conversación en la vista de mensajes o seleccione un componente de seguimiento en la pestaña **Seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="211bc-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="211bc-197">Haga clic en **Flujo de llamada**.</span><span class="sxs-lookup"><span data-stu-id="211bc-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="211bc-198">Si hace clic en un mensaje o una traza que no forma parte de un flujo de llamadas, el diagrama no aparecerá y aparecerá un mensaje de estado en la parte inferior del rastreador en el que se indica "este mensaje no es apto para callfow".</span><span class="sxs-lookup"><span data-stu-id="211bc-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="211bc-199">Elija otro mensaje o seguimiento, y el flujo de llamada aparecerá si el mensaje o seguimiento forma parte del flujo de llamada.</span><span class="sxs-lookup"><span data-stu-id="211bc-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="211bc-200">Desplácese por las líneas de mensajes o seguimientos y observe si el diagrama de flujo de llamada se actualiza o cambia para mostrar un diagrama nuevo.</span><span class="sxs-lookup"><span data-stu-id="211bc-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="211bc-201">Pase el mouse por encima de los elementos para obtener información sobre los mensajes de llamadas, los extremos y otros componentes.</span><span class="sxs-lookup"><span data-stu-id="211bc-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
