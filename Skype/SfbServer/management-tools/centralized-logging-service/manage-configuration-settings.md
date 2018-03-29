---
title: Administrar las opciones de configuración del servicio de registro centralizado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Resumen: Conozca cómo recuperar, actualizar y crear opciones de configuración para el servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: 0c4d03119a61fccd062e650c38815bee069852f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="abc3c-103">Administrar las opciones de configuración del servicio de registro centralizado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="abc3c-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="abc3c-104">**Resumen:** Aprenda a recuperar, actualizar y crear opciones de configuración para el servicio de registro centralizado en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="abc3c-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="abc3c-105">El servicio de registro centralizado está controlado y configurado por la configuración y los parámetros que se crean y utilizan el centralizado registro controlador del servicio (CLSController) para enviar comandos a (agente de servicio de registro centralizado) del equipo individuales CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="abc3c-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="abc3c-106">El agente procesa los comandos que le envían y (en el caso del comando Start) usa la configuración de los escenarios, los proveedores, la duración del seguimiento y las marcas para empezar a recopilar registros de seguimiento de acuerdo con la información de configuración facilitada.</span><span class="sxs-lookup"><span data-stu-id="abc3c-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="abc3c-107">No todos los cmdlets de Windows PowerShell para el servicio de registro centralizado está destinados con Skype para las implementaciones locales de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="abc3c-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="abc3c-108">Aunque parecen funcionar, los cmdlets siguientes no están diseñados para funcionar con Skype para las implementaciones locales de Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="abc3c-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="abc3c-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [Nueva CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)y [CsClsRegion de quitar](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="abc3c-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span> 
-  <span data-ttu-id="abc3c-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) y [CsClsSearchTerm del conjunto](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="abc3c-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>  
-  <span data-ttu-id="abc3c-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [Nueva CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)y [CsClsSecurityGroup de quitar](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="abc3c-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span> 

<span data-ttu-id="abc3c-112">La configuración definida en estos cmdlets no obstaculizar ni provocar cualquier comportamiento adverso, pero están diseñadas para su uso con Microsoft Office 365 y no producirá los resultados esperados en las implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="abc3c-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="abc3c-113">Esto no significa que estos cmdlets no sirvan para las implementaciones locales, sino que lo cierto es que tienen un uso más avanzado que no se aborda en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="abc3c-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>
  
<span data-ttu-id="abc3c-114">Se puede ejecutar el servicio de registro centralizado en un ámbito que incluye un único equipo o un grupo de equipos, en un ámbito de sitio (es decir, un sitio definido como el sitio Redmond que contiene una colección de equipo y grupos en la implementación) o en un ámbito global (es decir todos los equipos y grupos en la implementación).</span><span class="sxs-lookup"><span data-stu-id="abc3c-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>
  
<span data-ttu-id="abc3c-115">Para configurar el ámbito del servicio de registro centralizado mediante el Skype para negocios de Shell de administración de servidor, debe ser miembro de la CsAdministrator o los grupos de seguridad de CsServerAdministrator acceso basado en roles (RBAC) de control o una función personalizada de RBAC que contiene cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="abc3c-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="abc3c-116">Para devolver una lista de todas las funciones RBAC que se ha asignado este cmdlet en (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el Skype para el Shell de administración de servidor de negocios o el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="abc3c-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="abc3c-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc3c-117">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="abc3c-118">Hay diferencias fundamentales entre los comandos de línea de comandos que puede ejecutar en Windows PowerShell o CLSController.</span><span class="sxs-lookup"><span data-stu-id="abc3c-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="abc3c-119">Windows PowerShell proporciona un método completo para configurar y definir los escenarios y volver a los escenarios en forma significativa para los escenarios de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="abc3c-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="abc3c-120">Aunque CLSController ofrece una manera rápida y eficaz de emitir comandos y obtener resultados, el conjunto de comandos de CLSController se limita al número finito de comandos que hay disponibles en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="abc3c-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="abc3c-121">A diferencia de los cmdlets de Windows PowerShell, CLSController no se puede definir nuevos escenarios, administrar el ámbito en un sitio o nivel global y muchas otras limitaciones de un conjunto de comandos limitado que no se puede configurar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="abc3c-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="abc3c-122">Mientras CLSController proporciona un medio de ejecución rápida, Windows PowerShell proporciona un medio para ampliar la funcionalidad del servicio de registro centralizado más allá de lo que es posible con CLSController.</span><span class="sxs-lookup"><span data-stu-id="abc3c-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span> 
  
