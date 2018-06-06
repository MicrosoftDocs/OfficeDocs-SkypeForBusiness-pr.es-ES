---
title: Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Resumen: Obtenga información sobre cómo crear, modificar y eliminar los escenarios para el servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: d9280c8b72498e9c280ec89dfb1220a24fc154c9
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569930"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="8146c-103">Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="8146c-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8146c-104">**Resumen:** Obtenga información sobre cómo crear, modificar y eliminar los escenarios para el servicio de registro centralizado en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8146c-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8146c-105">Escenarios de definición el ámbito (es decir, global, sitio, grupo o equipo) y qué proveedores para usar en el servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="8146c-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="8146c-106">Al usar escenarios, puede habilitar o deshabilitar el seguimiento de proveedores (por ejemplo, S4, SIPStack, mensajería instantánea y presencia).</span><span class="sxs-lookup"><span data-stu-id="8146c-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="8146c-107">Al configurar un escenario, puede agrupar a todos los proveedores de una colección lógica determinada que aborda una condición para un problema concreto.</span><span class="sxs-lookup"><span data-stu-id="8146c-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="8146c-108">Si observa que debe modificarse para satisfacer la solución de problemas y registro de las necesidades de un escenario, el Skype para las herramientas de depuración de Business Server 2015 proporciona un módulo de Windows PowerShell denominado ClsScenarioEdit.psm1 que contiene una función namedEdit-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="8146c-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="8146c-109">La finalidad del módulo es editar las propiedades del escenario en cuestión.</span><span class="sxs-lookup"><span data-stu-id="8146c-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="8146c-110">En este tema se muestran ejemplos del funcionamiento de este módulo.</span><span class="sxs-lookup"><span data-stu-id="8146c-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="8146c-111">Descargue el Skype para [Herramientas de depuración](https://go.microsoft.com/fwlink/p/?LinkId=285257) de Business Server 2015 antes continuar cualquiera.</span><span class="sxs-lookup"><span data-stu-id="8146c-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8146c-112">Para cualquier ese ámbito: global, sitio, grupo o equipo, puede ejecutar un máximo de dos escenarios en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="8146c-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="8146c-113">Para determinar qué escenarios se están ejecutando actualmente, use Windows PowerShell y [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8146c-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="8146c-114">Mediante el uso de Windows PowerShell y [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), puede cambiar dinámicamente qué escenarios se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="8146c-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="8146c-115">Puede modificar qué escenarios se ejecutan durante una sesión de registro para ajustar o restringir los datos que se va a recopilar y de los proveedores.</span><span class="sxs-lookup"><span data-stu-id="8146c-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="8146c-116">Para ejecutar las funciones de servicio de registro centralizado mediante el uso de la Skype para Shell de administración de servidor empresarial, debe ser un miembro de la CsAdministrator o los grupos de seguridad de CsServerAdministrator acceso basado en roles (RBAC) del control o un rol RBAC personalizado que contiene cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="8146c-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="8146c-117">Para devolver una lista de todos los el RBAC roles que se ha asignado este cmdlet, incluidos los roles RBAC personalizados que haya creado, ejecutan el siguiente comando desde el Skype para Business Server Management Shell o el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8146c-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="8146c-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8146c-118">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="8146c-119">El resto de este tema se centra en cómo definir un escenario, modificarlo, recuperar los escenarios en ejecución, quitar un escenario y especificar qué contiene un escenario a fin de optimizar la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="8146c-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="8146c-120">Puede usar el Skype para Shell de administración de servidor empresarial para emitir los comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8146c-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="8146c-121">Cuando se usa Windows PowerShell, puede definir nuevos escenarios para su uso en las sesiones de registro.</span><span class="sxs-lookup"><span data-stu-id="8146c-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="8146c-122">Como se comentó en [Servicio de registro centralizado en Skype para profesionales de 2015](centralized-logging-service.md), los elementos de un escenario son:</span><span class="sxs-lookup"><span data-stu-id="8146c-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="8146c-123">**Proveedores de** Si está familiarizado con OCSLogger, los proveedores son los componentes que elija para indicar a OCSLogger el motor de seguimiento de qué debe recopilar los registros de.</span><span class="sxs-lookup"><span data-stu-id="8146c-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="8146c-124">Los proveedores son los mismos componentes (y, muchas veces, con los mismos nombres) que los de OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="8146c-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="8146c-125">Si no está familiarizado con OCSLogger, los proveedores son componentes específicos de roles de servidor que el servicio de registro centralizado puede recopilar los registros de.</span><span class="sxs-lookup"><span data-stu-id="8146c-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="8146c-126">Para obtener información detallada sobre la configuración de proveedores, vea [Configurar proveedores de servicio de registro centralizado en Skype para Business Server 2015](configure-providers.md).</span><span class="sxs-lookup"><span data-stu-id="8146c-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="8146c-127">**Identidad** El parámetro-Identity establece el ámbito y el nombre del escenario.</span><span class="sxs-lookup"><span data-stu-id="8146c-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="8146c-128">Por ejemplo, podría establecer un ámbito de "global" e identificar el escenario con "LyssServiceScenario".</span><span class="sxs-lookup"><span data-stu-id="8146c-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="8146c-129">Cuando se combinan las dos, definir la identidad (por ejemplo, "global/LyssServiceScenario").</span><span class="sxs-lookup"><span data-stu-id="8146c-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="8146c-130">De forma opcional, puede usar los parámetros - nombre y - primario.</span><span class="sxs-lookup"><span data-stu-id="8146c-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="8146c-131">Definir el parámetro Name para identificar de forma exclusiva el escenario.</span><span class="sxs-lookup"><span data-stu-id="8146c-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="8146c-132">Si utiliza un nombre, también debe usar primario para agregar el escenario alguna global o sitio.</span><span class="sxs-lookup"><span data-stu-id="8146c-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="8146c-133">Si usa los parámetros Name y Parent, no se puede usar el **-Identity** parámetro.</span><span class="sxs-lookup"><span data-stu-id="8146c-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="8146c-134">Para crear un escenario con el cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8146c-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8146c-135">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8146c-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8146c-136">Para crear un nuevo escenario para una sesión de registro, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) y defina el nombre del escenario (es decir, cómo se identifica de forma exclusiva identificará).</span><span class="sxs-lookup"><span data-stu-id="8146c-136">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="8146c-137">Elija un tipo de formato de registro de WPP (es decir, el preprocesador de seguimiento del software de Windows; es el predeterminado), EventLog (el formato de registro de eventos de Windows) o IISLog (el archivo de formato ASCII basado en el formato de archivo de registro de IIS).</span><span class="sxs-lookup"><span data-stu-id="8146c-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="8146c-138">Luego, defina Level y Flags tal como se definen en este tema los niveles de registro y las marcas, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8146c-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="8146c-139">Para este escenario de ejemplo, utilizaremos LyssProvider como variable de ejemplo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="8146c-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="8146c-140">Para crear un escenario con las opciones especificadas, escriba:</span><span class="sxs-lookup"><span data-stu-id="8146c-140">To create a scenario using the options defined, type:</span></span>
    
  ```
  New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
  ```

    <span data-ttu-id="8146c-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8146c-141">For example:</span></span>
    
  ```
  New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
  ```

    <span data-ttu-id="8146c-142">El formato alternativo utilizando - Name y - Parent:</span><span class="sxs-lookup"><span data-stu-id="8146c-142">The alternate format using -Name and -Parent:</span></span>
    
  ```
  New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
  ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="8146c-143">Para crear un escenario con varios proveedores por medio del cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8146c-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8146c-144">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8146c-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8146c-145">Por cada ámbito puede haber un máximo de dos escenarios.</span><span class="sxs-lookup"><span data-stu-id="8146c-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="8146c-146">Sin embargo, no está limitado a un número determinado de proveedores.</span><span class="sxs-lookup"><span data-stu-id="8146c-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="8146c-147">En este ejemplo, se supone que hemos creado tres proveedores, y que desea asignar las tres para el escenario que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="8146c-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="8146c-148">Los nombres de variable de proveedor son LyssProvider, ABServerProvider y SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="8146c-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="8146c-149">Para definir y asignar a varios proveedores para un escenario, escriba lo siguiente en un Skype para símbolo del Shell de administración de servidor empresarial o Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8146c-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
  ```
  New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
  ```

    > [!NOTE]
    > <span data-ttu-id="8146c-150">Como se conoce en Windows PowerShell, la convención para la creación de una tabla hash de los valores con `@{<variable>=<value1>, <value2>, <value>…}` se conoce assplatting.</span><span class="sxs-lookup"><span data-stu-id="8146c-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="8146c-151">Para obtener información detallada acerca de splatting en Windows PowerShell, consulte [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span><span class="sxs-lookup"><span data-stu-id="8146c-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="8146c-152">Para modificar un escenario existente con el cmdlet Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8146c-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8146c-153">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8146c-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8146c-154">Por cada ámbito puede haber un máximo de dos escenarios.</span><span class="sxs-lookup"><span data-stu-id="8146c-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="8146c-155">Puede cambiar los escenarios que estén en ejecución en cualquier momento, incluso si hay una sesión de captura de registros en proceso.</span><span class="sxs-lookup"><span data-stu-id="8146c-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="8146c-156">Si redefine los escenarios que están en ejecución, la sesión de registro actual dejará de usar el escenario que se haya quitado y empezará a usar el escenario nuevo.</span><span class="sxs-lookup"><span data-stu-id="8146c-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="8146c-157">Pero, la información de registro que se capturó con el escenario quitado se mantendrá en los registros capturados.</span><span class="sxs-lookup"><span data-stu-id="8146c-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="8146c-158">Para definir un nuevo escenario, haga lo siguiente (es decir, si la adición de un proveedor ya definido denominado "S4Provider"):</span><span class="sxs-lookup"><span data-stu-id="8146c-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
  ```
  Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
  ```

    <span data-ttu-id="8146c-159">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8146c-159">For example:</span></span>
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
  ```

    <span data-ttu-id="8146c-p112">Si desea reemplazar los proveedores, defina un único proveedor o bien una lista de proveedores separados entre sí por comas para cambiar el conjunto actual. Si solo desea reemplazar uno de los proveedores, agregue los proveedores actuales a los nuevos para crear un conjunto de proveedores distinto que contenga tanto los proveedores existentes como los nuevos. Para reemplazar todos los proveedores con un conjunto nuevo, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8146c-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
  ```
  Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
  ```

    <span data-ttu-id="8146c-163">Por ejemplo, para reemplazar el conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider:</span><span class="sxs-lookup"><span data-stu-id="8146c-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
  ```

    <span data-ttu-id="8146c-164">Para reemplazar solo el proveedor $LyssProvider del conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8146c-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
  ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="8146c-165">Para quitar un escenario existente con el cmdlet Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8146c-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8146c-166">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8146c-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8146c-167">Si desea quitar un escenario que se definió previamente, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8146c-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
  ```
  Remove-CsClsScenario -Identity <name of scope and scenario>
  ```

    <span data-ttu-id="8146c-168">Por ejemplo, para quitar el escenario definido site:Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="8146c-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
  ```
  Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
  ```

<span data-ttu-id="8146c-169">El cmdlet **Remove-CsClsScenario** quita el escenario especificado, pero siguen estando disponibles en los registros para buscar en los seguimientos que se hayan capturado.</span><span class="sxs-lookup"><span data-stu-id="8146c-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="8146c-170">Para cargar y descargar el cmdlet Edit-CsClsScenario con el módulo ClsScenarioEdit.psm1</span><span class="sxs-lookup"><span data-stu-id="8146c-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="8146c-171">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8146c-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8146c-172">El módulo CClsScenarioEdit.psm1 se proporciona como una descarga web aparte.</span><span class="sxs-lookup"><span data-stu-id="8146c-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="8146c-173">El módulo es parte de la Skype para las herramientas de depuración de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8146c-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="8146c-174">De forma predeterminada, las herramientas de depuración se instalan en el directorio C:\Archivos de programa\Skype Empresarial Server 2015\Herramientas de depuración.</span><span class="sxs-lookup"><span data-stu-id="8146c-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="8146c-175">En Windows PowerShell, escriba:</span><span class="sxs-lookup"><span data-stu-id="8146c-175">From the Windows PowerShell, type:</span></span>
    
  ```
  Import-Module "CDBurn\OCO\amd64\Support"
  ```

    > [!TIP]
    > <span data-ttu-id="8146c-176">Carga correcta del módulo vuelve a la línea de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8146c-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="8146c-177">Para confirmar que el módulo se carga y que Edit-CsClsScenario está disponible, escriba `Get-Help Edit-CsClsScenario`.</span><span class="sxs-lookup"><span data-stu-id="8146c-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="8146c-178">Tendría que ver una muestra general de la sintaxis de EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="8146c-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="8146c-179">Para descargar los módulos, escriba:</span><span class="sxs-lookup"><span data-stu-id="8146c-179">To unload the modules, type:</span></span>
    
  ```
  Remove-Module ClsController
  ```

    > [!TIP]
    > <span data-ttu-id="8146c-180">Correcta descarga de las devoluciones de módulo, en el símbolo del sistema de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8146c-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="8146c-181">Para confirmar que se descarga el módulo, escriba `Get-Help Edit-CsClsScenario`.</span><span class="sxs-lookup"><span data-stu-id="8146c-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="8146c-182">Windows PowerShell se intentará buscar la ayuda para el cmdlet y producirá un error.</span><span class="sxs-lookup"><span data-stu-id="8146c-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="8146c-183">Para quitar un proveedor existente de un escenario con el módulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="8146c-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="8146c-184">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8146c-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8146c-185">En Windows PowerShell, escriba:</span><span class="sxs-lookup"><span data-stu-id="8146c-185">From the Windows PowerShell, type:</span></span>
    
  ```
  Import-Module "CDBurn\OCO\amd64\Support"
  ```

    > [!TIP]
    > <span data-ttu-id="8146c-186">Carga correcta del módulo vuelve a la línea de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8146c-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="8146c-187">Para confirmar que el módulo se carga y que Edit-CsClsScenario está disponible, escriba `Get-Help Edit-CsClsScenario`.</span><span class="sxs-lookup"><span data-stu-id="8146c-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="8146c-188">Tendría que ver una muestra general de la sintaxis de EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="8146c-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="8146c-189">Para quitar un proveedor del escenario AlwaysOn, escriba:</span><span class="sxs-lookup"><span data-stu-id="8146c-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
  ```
  Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
  ```

  <span data-ttu-id="8146c-190">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8146c-190">For Example:</span></span>
    
  ```
  Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
  ```

   <span data-ttu-id="8146c-p117">ScenarioName y ProviderName son parámetros de posición (es decir, es necesario que se definan en una posición determinada en la línea de comandos). El nombre de los parámetros no tiene que definirse explícitamente si el nombre del escenario ocupa el segundo lugar y el proveedor ocupa el tercero tomando como referencia el nombre del cmdlet, que aparece en primer lugar. Teniendo en cuenta esta información, el comando anterior quedaría así:</span><span class="sxs-lookup"><span data-stu-id="8146c-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
  ```
  Edit-CsClsScenario AlwaysOn ChatServer -Remove
  ```

  <span data-ttu-id="8146c-194">La colocación de posición de los valores de parámetro sólo aplica a - escenario y - proveedor.</span><span class="sxs-lookup"><span data-stu-id="8146c-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="8146c-195">Es necesario definir explícitamente todos los demás parámetros.</span><span class="sxs-lookup"><span data-stu-id="8146c-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="8146c-196">Para agregar un proveedor a un escenario con el módulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="8146c-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="8146c-197">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="8146c-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8146c-198">Para agregar un proveedor al escenario AlwaysOn, escriba:</span><span class="sxs-lookup"><span data-stu-id="8146c-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
  ```
  Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
  ```

    <span data-ttu-id="8146c-199">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8146c-199">For Example:</span></span>
    
  ```
  Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
  ```

    <span data-ttu-id="8146c-200">Loglevel - puede ser del tipo de error grave, Error, advertencia, información, detallado, depurar o todos.</span><span class="sxs-lookup"><span data-stu-id="8146c-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="8146c-201">-Flags pueden ser cualquiera de los indicadores que admite el proveedor, como TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="8146c-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="8146c-202">-Flags también pueden ser de valor todos</span><span class="sxs-lookup"><span data-stu-id="8146c-202">-Flags can also be of value ALL</span></span>
    
  <span data-ttu-id="8146c-p120">El ejemplo anterior también se puede introducir usando la característica de colocación posicional del cmdlet. Por ejemplo, para agregar el proveedor ChatServer al escenario AlwaysOn, escriba:</span><span class="sxs-lookup"><span data-stu-id="8146c-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
  ```
  Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
  ```