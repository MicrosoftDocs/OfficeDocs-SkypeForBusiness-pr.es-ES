---
title: Administrar las opciones de configuración del servicio de registro centralizado en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Resumen: obtenga información sobre cómo recuperar, actualizar y crear opciones de configuración para el servicio de registro centralizado en Skype Empresarial Server 2015.'
ms.openlocfilehash: dd292465d65116dc1f497a733ca8e010e57b9137
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835160"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="d80ee-103">Administrar las opciones de configuración del servicio de registro centralizado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d80ee-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="d80ee-104">**Resumen:** Obtenga información sobre cómo recuperar, actualizar y crear opciones de configuración para el servicio de registro centralizado en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d80ee-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="d80ee-105">El servicio de registro centralizado se controla y configura mediante la configuración y los parámetros creados y usados por el controlador de servicio de registro centralizado (CLSController) para enviar comandos al agente de servicio de registro centralizado (CLSAgent) del equipo individual.</span><span class="sxs-lookup"><span data-stu-id="d80ee-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="d80ee-106">El agente procesa los comandos que se le envían y , en el caso de un comando Start, usa la configuración de los escenarios, proveedores, duración de seguimiento y marcas para empezar a recopilar registros de seguimiento según la información de configuración proporcionada.</span><span class="sxs-lookup"><span data-stu-id="d80ee-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="d80ee-107">No todos Windows PowerShell cmdlets que se enumeran para el servicio de registro centralizado están diseñados para usarse con implementaciones locales de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d80ee-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="d80ee-108">Aunque parezca que funcionan, los cmdlets siguientes no están diseñados para funcionar con implementaciones locales de Skype Empresarial Server 2015:</span><span class="sxs-lookup"><span data-stu-id="d80ee-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="d80ee-109">**Cmdlets CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)y [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d80ee-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="d80ee-110">**Cmdlets de CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) y [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d80ee-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="d80ee-111">**Cmdlets CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)y [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d80ee-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="d80ee-112">La configuración definida en estos cmdlets no obstaculizará ni provocará ningún comportamiento adverso, pero está diseñada para su uso con Microsoft 365 u Office 365 y no dará los resultados esperados en implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="d80ee-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="d80ee-113">Lo cual no significa que estos cmdlets no sirvan para las implementaciones locales, sino que lo cierto es que tienen un uso más avanzado que no se aborda en esta documentación.</span><span class="sxs-lookup"><span data-stu-id="d80ee-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="d80ee-114">El servicio de registro centralizado se puede ejecutar en un ámbito que incluya un único equipo o un grupo de equipos, en un ámbito de sitio (es decir, un sitio definido como el sitio Redmond que contiene una colección de equipos y grupos de servidores de la implementación) o en un ámbito global (es decir, todos los equipos y grupos de la implementación).</span><span class="sxs-lookup"><span data-stu-id="d80ee-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="d80ee-115">Para configurar el ámbito del servicio de registro centralizado mediante el Shell de administración de Skype Empresarial Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="d80ee-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="d80ee-116">Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC personalizados que haya creado usted mismo), ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server o desde el símbolo del sistema Windows PowerShell voz:</span><span class="sxs-lookup"><span data-stu-id="d80ee-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="d80ee-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d80ee-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="d80ee-118">Existen diferencias fundamentales entre los comandos de línea de comandos que puede ejecutar en Windows PowerShell o CLSController.</span><span class="sxs-lookup"><span data-stu-id="d80ee-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="d80ee-119">Windows PowerShell proporciona un método enriquecido para configurar y definir escenarios, y para reutilizar esos escenarios de una manera significativa para los escenarios de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="d80ee-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="d80ee-120">Aunque CLSController ofrece una manera rápida y eficaz de ejecutar comandos y obtener resultados, el conjunto de comandos de CLSController se limita al número finito de comandos que hay disponibles en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d80ee-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="d80ee-121">A diferencia de los cmdlets Windows PowerShell, CLSController no puede definir nuevos escenarios, administrar el ámbito en un sitio o nivel global, y muchas otras limitaciones de un conjunto de comandos finito que no se puede configurar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="d80ee-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="d80ee-122">Aunque CLSController proporciona un medio para una ejecución rápida, Windows PowerShell proporciona un medio para ampliar la funcionalidad del servicio de registro centralizado más allá de lo que es posible con CLSController.</span><span class="sxs-lookup"><span data-stu-id="d80ee-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="d80ee-123">Se puede definir un ámbito de equipo único durante la ejecución de un comando [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) y [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) mediante el parámetro -Computers.</span><span class="sxs-lookup"><span data-stu-id="d80ee-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="d80ee-124">El parámetro -Computers acepta una lista separada por comas de nombres de dominio completos (FQDN) para el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="d80ee-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="d80ee-125">También puede definir -Pools y una lista separada por comas de los grupos en los que desea ejecutar los comandos de registro.</span><span class="sxs-lookup"><span data-stu-id="d80ee-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="d80ee-126">Los ámbitos de sitio y global se definen en los cmdlets **New-**, **Set-** y **Remove-** Centralized Logging Service.</span><span class="sxs-lookup"><span data-stu-id="d80ee-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="d80ee-127">En los siguientes ejemplos se muestra cómo establecer un ámbito de sitio y un ámbito global.</span><span class="sxs-lookup"><span data-stu-id="d80ee-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d80ee-128">Los comandos mostrados pueden contener parámetros y conceptos tratados en otras secciones.</span><span class="sxs-lookup"><span data-stu-id="d80ee-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="d80ee-129">Los comandos de ejemplo están diseñados para demostrar el uso del parámetro **-Identity** para definir el ámbito, y los demás parámetros se incluyen para completar y especificar el ámbito.</span><span class="sxs-lookup"><span data-stu-id="d80ee-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="d80ee-130">Para obtener más información sobre los cmdlets de **Set-CsClsConfiguration**, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="d80ee-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="d80ee-131">Para recuperar la configuración actual del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="d80ee-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="d80ee-132">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="d80ee-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d80ee-133">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d80ee-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="d80ee-134">Use los **cmdlets New-CsClsConfiguration** y **Set-CsClsConfiguration** para crear una nueva configuración o actualizar una existente. Al ejecutar **Get-CsClsConfiguration,** se muestra información similar a la siguiente captura de pantalla, donde la implementación tiene actualmente la configuración global predeterminada, pero no hay configuraciones de sitio definidas:</span><span class="sxs-lookup"><span data-stu-id="d80ee-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Salida de ejemplo de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="d80ee-136">Para recuperar la configuración actual del servicio de registro centralizado del almacén local del equipo</span><span class="sxs-lookup"><span data-stu-id="d80ee-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="d80ee-137">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="d80ee-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d80ee-138">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d80ee-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="d80ee-139">Cuando se usa el primer ejemplo en el que **Get-CsClsConfiguration** no especifica ningún parámetro, el comando hace referencia al almacén de administración central para los datos.</span><span class="sxs-lookup"><span data-stu-id="d80ee-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="d80ee-140">Si especifica el parámetro -LocalStore, el comando hace referencia al equipo LocalStore en lugar del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="d80ee-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="d80ee-141">Para recuperar la lista de los escenarios actualmente definidos</span><span class="sxs-lookup"><span data-stu-id="d80ee-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="d80ee-142">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="d80ee-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d80ee-143">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d80ee-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="d80ee-144">Por ejemplo, para recuperar los escenarios definidos en el ámbito global:</span><span class="sxs-lookup"><span data-stu-id="d80ee-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="d80ee-145">El cmdlet **Get-CsClsConfiguration** siempre muestra los escenarios que forman parte de la configuración de un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="d80ee-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="d80ee-146">En la mayoría de los casos, no se muestran todos los escenarios y están truncados.</span><span class="sxs-lookup"><span data-stu-id="d80ee-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="d80ee-147">El comando usado aquí enumera todos los escenarios e información parcial acerca de los proveedores, la configuración y los indicadores que se utilizan.</span><span class="sxs-lookup"><span data-stu-id="d80ee-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="d80ee-148">Para actualizar un ámbito global para el servicio de registro centralizado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d80ee-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="d80ee-149">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="d80ee-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d80ee-150">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d80ee-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="d80ee-151">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d80ee-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="d80ee-p111">El comando indica a CLSAgent en cada equipo y grupo de la implementación que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando afectará a los equipos y grupos de todos los sitios, y establecerá el valor de sustitución del registro de seguimiento en 40 megabytes.</span><span class="sxs-lookup"><span data-stu-id="d80ee-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="d80ee-154">Para actualizar un ámbito de sitio para el servicio de registro centralizado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d80ee-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="d80ee-155">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="d80ee-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d80ee-156">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d80ee-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="d80ee-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d80ee-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="d80ee-p112">Como se indica en el ejemplo, la ubicación predeterminada de los archivos de registro es %TEMP%\Tracing. Sin embargo, como es CLSAgent quien realmente escribe en el archivo y CLSAgent se ejecuta como un servicio de red, la variable %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="d80ee-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="d80ee-p113">El comando indica a CLSAgent en cada equipo y grupo del sitio Redmond que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando no afectará a los equipos y grupos de los demás sitios, y continuarán usando el valor de sustitución del registro de seguimiento definido de forma predeterminada (20 megabytes) o al inicio de la sesión de registro.</span><span class="sxs-lookup"><span data-stu-id="d80ee-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="d80ee-162">Para crear una nueva configuración del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="d80ee-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="d80ee-163">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="d80ee-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d80ee-164">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d80ee-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="d80ee-165">New-CsClsConfiguration proporciona acceso a un gran número de opciones de configuración opcionales.</span><span class="sxs-lookup"><span data-stu-id="d80ee-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="d80ee-166">Para obtener más información sobre las opciones de configuración, consulte [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span><span class="sxs-lookup"><span data-stu-id="d80ee-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="d80ee-167">Por ejemplo, para crear una nueva configuración que define una carpeta de red para archivos de caché, el período de tiempo de sustitución para los archivos de registro y el tamaño de sustitución para los archivos de registro, escribiría:</span><span class="sxs-lookup"><span data-stu-id="d80ee-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="d80ee-168">Debe planear cuidadosamente la creación de nuevas configuraciones y cómo definir nuevas propiedades para el servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="d80ee-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="d80ee-169">Debe tener precaución a la hora de realizar cambios y asegurarse de que comprende cómo afectan a su capacidad para registrar correctamente escenarios de problemas.</span><span class="sxs-lookup"><span data-stu-id="d80ee-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="d80ee-170">Debe realizar cambios en la configuración que mejoren su capacidad para administrar los registros y establecer un tamaño y un período de sustitución que permitan resolver el problema cuando se produzca.</span><span class="sxs-lookup"><span data-stu-id="d80ee-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="d80ee-171">Para quitar una configuración existente del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="d80ee-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="d80ee-172">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="d80ee-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d80ee-173">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d80ee-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="d80ee-174">Por ejemplo, para quitar una configuración del servicio de registro centralizado que creó para aumentar el tiempo de succión del archivo de registro, aumente el tamaño del archivo de registro de suversión y establezca la ubicación de la memoria caché del archivo de registro en un recurso compartido de red de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d80ee-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="d80ee-175">Esta es la nueva configuración que se creó en el procedimiento "Para crear una nueva configuración del servicio de registro centralizado".</span><span class="sxs-lookup"><span data-stu-id="d80ee-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="d80ee-176">Si decide quitar una configuración en el nivel de sitio, el sitio usará la configuración global.</span><span class="sxs-lookup"><span data-stu-id="d80ee-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="d80ee-177">Ver también</span><span class="sxs-lookup"><span data-stu-id="d80ee-177">See also</span></span>

[<span data-ttu-id="d80ee-178">Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d80ee-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="d80ee-179">Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d80ee-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="d80ee-180">Servicio de registro centralizado en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="d80ee-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="d80ee-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d80ee-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="d80ee-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d80ee-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="d80ee-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d80ee-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="d80ee-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d80ee-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
