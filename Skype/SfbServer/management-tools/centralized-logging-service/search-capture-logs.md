---
title: Registros de captura de búsqueda creados por el servicio de registro centralizado en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Resumen: obtenga información sobre cómo buscar y leer registros de captura del servicio de registro centralizado en Skype Empresarial Server 2015.'
ms.openlocfilehash: 1a030e18f9e59fa26c4bd51aa8c6e69dd96004ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835130"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="76213-103">Registros de captura de búsqueda creados por el servicio de registro centralizado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="76213-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="76213-104">**Resumen:** Obtenga información sobre cómo buscar y leer registros de captura del servicio de registro centralizado en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="76213-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="76213-105">Las características de búsqueda del servicio de registro centralizado son útiles y eficaces por las siguientes razones:</span><span class="sxs-lookup"><span data-stu-id="76213-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="76213-106">Sus búsquedas y los resultados se ejecutan en un único equipo, un grupo de servidores, un sitio o un ámbito global, según el criterio que defina.</span><span class="sxs-lookup"><span data-stu-id="76213-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="76213-107">Sus búsquedas pueden ser inicialmente amplias y luego acotarse a un criterio más específico como hora, componente o equipo.</span><span class="sxs-lookup"><span data-stu-id="76213-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="76213-108">La búsqueda se hace en los mismos registros y no es necesario volver a ejecutar una sesión de registro cuando cambian los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76213-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="76213-p102">Los resultados de su búsqueda se toman de todos los equipos y los grupos de servidores del ámbito, se reúnen y se agregan en un único archivo de salida que representa todos los resultados de los criterios de búsqueda (limitado a los escenarios que se han estado ejecutando y los datos capturados por los escenarios). Utiliza herramientas familiares como **Snooper** o **Notepad** para leer el archivo de salida y los mensajes de seguimiento desde su implementación.</span><span class="sxs-lookup"><span data-stu-id="76213-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="76213-p103">El CLSAgent en cada equipo individual crea los registros en función del escenario o los escenarios (es posible ejecutar dos escenarios por equipo en cualquier momento). Los registros y sus archivos de caché e índice asociados son administrados por el CLSAgent. Cuando define y ejecuta una búsqueda, el comando de búsqueda da al CLSAgent la instrucción de qué información debe recuperarse. El CLSAgent ejecuta la consulta en los archivos de registro, los archivos de caché y los archivos de índice y devuelve los resultados de la búsqueda al CLSContoller. El CLSController recibe los resultados de búsqueda de todos los equipos y grupos de servidores en el ámbito de la búsqueda. El CLSController luego agrega (combina) los registros y los coloca en orden delta de tiempo, la entrada más antigua en primer lugar, y avanzando en el tiempo hasta la entrada más reciente en último lugar.</span><span class="sxs-lookup"><span data-stu-id="76213-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="76213-117">Después de cada búsqueda, se ejecuta el cmdlet **Sync-CsClsLogging**, que vacía el caché utilizado por búsquedas (que no debe confundirse con los archivos de caché mantenidos por el CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="76213-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="76213-118">Vaciar el caché ayuda a asegurar que haya un registro limpio y a realizar un seguimiento del búfer de captura de archivos en el CLSController para la próxima operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76213-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="76213-119">Para aprovechar al máximo el servicio de registro centralizado, necesita comprender bien cómo configurar la búsqueda para devolver solo los mensajes de seguimiento del equipo y los registros del grupo que son relevantes para el problema que está investigando.</span><span class="sxs-lookup"><span data-stu-id="76213-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="76213-120">issues</span><span class="sxs-lookup"><span data-stu-id="76213-120">issues</span></span>
  
<span data-ttu-id="76213-121">Para ejecutar las funciones de búsqueda del Servicio de registro centralizado mediante el Shell de administración de Skype Empresarial Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="76213-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="76213-122">Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC personalizados que haya creado usted mismo), ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server o desde el símbolo del sistema Windows PowerShell usuario:</span><span class="sxs-lookup"><span data-stu-id="76213-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="76213-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76213-123">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="76213-124">El resto de este tema se centra en cómo definir una búsqueda para optimizar su resolución de problemas.</span><span class="sxs-lookup"><span data-stu-id="76213-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="76213-125">Para ejecutar una búsqueda básica mediante el servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="76213-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="76213-126">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="76213-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="76213-127">Asegúrese de que el escenario AlwaysOn se encuentra en ejecución en su implementación en el ámbito global y luego escriba lo siguiente en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="76213-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="76213-128">Por defecto, Search-CsClsLogging envía los resultados de la búsqueda a la consola.</span><span class="sxs-lookup"><span data-stu-id="76213-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="76213-129">Si desea guardar los resultados de la búsqueda en un archivo, use -OutputFilePath  _\<string fully qualified file path\>_ .</span><span class="sxs-lookup"><span data-stu-id="76213-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="76213-130">Para definir el parámetro -OutputFilePath, proporcione una ruta de acceso y un nombre de archivo como parte del parámetro en un formato de cadena entre comillas (por ejemplo, C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="76213-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="76213-131">En este ejemplo, debe asegurarse de que exista el directorio C:\LogFiles y de que tenga los permisos de lectura y escritura (permiso NTFS Modificar) de archivos de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="76213-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="76213-132">El resultado se anexa y no se sobreescribe.</span><span class="sxs-lookup"><span data-stu-id="76213-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="76213-133">Si necesita archivos independientes, defina un nombre de archivo diferente para cada búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76213-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="76213-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76213-134">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="76213-135">Para ejecutar una búsqueda básica en un grupo o equipo mediante el servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="76213-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="76213-136">Para limitar la búsqueda a un equipo o grupo de servidores específicos, use el parámetro -Computers con el equipo definido por un nombre completo del equipo, entre comillas y separado por una coma de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="76213-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="76213-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76213-137">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="76213-138">Para buscar más de un equipo, escriba varios nombres de equipos encerrados entre comillas y separados por comas, como por ejemplo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="76213-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="76213-139">Si necesita buscar en un grupo de servidores completo en lugar de en un único equipo, cambie el parámetro -Computers a -Pools, quite el nombre del equipo y reemplázalo por el grupo de servidores o grupos entre comillas separados por comas.</span><span class="sxs-lookup"><span data-stu-id="76213-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="76213-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76213-140">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="76213-141">Al usar los comandos de búsqueda, los grupos de servidores pueden ser cualquier grupo de servidores de la implementación, como grupos de servidores front-end, grupos de servidores perimetrales, grupos de servidores de chat persistente u otros que se definen como un grupo de servidores en la implementación.</span><span class="sxs-lookup"><span data-stu-id="76213-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="76213-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76213-142">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="76213-143">Para ejecutar una búsqueda utilizando los parámetros de hora</span><span class="sxs-lookup"><span data-stu-id="76213-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="76213-144">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="76213-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="76213-145">De forma predeterminada, la hora de inicio de los parámetros específicos del tiempo de una búsqueda es de 25 minutos antes de cinco minutos después del momento en que se inicia la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76213-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="76213-146">En otras palabras, si buscamos a las 16:00:00, la hora de inicio de la búsqueda se mostrará de 3:35:00 PM a 4:05:00 PM.</span><span class="sxs-lookup"><span data-stu-id="76213-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="76213-147">Si necesita buscar 60 minutos o 3 horas antes de la hora actual, use el parámetro -StartTime y establezca la cadena de fecha y hora para indicar la hora en la que desea que se inicie la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="76213-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="76213-148">Por ejemplo, si usa -StartTime y -EndTime para definir un intervalo de fechas y horas, puede definir una búsqueda entre las 8 a.m. y las 9 a.m. del 20/11/2012 en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="76213-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="76213-149">Puede definir la ruta de salida para que escriba los resultados en un archivo llamado c:\logfile.txt de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="76213-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="76213-150">La cadena de fecha y hora que especifique puede ser "fecha y hora" o "fecha de hora".</span><span class="sxs-lookup"><span data-stu-id="76213-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="76213-151">" El comando analizará la cadena y usará los valores adecuados para la fecha y hora, así como la configuración regional y la referencia cultural en el equipo desde el que ejecuta el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="76213-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="76213-152">Si desea recuperar registros a partir de las 11:00:00 am del 20/11/2012, defina -StartTime.</span><span class="sxs-lookup"><span data-stu-id="76213-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="76213-153">El intervalo de tiempo predeterminado para la búsqueda es de 30 minutos a menos que defina un -EndTime específico.</span><span class="sxs-lookup"><span data-stu-id="76213-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="76213-154">La búsqueda resultante devolverá registros desde el equipo o los grupos de servidores definidos desde las 11:00:00 hasta las 11:30:00.</span><span class="sxs-lookup"><span data-stu-id="76213-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="76213-155">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76213-155">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="76213-156">Para realizar una búsqueda de registros en un período de tiempo específico, defina -StartTime y -EndTime.</span><span class="sxs-lookup"><span data-stu-id="76213-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="76213-157">Necesita registros desde las 13 hasta las 14:45 en el equipo edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="76213-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="76213-158">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76213-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="76213-159">Para ejecutar una búsqueda avanzada utilizando otros criterios y opciones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="76213-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="76213-160">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="76213-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="76213-161">Para ejecutar un comando para reunir seguimientos de determinados componentes, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="76213-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="76213-162">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76213-162">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="76213-163">La búsqueda resultante devuelve todas las entradas de registro que tengan componentes de seguimiento para SIPStack, S4 y UserServices en todos los equipos y grupos de servidores en su implementación para los últimos 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="76213-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="76213-164">Para limitar la búsqueda con los mismos componentes al grupo de servidores front-end denominado pool01.contoso.net, escriba:</span><span class="sxs-lookup"><span data-stu-id="76213-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="76213-165">La lógica de búsqueda predeterminada para los comandos con varios parámetros es utilizar el conector lógico O con cada uno de los parámetros definidos.</span><span class="sxs-lookup"><span data-stu-id="76213-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="76213-166">Puede cambiar este comportamiento especificando el **parámetro -MatchAll.**</span><span class="sxs-lookup"><span data-stu-id="76213-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="76213-167">Para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="76213-167">To do this, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="76213-p114">Si sus escenarios están definidos para que se ejecuten constantemente, como AlwaysOn, o ha definido un escenario de larga ejecución, los registros podrían salir de la máquina local y pasar al recurso compartido de archivos. Define el recurso compartido de archivos utilizando el parámetro CacheFileNetworkFolder utilizando New-CsClsConfiguration para crear una nueva configuración o modificando una configuración existente con Set-CsClsConfiguration. Si no desea que la búsqueda incluya el recurso compartido de archivos en la serie de registros que se buscarán, utilice el parámetro SkipNetworkLogs de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="76213-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="76213-171">Leer registros de captura desde el servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="76213-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="76213-172">Se da cuenta de la ventaja real del servicio de registro centralizado después de ejecutar la búsqueda y tiene un archivo que puede usar para realizar un seguimiento de un problema notificado.</span><span class="sxs-lookup"><span data-stu-id="76213-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="76213-173">Hay varias formas de leer el archivo.</span><span class="sxs-lookup"><span data-stu-id="76213-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="76213-174">El archivo de salida está en un formato de texto estándar y puede usar Notepad.exe o cualquier otro programa que le permita abrir y leer un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="76213-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="76213-175">Para archivos más grandes y problemas más complejos, puede usar una herramienta como Snooper.exe diseñada para leer y analizar el resultado de registro del servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="76213-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="76213-176">Snooper se incluye con las herramientas de depuración que están disponibles como descarga independiente.</span><span class="sxs-lookup"><span data-stu-id="76213-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="76213-177">Puede descargar las herramientas de depuración aquí: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257) .</span><span class="sxs-lookup"><span data-stu-id="76213-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="76213-178">Al instalar las herramientas de depuración, no se crean cortas ni elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="76213-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="76213-179">Después de instalar las herramientas de depuración, abra el Explorador de Windows, una ventana de línea de comandos o el Shell de administración de Skype Empresarial Server y vaya al directorio (ubicación predeterminada) C:\Archivos de programa\Skype Empresarial Server 2015\Herramientas de depuración.</span><span class="sxs-lookup"><span data-stu-id="76213-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="76213-180">Haga doble clic Snooper.exe o escriba Snooper.exe y, a continuación, presione ENTRAR si usa la línea de comandos o el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="76213-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="76213-181">La finalidad de este tema no es dar información detallada ni tratar las técnicas de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="76213-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="76213-182">La solución de problemas y los procesos relacionados con esta son un tema muy complejo.</span><span class="sxs-lookup"><span data-stu-id="76213-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="76213-183">Para obtener más información sobre la solución de problemas básicos y la solución de problemas de cargas de trabajo específicas, consulte el libro del Kit de recursos de Microsoft Lync Server 2010 en [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003) .</span><span class="sxs-lookup"><span data-stu-id="76213-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="76213-184">Los procesos y procedimientos se siguen aplicando a Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="76213-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="76213-185">Para abrir un archivo de registro en Snooper:</span><span class="sxs-lookup"><span data-stu-id="76213-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="76213-p117">Para usar Snooper y abrir archivos de registro, debe tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="76213-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="76213-188">Después de instalar las herramientas de depuración (LyncDebugTools.msi), cambia el directorio a la ubicación de Snooper.exe mediante el Explorador de Windows o desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="76213-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="76213-189">De forma predeterminada, las herramientas de depuración se encuentran en C:\Archivos de programa\Skype Empresarial Server 2015\Herramientas de depuración.</span><span class="sxs-lookup"><span data-stu-id="76213-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="76213-190">Haga doble clic en Snooper.exe o ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="76213-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="76213-191">Tras abrir Snooper, haga clic con el botón secundario en **Archivo**, haga clic en **Abrir archivo**, localice los archivos de registro, seleccione un archivo en el cuadro de diálogo **Abrir** y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="76213-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="76213-192">Los mensajes de seguimiento **del** archivo de registro se muestran en la **pestaña** Seguimiento. Haga clic **en la pestaña** Mensajes para ver el contenido del mensaje de los seguimientos recopilados.</span><span class="sxs-lookup"><span data-stu-id="76213-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="76213-193">Para mostrar un diagrama de flujo de llamada:</span><span class="sxs-lookup"><span data-stu-id="76213-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="76213-p119">Para usar Snooper y abrir archivos de registro, debe tener acceso de lectura a los archivos de registro. Para usar Snooper y tener acceso a los archivos de registro debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o de un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="76213-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="76213-196">Abra el archivo de registro y haga clic en la pestaña **Mensajes**, seleccione una conversación en la vista de mensajes o seleccione un componente de seguimiento en la pestaña **Seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="76213-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="76213-197">Haga clic en **Flujo de llamada**.</span><span class="sxs-lookup"><span data-stu-id="76213-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="76213-198">Si hace clic en un mensaje o seguimiento que no forma parte de un flujo de llamada, el diagrama no aparecerá y aparecerá un mensaje de estado en la parte inferior de Snooper que indica "Este mensaje no es apto para el mensaje de llamada".</span><span class="sxs-lookup"><span data-stu-id="76213-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="76213-199">Elija otro mensaje o seguimiento, y el flujo de llamada aparecerá si el mensaje o seguimiento forma parte del flujo de llamada.</span><span class="sxs-lookup"><span data-stu-id="76213-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="76213-200">Desplácese por las líneas de mensajes o seguimientos y observe si el diagrama de flujo de llamada se actualiza o cambia para mostrar un diagrama nuevo.</span><span class="sxs-lookup"><span data-stu-id="76213-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="76213-201">Pase el mouse por encima de los elementos para obtener información sobre los mensajes de llamadas, los extremos y otros componentes.</span><span class="sxs-lookup"><span data-stu-id="76213-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
