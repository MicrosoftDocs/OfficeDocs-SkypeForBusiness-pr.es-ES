---
title: Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Resumen: Aprenda a configurar proveedores de escenarios para el servicio de registro centralizado en Skype empresarial Server 2015.'
ms.openlocfilehash: e2c633dabf30ffbc42fa90066bf469e10dc25fb6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816609"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="ebe10-103">Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="ebe10-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ebe10-104">**Resumen:** Aprenda a configurar proveedores de escenarios para el servicio de registro centralizado en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ebe10-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ebe10-105">Los conceptos y la configuración de proveedores en el servicio de registro centralizado es uno de los más importantes para comprender.</span><span class="sxs-lookup"><span data-stu-id="ebe10-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="ebe10-106">Los proporcionantes se asignan directamente a los componentes de rol de servidor de Skype empresarial Server en el modelo de seguimiento de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ebe10-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="ebe10-107">El proveedor define los componentes de un servidor de Skype empresarial 2015 en el que se realizará el seguimiento, el tipo de mensajes (por ejemplo, fatal, error o Warning) que se van a recopilar, así como las marcas (por ejemplo, TF_Connection o TF_Diag).</span><span class="sxs-lookup"><span data-stu-id="ebe10-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="ebe10-108">Los proveedores son los componentes que se pueden rastrear en cada rol de servidor de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ebe10-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="ebe10-109">Si usa proveedores, necesitará establecer el nivel y el tipo de seguimiento de los componentes (S4, SIPStack, MI y presencia, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="ebe10-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="ebe10-110">El proveedor definido se usa en un escenario para agrupar a todos los proveedores de una colección lógica determinada que abordan un problema concreto.</span><span class="sxs-lookup"><span data-stu-id="ebe10-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="ebe10-111">Para ejecutar las funciones del servicio de registro centralizado con el shell de administración de Skype empresarial Server, debe ser miembro de los grupos de seguridad de control de acceso basado en roles (RBAC) de CsAdministrator o CsServerAdministrator, o un rol de RBAC personalizado que contiene alguno de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="ebe10-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="ebe10-112">Para devolver una lista de todas las funciones de control de acceso basado en roles (RBAC) a las que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el shell de administración de Skype empresarial Server o Windows PowerShell deba</span><span class="sxs-lookup"><span data-stu-id="ebe10-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="ebe10-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ebe10-113">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="ebe10-114">El resto de este tema se centra en cómo definir proveedores, modificar un proveedor y qué contiene una definición de proveedor para optimizar la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="ebe10-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="ebe10-115">Hay dos formas de emitir comandos de servicio de registro centralizados.</span><span class="sxs-lookup"><span data-stu-id="ebe10-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="ebe10-116">Puede usar el CLSController. exe, que está ubicado, de forma predeterminada, en el directorio C:\Archivos de Programa\archivos Files\Skype para empresas Server 2015 \ CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="ebe10-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="ebe10-117">O bien, puede usar el shell de administración de Skype empresarial Server para emitir comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebe10-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="ebe10-118">Al usar Windows PowerShell, puede definir nuevos proveedores para usarlos en sus sesiones de registro y tener control completo sobre su creación, qué recopilan y en qué nivel recopilan datos.</span><span class="sxs-lookup"><span data-stu-id="ebe10-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ebe10-p104">Tal y como se ha mencionado, los proveedores son tremendamente importantes, pero más importantes aún son los escenarios, ya que contienen toda la información necesaria para definir y ejecutar el seguimiento en los componentes que los proveedores representan. Si consideramos un escenario como un conjunto de proveedores, sería comparable (de forma muy vaga) a ejecutar un archivo por lotes que contiene cientos de comandos para recopilar una gran cantidad de información frente a emitir cientos de comandos de una sola vez en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ebe10-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="ebe10-122">En lugar de tener que profundizar profundamente en los detalles de los proveedores, el servicio de registro centralizado proporciona una serie de escenarios que ya están definidos para usted.</span><span class="sxs-lookup"><span data-stu-id="ebe10-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="ebe10-123">Los escenarios proporcionados cubren la gran mayoría de posibles problemas que surjan.</span><span class="sxs-lookup"><span data-stu-id="ebe10-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="ebe10-124">En raras ocasiones, es posible que tenga que crear y definir proveedores y asignarlos a escenarios.</span><span class="sxs-lookup"><span data-stu-id="ebe10-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="ebe10-125">Le recomendamos encarecidamente que se familiarice con cada uno de los escenarios proporcionados antes de investigar la necesidad de crear nuevos proveedores y escenarios.</span><span class="sxs-lookup"><span data-stu-id="ebe10-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="ebe10-126">Aunque encontrará información sobre la creación de proveedores aquí para familiarizarse con el modo en que los escenarios usan los elementos del proveedor para recopilar información de seguimiento, en este momento no se proporcionan detalles de los propios proveedores.</span><span class="sxs-lookup"><span data-stu-id="ebe10-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="ebe10-127">Introducido en el [servicio de registro centralizado en Skype empresarial 2015](centralized-logging-service.md), los elementos clave de la definición de un proveedor para su uso en un escenario son:</span><span class="sxs-lookup"><span data-stu-id="ebe10-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="ebe10-128">**Proveedores** Si está familiarizado con OCSLogger, los proveedores son los componentes que usted elige para indicar OCSLogger de qué debe recopilar los registros el motor de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ebe10-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="ebe10-129">Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="ebe10-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="ebe10-130">Si no está familiarizado con OCSLogger, los proveedores son componentes específicos del rol de servidor del que el servicio de registro centralizado puede recopilar registros.</span><span class="sxs-lookup"><span data-stu-id="ebe10-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="ebe10-131">En el caso del servicio de registro centralizado, CLSAgent es la parte arquitectónica del servicio de registro centralizado que realiza el seguimiento de los componentes que define en la configuración de los proveedores.</span><span class="sxs-lookup"><span data-stu-id="ebe10-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="ebe10-132">**Niveles de registro** OCSLogger proporcionó la opción de elegir un número de niveles de detalle para los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="ebe10-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="ebe10-133">Esta característica es una parte integral del servicio de registro centralizado y los escenarios, y se define mediante el parámetro **Type** .</span><span class="sxs-lookup"><span data-stu-id="ebe10-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="ebe10-134">Puede elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ebe10-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="ebe10-135">**Todas las** Recopila mensajes de seguimiento de tipo grave, error, warning, verbose e información de depuración en el registro para el proveedor definido.</span><span class="sxs-lookup"><span data-stu-id="ebe10-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="ebe10-136">**Error grave** Recopila solo los mensajes de seguimiento definidos como "fatales".</span><span class="sxs-lookup"><span data-stu-id="ebe10-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="ebe10-137">**Error** Recopila solo los mensajes de seguimiento definidos como "error" o "fatal".</span><span class="sxs-lookup"><span data-stu-id="ebe10-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="ebe10-138">**ADVERTENCIA** Recopila solo los mensajes de seguimiento de tipo "WARNING", "error" y "fatal".</span><span class="sxs-lookup"><span data-stu-id="ebe10-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="ebe10-139">**Información** Recopila solo los mensajes de seguimiento que indican un mensaje informativo para el proveedor definido, además de mensajes de error, de errores y advertencias.</span><span class="sxs-lookup"><span data-stu-id="ebe10-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="ebe10-140">**Detallado** Recopila todos los mensajes de seguimiento de tipo grave, error, warning y verbose para el proveedor definido.</span><span class="sxs-lookup"><span data-stu-id="ebe10-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="ebe10-141">**Depurar** es esencialmente un equivalente de ' All ': recopila rastros de tipo grave, error, warning, info, verbose y Debug para el proveedor definido.</span><span class="sxs-lookup"><span data-stu-id="ebe10-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="ebe10-142">**Marcas** OCSLogger proporcionó la opción de elegir marcas para cada proveedor que definió el tipo de información que podría recuperar de los archivos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ebe10-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="ebe10-143">Puede elegir los siguientes marcadores, en función del proveedor:</span><span class="sxs-lookup"><span data-stu-id="ebe10-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="ebe10-144">**TF_Connection** Proporciona entradas de registro relacionadas con la conexión.</span><span class="sxs-lookup"><span data-stu-id="ebe10-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="ebe10-145">Estos registros incluyen información acerca de las conexiones establecidas a un componente determinado y desde él.</span><span class="sxs-lookup"><span data-stu-id="ebe10-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="ebe10-146">También puede incluir información importante sobre el nivel de red (es decir, para los componentes sin el concepto de conexión).</span><span class="sxs-lookup"><span data-stu-id="ebe10-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="ebe10-147">**TF_Security** Proporciona todos los eventos/entradas de registro relacionadas con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="ebe10-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="ebe10-148">Por ejemplo, para SipStack, estos son eventos de seguridad, como errores de validación de dominio, y errores de autenticación/autorización de clientes.</span><span class="sxs-lookup"><span data-stu-id="ebe10-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="ebe10-149">**TF_Diag** Proporciona eventos de diagnóstico que puede usar para diagnosticar o solucionar problemas del componente.</span><span class="sxs-lookup"><span data-stu-id="ebe10-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="ebe10-150">Por ejemplo, para SipStack, se trata de errores de certificado o advertencias o errores de DNS.</span><span class="sxs-lookup"><span data-stu-id="ebe10-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="ebe10-151">**TF_Protocol** Proporciona mensajes de protocolo, como los mensajes de los paquetes de códec de la comunidad combinada y SIP.</span><span class="sxs-lookup"><span data-stu-id="ebe10-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="ebe10-152">**TF_Component** Habilita el registro de los componentes especificados como parte de los proveedores.</span><span class="sxs-lookup"><span data-stu-id="ebe10-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="ebe10-153">**Todas las** Establece todas las marcas disponibles para el proveedor.</span><span class="sxs-lookup"><span data-stu-id="ebe10-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="ebe10-154">Para revisar la información sobre los proveedores de escenarios del servicio de registro centralizado existentes</span><span class="sxs-lookup"><span data-stu-id="ebe10-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="ebe10-155">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="ebe10-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ebe10-156">Para revisar la configuración de proveedores existentes, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebe10-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="ebe10-157">Por ejemplo, para revisar la información sobre el operador de conferencia global, escriba:</span><span class="sxs-lookup"><span data-stu-id="ebe10-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="ebe10-158">El comando muestra una lista de proveedores con los indicadores, la configuración y los componentes asociados.</span><span class="sxs-lookup"><span data-stu-id="ebe10-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="ebe10-159">Si la información que se muestra no es suficiente o la lista es demasiado larga para el formato de lista predeterminado de Windows PowerShell, puede mostrar información adicional definiendo un método de salida diferente.</span><span class="sxs-lookup"><span data-stu-id="ebe10-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="ebe10-160">Para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebe10-160">To do this, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="ebe10-161">La salida de este comando muestra cada proveedor mostrado en un formato de cinco líneas con el nombre del proveedor, el tipo de registro, el nivel de registro, las marcas, el GUID y el rol, cada uno en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="ebe10-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="ebe10-162">Para definir un nuevo proveedor de escenarios de servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="ebe10-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="ebe10-163">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="ebe10-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ebe10-164">Un proveedor de escenarios consta de un componente para el seguimiento, las marcas que se van a usar y un nivel de detalle que se va a recopilar.</span><span class="sxs-lookup"><span data-stu-id="ebe10-164">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect.</span></span> <span data-ttu-id="ebe10-165">Para ello, escriba:</span><span class="sxs-lookup"><span data-stu-id="ebe10-165">You do this by typing:</span></span>
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="ebe10-166">Por ejemplo, una definición de proveedor de seguimiento que define lo que se debe recopilar y el nivel de detalle del proveedor de Lyss es similar a:</span><span class="sxs-lookup"><span data-stu-id="ebe10-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="ebe10-167">El nivel obtiene mensajes de error, advertencia e información.</span><span class="sxs-lookup"><span data-stu-id="ebe10-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="ebe10-168">Los indicadores que se usan son todos los definidos para el proveedor de Lyss e incluyen TF_Connection, TF_Diag y TF_Protocol. después de definir la variable $LyssProvider, puede usarla con el cmdlet **New-CsClsScenario** para recopilar seguimientos del proveedor de Lyss.</span><span class="sxs-lookup"><span data-stu-id="ebe10-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="ebe10-169">Para completar la creación y asignación del proveedor a un nuevo escenario, escriba:</span><span class="sxs-lookup"><span data-stu-id="ebe10-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="ebe10-170">Donde $LyssProvider es la variable que contiene el escenario definido creado con **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="ebe10-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="ebe10-171">Para cambiar un proveedor de escenarios de servicio de registro centralizado existente</span><span class="sxs-lookup"><span data-stu-id="ebe10-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="ebe10-172">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="ebe10-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ebe10-173">Para actualizar o cambiar la configuración de un proveedor existente, escriba:</span><span class="sxs-lookup"><span data-stu-id="ebe10-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="ebe10-174">A continuación, debe actualizar el escenario para asignar el proveedor escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebe10-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="ebe10-175">El resultado final del comando es que el sitio del escenario: Redmond/RedmondLyssInfo tendrá marcas y niveles actualizados para el proveedor que se le haya asignado.</span><span class="sxs-lookup"><span data-stu-id="ebe10-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="ebe10-176">Puede ver el nuevo escenario con get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="ebe10-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="ebe10-177">Para obtener más información, vea [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ebe10-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="ebe10-178">**New-ClsCsProvider** no comprueba si los marcadores son válidos.</span><span class="sxs-lookup"><span data-stu-id="ebe10-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="ebe10-179">Asegúrese de que la ortografía de las marcas (por ejemplo, TF_DIAG o TF_CONNECTION) esté escrita correctamente.</span><span class="sxs-lookup"><span data-stu-id="ebe10-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="ebe10-180">Si los marcadores no se escriben correctamente, el proveedor no puede devolver la información de registro esperada.</span><span class="sxs-lookup"><span data-stu-id="ebe10-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="ebe10-181">Si desea agregar proveedores adicionales a este escenario, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebe10-181">If you want to add additional providers to this scenario, type the following:</span></span>

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="ebe10-182">Donde cada proveedor definido con la Directiva Add ya se ha definido mediante el proceso **New-CsClsProvider** .</span><span class="sxs-lookup"><span data-stu-id="ebe10-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="ebe10-183">Para quitar un proveedor de escenarios</span><span class="sxs-lookup"><span data-stu-id="ebe10-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="ebe10-184">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="ebe10-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ebe10-185">Los cmdlets proporcionados le permiten actualizar proveedores existentes y crear nuevos proveedores.</span><span class="sxs-lookup"><span data-stu-id="ebe10-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="ebe10-186">Para quitar un proveedor, debe usar la Directiva Replace para que el parámetro Provider **establezca-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="ebe10-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="ebe10-187">La única forma de quitar un proveedor por completo es reemplazarlo por un proveedor redefinido con el mismo nombre y utilizar la Directiva de actualización.</span><span class="sxs-lookup"><span data-stu-id="ebe10-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="ebe10-188">Por ejemplo, nuestro proveedor LyssProvider se define con WPP como el tipo de registro, Level establecido en debug, y los indicadores establecidos son TF_CONNECTION y TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="ebe10-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="ebe10-189">Debe cambiar las marcas a "todo".</span><span class="sxs-lookup"><span data-stu-id="ebe10-189">You need to change the flags to "All".</span></span> <span data-ttu-id="ebe10-190">Para cambiar el proveedor, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebe10-190">To change the provider, type the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="ebe10-191">Si desea quitar por completo un escenario y los proveedores asociados a él, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebe10-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="ebe10-192">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ebe10-192">For example:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="ebe10-193">El cmdlet **Remove-CsClsScenario** no le solicita confirmación.</span><span class="sxs-lookup"><span data-stu-id="ebe10-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="ebe10-194">El escenario se elimina, junto con los proveedores que se le asignaron.</span><span class="sxs-lookup"><span data-stu-id="ebe10-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="ebe10-195">Puede volver a crear el escenario volviendo a ejecutar los comandos usados para crearlo inicialmente.</span><span class="sxs-lookup"><span data-stu-id="ebe10-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="ebe10-196">No hay ningún procedimiento para recuperar los escenarios o proveedores eliminados.</span><span class="sxs-lookup"><span data-stu-id="ebe10-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="ebe10-197">Al quitar un escenario mediante el cmdlet **Remove-CsClsScenario** , se elimina completamente el escenario del ámbito.</span><span class="sxs-lookup"><span data-stu-id="ebe10-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="ebe10-198">Para usar los escenarios que ha creado y los proveedores que forman parte del escenario, cree nuevos proveedores y asígnelos a un nuevo escenario.</span><span class="sxs-lookup"><span data-stu-id="ebe10-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="ebe10-199">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebe10-199">See also</span></span>

[<span data-ttu-id="ebe10-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="ebe10-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="ebe10-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="ebe10-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="ebe10-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="ebe10-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="ebe10-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="ebe10-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="ebe10-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="ebe10-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
