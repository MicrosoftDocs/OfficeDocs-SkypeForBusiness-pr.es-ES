---
title: Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015
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
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Resumen: obtenga información sobre cómo crear, modificar y quitar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015.'
ms.openlocfilehash: 8778530826cdbd0c3ecc5128385644f2191a858e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835190"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="27c8e-103">Configurar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="27c8e-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="27c8e-104">**Resumen:** Obtenga información sobre cómo crear, modificar y quitar escenarios para el servicio de registro centralizado en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="27c8e-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="27c8e-105">Los escenarios definen el ámbito (es decir, global, de sitio, de grupo o de equipo) y qué proveedores usar en el servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="27c8e-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="27c8e-106">Al usar escenarios, puede habilitar o deshabilitar el seguimiento de proveedores (por ejemplo, S4, SIPStack, mensajería instantánea y presencia).</span><span class="sxs-lookup"><span data-stu-id="27c8e-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="27c8e-107">Al configurar un escenario, puede agrupar todos los proveedores de una colección lógica determinada que aborda una condición para un problema concreto.</span><span class="sxs-lookup"><span data-stu-id="27c8e-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="27c8e-108">Si ve que es necesario modificar un escenario para satisfacer sus necesidades de solución de problemas y registro, las herramientas de depuración de Skype Empresarial Server 2015 le proporcionan un módulo de Windows PowerShell denominado ClsScenarioEdit.psm1 que contiene una función denominadaEdit-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="27c8e-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="27c8e-109">El propósito del módulo es editar las propiedades del escenario en cuestión.</span><span class="sxs-lookup"><span data-stu-id="27c8e-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="27c8e-110">En este tema se muestran ejemplos del funcionamiento del módulo.</span><span class="sxs-lookup"><span data-stu-id="27c8e-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="27c8e-111">Descargue las herramientas de depuración [](https://go.microsoft.com/fwlink/p/?LinkId=285257) de Skype Empresarial Server 2015 antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="27c8e-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="27c8e-112">Para cualquier ámbito determinado (sitio, global, grupo o equipo), puede ejecutar un máximo de dos escenarios en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="27c8e-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="27c8e-113">Para determinar qué escenarios se están ejecutando actualmente, use Windows PowerShell [y Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="27c8e-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="27c8e-114">Al usar Windows PowerShell [y Set-CsClsScenario,](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)puede cambiar dinámicamente los escenarios que se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="27c8e-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="27c8e-115">Puede modificar qué escenarios se ejecutan durante una sesión de registro para ajustar o refinar los datos que está recopilando y de qué proveedores.</span><span class="sxs-lookup"><span data-stu-id="27c8e-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="27c8e-116">Para ejecutar las funciones del servicio de registro centralizado mediante el Shell de administración de Skype Empresarial Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) CsAdministrator o CsServerAdministrator, o un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="27c8e-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="27c8e-117">Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet, incluidos los roles RBAC personalizados que haya creado usted mismo, ejecute el siguiente comando desde el Shell de administración de Skype Empresarial Server o desde el símbolo del sistema Windows PowerShell voz:</span><span class="sxs-lookup"><span data-stu-id="27c8e-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="27c8e-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27c8e-118">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="27c8e-119">El resto de este tema se centra en cómo definir un escenario, modificar un escenario, recuperar qué escenarios se están ejecutando, quitar un escenario y especificar qué contiene un escenario para optimizar la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="27c8e-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="27c8e-120">Puede usar el Shell de administración de Skype Empresarial Server para emitir Windows PowerShell comandos.</span><span class="sxs-lookup"><span data-stu-id="27c8e-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="27c8e-121">Al usar Windows PowerShell, puede definir nuevos escenarios para usarlos en las sesiones de registro.</span><span class="sxs-lookup"><span data-stu-id="27c8e-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="27c8e-122">Como se introdujo en el servicio de [registro centralizado en Skype Empresarial 2015,](centralized-logging-service.md)los elementos de un escenario son:</span><span class="sxs-lookup"><span data-stu-id="27c8e-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="27c8e-123">**Proveedores** Si está familiarizado con OCSLogger, los proveedores son los componentes que elige para decir a OCSLogger de qué debe recopilar registros el motor de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="27c8e-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="27c8e-124">Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="27c8e-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="27c8e-125">Si no está familiarizado con OCSLogger, los proveedores son componentes específicos de roles de servidor de los que el servicio de registro centralizado puede recopilar registros.</span><span class="sxs-lookup"><span data-stu-id="27c8e-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="27c8e-126">Para obtener más información sobre la configuración de los proveedores, consulte Configurar proveedores para el servicio de registro centralizado en [Skype Empresarial Server 2015.](configure-providers.md)</span><span class="sxs-lookup"><span data-stu-id="27c8e-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="27c8e-127">**Identidad** El parámetro -Identity establece el ámbito y el nombre del escenario.</span><span class="sxs-lookup"><span data-stu-id="27c8e-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="27c8e-128">Por ejemplo, puede establecer un ámbito de "global" e identificar el escenario con "LyssServiceScenario".</span><span class="sxs-lookup"><span data-stu-id="27c8e-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="27c8e-129">Al combinar los dos, se define la identidad (por ejemplo, "global/LyssServiceScenario").</span><span class="sxs-lookup"><span data-stu-id="27c8e-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="27c8e-130">Opcionalmente, puede usar los parámetros -Name y -Parent.</span><span class="sxs-lookup"><span data-stu-id="27c8e-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="27c8e-131">El parámetro Name se define para identificar de forma única el escenario.</span><span class="sxs-lookup"><span data-stu-id="27c8e-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="27c8e-132">Si usa Name, también debe usar Parent para agregar el escenario a global o site.</span><span class="sxs-lookup"><span data-stu-id="27c8e-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="27c8e-133">Si usa los parámetros Name y Parent, no puede usar el **parámetro -Identity.**</span><span class="sxs-lookup"><span data-stu-id="27c8e-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="27c8e-134">Para crear un escenario con el cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="27c8e-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="27c8e-135">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="27c8e-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="27c8e-136">Para crear un escenario para una sesión de registro, utilice [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) y defina el nombre del escenario (es decir, un nombre de identificación único).</span><span class="sxs-lookup"><span data-stu-id="27c8e-136">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="27c8e-137">Elija un tipo de formato de registro de WPP (es decir, el preprocesador de seguimiento del software de Windows; es el predeterminado), EventLog (el formato de registro de eventos de Windows) o IISLog (el archivo de formato basado en el formato de archivo de registro de IIS).</span><span class="sxs-lookup"><span data-stu-id="27c8e-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="27c8e-138">A continuación, defina Level y Flags tal como se definen en este tema los niveles de registro y las etiquetas, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="27c8e-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="27c8e-139">Para este escenario de muestra, utilizaremos LyssProvider como variable del proveedor.</span><span class="sxs-lookup"><span data-stu-id="27c8e-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="27c8e-140">Para crear un escenario con las opciones especificadas, escriba:</span><span class="sxs-lookup"><span data-stu-id="27c8e-140">To create a scenario using the options defined, type:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="27c8e-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27c8e-141">For example:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="27c8e-142">Formato alternativo con -Name y -Parent:</span><span class="sxs-lookup"><span data-stu-id="27c8e-142">The alternate format using -Name and -Parent:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="27c8e-143">Para crear un escenario con varios proveedores con el cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="27c8e-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="27c8e-144">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="27c8e-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="27c8e-145">Por cada ámbito puede haber un máximo de dos escenarios.</span><span class="sxs-lookup"><span data-stu-id="27c8e-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="27c8e-146">Sin embargo, el número de proveedores no está limitado.</span><span class="sxs-lookup"><span data-stu-id="27c8e-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="27c8e-147">Para este ejemplo, supongamos que ha creado tres proveedores y que desea asignarlos al escenario que está definiendo.</span><span class="sxs-lookup"><span data-stu-id="27c8e-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="27c8e-148">Los nombres de la variable "provider" son LyssProvider, ABServerProvider y SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="27c8e-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="27c8e-149">Para definir y asignar varios proveedores a un escenario, escriba lo siguiente en un Shell de administración de Skype Empresarial Server o Windows PowerShell símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="27c8e-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="27c8e-150">Como se conoce en Windows PowerShell, la convención para crear una tabla hash de valores mediante el uso se  `@{<variable>=<value1>, <value2>, <value>…}` conoce como "plataforma".</span><span class="sxs-lookup"><span data-stu-id="27c8e-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="27c8e-151">Para obtener más información acerca de la Windows PowerShell, vea [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760) .</span><span class="sxs-lookup"><span data-stu-id="27c8e-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="27c8e-152">Para modificar un escenario existente con el cmdlet Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="27c8e-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="27c8e-153">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="27c8e-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="27c8e-154">Por cada ámbito puede haber un máximo de dos escenarios.</span><span class="sxs-lookup"><span data-stu-id="27c8e-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="27c8e-155">Puede cambiar los escenarios que estén en ejecución en cualquier momento, incluso si hay una sesión de captura de registros en proceso.</span><span class="sxs-lookup"><span data-stu-id="27c8e-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="27c8e-156">Si redefine los escenarios que se están ejecutándose, la sesión de registro actual dejará de usar el escenario que se haya quitado y comenzará a usar el escenario nuevo.</span><span class="sxs-lookup"><span data-stu-id="27c8e-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="27c8e-157">No obstante, la información de registro que se capturó con el escenario que se haya quitado se mantendrá en los registros capturados.</span><span class="sxs-lookup"><span data-stu-id="27c8e-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="27c8e-158">Para definir un nuevo escenario, haga lo siguiente (es decir, suponiendo que se haya agregado un proveedor ya definido denominado "S4Provider"):</span><span class="sxs-lookup"><span data-stu-id="27c8e-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="27c8e-159">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27c8e-159">For example:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="27c8e-p112">Si desea reemplazar los proveedores, defina un único proveedor o bien una lista de proveedores separados entre sí por comas para cambiar el conjunto actual. Si solo desea reemplazar uno de los proveedores, agregue los proveedores actuales a los nuevos para crear un conjunto de proveedores distinto que contenga tanto los proveedores existentes como los nuevos. Para reemplazar todos los proveedores con un conjunto nuevo, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27c8e-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="27c8e-163">Por ejemplo, para reemplazar el conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, el código sería:</span><span class="sxs-lookup"><span data-stu-id="27c8e-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="27c8e-164">Para reemplazar solo el proveedor $LyssProvider del conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27c8e-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="27c8e-165">Para quitar un escenario existente con el cmdlet Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="27c8e-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="27c8e-166">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="27c8e-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="27c8e-167">Si desea quitar un escenario que se definió previamente, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27c8e-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="27c8e-168">Por ejemplo, para reemplazar el escenario definido con site:Redmond/LyssServiceScenario, el código sería:</span><span class="sxs-lookup"><span data-stu-id="27c8e-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="27c8e-169">El cmdlet **Remove-CsClsScenario** quita el escenario especificado, pero los datos de seguimiento que se hayan capturado seguirán disponibles en los registros para su consulta.</span><span class="sxs-lookup"><span data-stu-id="27c8e-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="27c8e-170">Para cargar y descargar el cmdlet Edit-CsClsScenario con el módulo ClsScenarioEdit.psm1</span><span class="sxs-lookup"><span data-stu-id="27c8e-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="27c8e-171">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="27c8e-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="27c8e-172">El módulo ClsScenarioEdit.psm1 se proporciona como una descarga web independiente.</span><span class="sxs-lookup"><span data-stu-id="27c8e-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="27c8e-173">El módulo forma parte de las herramientas de depuración de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="27c8e-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="27c8e-174">De forma predeterminada, las herramientas de depuración se instalan en el directorio C:\Archivos de programa\Skype Empresarial Server 2015\Herramientas de depuración.</span><span class="sxs-lookup"><span data-stu-id="27c8e-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="27c8e-175">En la Windows PowerShell, escriba:</span><span class="sxs-lookup"><span data-stu-id="27c8e-175">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="27c8e-176">Si el módulo se carga correctamente, se le Windows PowerShell símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="27c8e-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="27c8e-177">Para confirmar que el módulo está cargado y que Edit-CsClsScenario está disponible, escriba  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="27c8e-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="27c8e-178">Debería ver una muestra general de la sintaxis de EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="27c8e-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="27c8e-179">Para descargar los módulos, escriba:</span><span class="sxs-lookup"><span data-stu-id="27c8e-179">To unload the modules, type:</span></span>
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="27c8e-180">Si el módulo se descarga correctamente, volverá al símbolo Windows PowerShell de comandos.</span><span class="sxs-lookup"><span data-stu-id="27c8e-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="27c8e-181">Para confirmar que el módulo está descargado, escriba  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="27c8e-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="27c8e-182">Windows PowerShell buscar la ayuda del cmdlet y se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="27c8e-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="27c8e-183">Para quitar un proveedor existente de un escenario con el módulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="27c8e-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="27c8e-184">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="27c8e-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="27c8e-185">En la Windows PowerShell, escriba:</span><span class="sxs-lookup"><span data-stu-id="27c8e-185">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="27c8e-186">Si el módulo se carga correctamente, se le Windows PowerShell símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="27c8e-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="27c8e-187">Para confirmar que el módulo está cargado y que Edit-CsClsScenario está disponible, escriba  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="27c8e-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="27c8e-188">Debería ver una muestra general de la sintaxis de EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="27c8e-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="27c8e-189">Para quitar un proveedor del escenario AlwaysOn, escriba:</span><span class="sxs-lookup"><span data-stu-id="27c8e-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="27c8e-190">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27c8e-190">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="27c8e-p117">ScenarioName y ProviderName son parámetros de posición (es decir, es necesario que se definan en una posición determinada en la línea de comandos). El nombre de los parámetros no tiene que definirse explícitamente si el nombre del escenario ocupa el segundo lugar y el proveedor ocupa el tercero tomando como referencia el nombre del cmdlet, que aparece en primer lugar. Teniendo en cuenta esta información, el comando anterior quedaría así:</span><span class="sxs-lookup"><span data-stu-id="27c8e-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="27c8e-194">La colocación posicional de los valores de parámetro solo se aplica a -Scenario y -Provider.</span><span class="sxs-lookup"><span data-stu-id="27c8e-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="27c8e-195">Todos los demás parámetros se deben definir explícitamente.</span><span class="sxs-lookup"><span data-stu-id="27c8e-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="27c8e-196">Para agregar un proveedor a un escenario con el módulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="27c8e-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="27c8e-197">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="27c8e-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="27c8e-198">Para agregar un proveedor al escenario AlwaysOn, escriba:</span><span class="sxs-lookup"><span data-stu-id="27c8e-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="27c8e-199">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27c8e-199">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="27c8e-200">-Loglevel puede ser del tipo Fatal, Error, Warning, Info, Verbose, Debug o All.</span><span class="sxs-lookup"><span data-stu-id="27c8e-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="27c8e-201">-Flags puede ser cualquiera de las marcas que admite el proveedor, como TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="27c8e-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="27c8e-202">-Flags también puede ser de valor ALL</span><span class="sxs-lookup"><span data-stu-id="27c8e-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="27c8e-p120">El ejemplo anterior también se puede introducir usando la característica de colocación posicional del cmdlet. Por ejemplo, para agregar el proveedor ChatServer al escenario AlwaysOn, el código quedaría así:</span><span class="sxs-lookup"><span data-stu-id="27c8e-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