<span data-ttu-id="abc3c-123">Puede definirse un ámbito único equipo durante la ejecución de [Búsqueda CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Mostrar CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [CsClsLogging de inicio](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Parada CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) y [CsClsLogging de actualización](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) uso del comando-parámetro de equipos.</span><span class="sxs-lookup"><span data-stu-id="abc3c-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="abc3c-124">-Equipos parámetro acepta una lista separada por comas de nombres de dominio completo (FQDN) del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="abc3c-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="abc3c-125">También puede definir - grupos y una lista separada por comas de grupos que desea ejecutar los comandos de registro en.</span><span class="sxs-lookup"><span data-stu-id="abc3c-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span> 
  
<span data-ttu-id="abc3c-126">Ámbitos de sitio y Global se definen en los cmdlets **Nuevo**, **Set**y **Remove -** centralizada de servicio de registro.</span><span class="sxs-lookup"><span data-stu-id="abc3c-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="abc3c-127">En los siguientes ejemplos se muestra cómo establecer un ámbito de sitio y un ámbito global.</span><span class="sxs-lookup"><span data-stu-id="abc3c-127">The following examples demonstrate how to set a site and a global scope.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="abc3c-128">Los comandos que se muestran pueden contener parámetros y conceptos tratados en otras secciones.</span><span class="sxs-lookup"><span data-stu-id="abc3c-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="abc3c-129">Los comandos de ejemplo se pretenden demostrar el uso de la **-identidad** parámetro para definir el ámbito y los demás parámetros se incluyen su integridad y para especificar el ámbito.</span><span class="sxs-lookup"><span data-stu-id="abc3c-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="abc3c-130">Para obtener más información acerca de los cmdlets **Set-CsClsConfiguration** , consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="abc3c-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="abc3c-131">Para recuperar la configuración actual del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="abc3c-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="abc3c-132">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="abc3c-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="abc3c-133">Escriba lo siguiente en el símbolo de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="abc3c-133">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration
  ```

<span data-ttu-id="abc3c-134">Usar los cmdlets de **Nuevo CsClsConfiguration** y **CsClsConfiguration de conjunto** para crear una nueva configuración o para actualizar una configuración existente. Al ejecutar **Get-CsClsConfiguration**, se muestra información similar a la siguiente pantalla, donde la implementación tiene actualmente la configuración Global predeterminada, pero no hay configuraciones de sitio definidos:</span><span class="sxs-lookup"><span data-stu-id="abc3c-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>
  
![Salida de ejemplo de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="abc3c-136">Para recuperar la configuración actual del servicio de registro centralizado desde el almacén del equipo local</span><span class="sxs-lookup"><span data-stu-id="abc3c-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="abc3c-137">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="abc3c-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="abc3c-138">Escriba lo siguiente en el símbolo de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="abc3c-138">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration -LocalStore
  ```

<span data-ttu-id="abc3c-139">Cuando utilizas el primer ejemplo donde **Get CsClsConfiguration** no especifica ningún parámetro, las referencias de comandos el almacén de Administración Central para los datos.</span><span class="sxs-lookup"><span data-stu-id="abc3c-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="abc3c-140">Si se especifica el parámetro - almacénLocal, el comando hace referencia a la almacénLocal de equipo en lugar del almacén de Administración Central.</span><span class="sxs-lookup"><span data-stu-id="abc3c-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="abc3c-141">Para recuperar la lista de los escenarios actualmente definidos</span><span class="sxs-lookup"><span data-stu-id="abc3c-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="abc3c-142">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="abc3c-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="abc3c-143">Escriba lo siguiente en el símbolo de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="abc3c-143">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
  ```

    <span data-ttu-id="abc3c-144">Por ejemplo, para recuperar los escenarios definidos en el ámbito global:</span><span class="sxs-lookup"><span data-stu-id="abc3c-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
  ```
  Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
  ```

<span data-ttu-id="abc3c-145">El cmdlet **Get-CsClsConfiguration** siempre muestra los escenarios que forman parte de la configuración de un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="abc3c-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="abc3c-146">En la mayoría de los casos, no se muestran todos los escenarios y están truncados.</span><span class="sxs-lookup"><span data-stu-id="abc3c-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="abc3c-147">El comando usado aquí enumera todos los escenarios e información parcial sobre los proveedores, la configuración y las marcas que se utilizan.</span><span class="sxs-lookup"><span data-stu-id="abc3c-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="abc3c-148">Para actualizar un ámbito global para el servicio de registro centralizado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="abc3c-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="abc3c-149">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="abc3c-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="abc3c-150">Escriba lo siguiente en el símbolo de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="abc3c-150">Type the following at the command-line prompt:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  <span data-ttu-id="abc3c-151">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc3c-151">For example:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="abc3c-p111">El comando indica a CLSAgent en cada equipo y grupo de la implementación que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando afectará a los equipos y grupos de todos los sitios, y establecerá el valor de sustitución del registro de seguimiento configurado en 40 megabytes.</span><span class="sxs-lookup"><span data-stu-id="abc3c-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="abc3c-154">Para actualizar un ámbito de sitio para el servicio de registro centralizado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="abc3c-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="abc3c-155">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="abc3c-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="abc3c-156">Escriba lo siguiente en el símbolo de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="abc3c-156">Type the following at the command-line prompt:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  <span data-ttu-id="abc3c-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="abc3c-157">For example:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40  
  ```

> [!NOTE]
> <span data-ttu-id="abc3c-p112">Como se indica en el ejemplo, la ubicación predeterminada de los archivos de registro es %TEMP%\Tracing. Pero, como es CLSAgent quien realmente escribe en el archivo y CLSAgent se ejecuta como un servicio de red, la variable %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="abc3c-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span> 
  
<span data-ttu-id="abc3c-p113">El comando indica a CLSAgent en cada equipo y grupo del sitio Redmond que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando no afectará a los equipos y grupos de los demás sitios, y continuarán usando el valor de sustitución del registro de seguimiento configurado definido de forma predeterminada (20 megabytes) o al inicio de la sesión de registro.</span><span class="sxs-lookup"><span data-stu-id="abc3c-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="abc3c-162">Para crear una nueva configuración del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="abc3c-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="abc3c-163">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="abc3c-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="abc3c-164">Escriba lo siguiente en el símbolo de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="abc3c-164">Type the following at the command-line prompt:</span></span>
    
  ```
  New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
  ```

    > [!NOTE]
    > <span data-ttu-id="abc3c-165">New-CsClsConfiguration proporciona acceso a una gran cantidad de opciones de configuración opcionales.</span><span class="sxs-lookup"><span data-stu-id="abc3c-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="abc3c-166">Para obtener más información acerca de las opciones de configuración, consulte [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) y [Entendimiento centralizada de registro de configuración de servicio](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span><span class="sxs-lookup"><span data-stu-id="abc3c-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span> 
  
<span data-ttu-id="abc3c-167">Por ejemplo, para crear una configuración que define una carpeta de red para archivos caché, el período de tiempo de sustitución para los archivos de registro y el tamaño de sustitución para los archivos de registro, escribiría:</span><span class="sxs-lookup"><span data-stu-id="abc3c-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="abc3c-168">Debe planear cuidadosamente la creación de nuevas configuraciones y cómo definir nuevas propiedades para el servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="abc3c-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="abc3c-169">Hay que tener precaución a la hora de realizar cambios y asegurarse de que comprende cómo afectan a su capacidad para registrar correctamente escenarios de problemas.</span><span class="sxs-lookup"><span data-stu-id="abc3c-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="abc3c-170">Es necesario realizar cambios en la configuración que mejoren su capacidad para administrar los registros y establecer un tamaño y un período de sustitución que permitan resolver el problema cuando se produzca.</span><span class="sxs-lookup"><span data-stu-id="abc3c-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="abc3c-171">Para eliminar una configuración existente del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="abc3c-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="abc3c-172">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="abc3c-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="abc3c-173">Escriba lo siguiente en el símbolo de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="abc3c-173">Type the following at the command-line prompt:</span></span>
    
  ```
  Remove-CsClsConfiguration -Identity <scope and name>
  ```

<span data-ttu-id="abc3c-174">Por ejemplo, para quitar una configuración de servicio de registro centralizado que creó para aumentar la hora de conversión del archivo de registro, aumente el tamaño de archivo de registro de conversión y establecer la ubicación de caché de archivo de registro a un recurso compartido de red de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="abc3c-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="abc3c-175">Ésta es la configuración nueva que creó en el procedimiento "para"crear una nueva configuración del servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="abc3c-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span> 
  
<span data-ttu-id="abc3c-176">Si decide quitar una configuración de sitio, el sitio usará la configuración global.</span><span class="sxs-lookup"><span data-stu-id="abc3c-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="abc3c-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="abc3c-177">See also</span></span>

#### 

[<span data-ttu-id="abc3c-178">Configurar los proveedores de servicio de registro centralizado en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="abc3c-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)
  
[<span data-ttu-id="abc3c-179">Configurar escenarios para el servicio de registro centralizado en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="abc3c-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)
#### 

[<span data-ttu-id="abc3c-180">Servicio de registro centralizado en Skype para negocios 2015</span><span class="sxs-lookup"><span data-stu-id="abc3c-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)
#### 

[<span data-ttu-id="abc3c-181">Conjunto de CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="abc3c-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="abc3c-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="abc3c-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="abc3c-183">Nueva CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="abc3c-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="abc3c-184">Quitar CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="abc3c-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)

