---
title: Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Resumen: Obtenga información sobre cómo configurar los proveedores de escenario para el servicio de registro centralizado en Skype para Business Server 2015.'
ms.openlocfilehash: e67a1dee9227624ecc94c50437f60781435b2fe8
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372495"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="20ae0-103">Configurar proveedores para el servicio de registro centralizado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="20ae0-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="20ae0-104">**Resumen:** Obtenga información sobre cómo configurar los proveedores de escenario para el servicio de registro centralizado en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="20ae0-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="20ae0-105">Los conceptos y la configuración de proveedores de servicio de registro centralizado es uno de los más importantes de entender.</span><span class="sxs-lookup"><span data-stu-id="20ae0-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="20ae0-106">Theproviders se asignan directamente a Skype para componentes de rol de servidor de Business Server en la Skype para el modelo de seguimiento de Business Server.</span><span class="sxs-lookup"><span data-stu-id="20ae0-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="20ae0-107">El proveedor define los componentes de un Skype para Business Server 2015 que se trazará, el tipo de mensajes (por ejemplo, grave, error o advertencia) para recopilar y los indicadores (por ejemplo, TF_Connection o TF_Diag).</span><span class="sxs-lookup"><span data-stu-id="20ae0-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="20ae0-108">Los proveedores son los componentes puede trazar en cada Skype para el rol de servidor de Business Server.</span><span class="sxs-lookup"><span data-stu-id="20ae0-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="20ae0-109">Si usa proveedores, necesitará establecer el nivel y el tipo de seguimiento de los componentes (S4, SIPStack, MI y presencia, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="20ae0-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="20ae0-110">El proveedor definido se usa en un escenario para agrupar a todos los proveedores de una colección lógica determinada que abordan un problema concreto.</span><span class="sxs-lookup"><span data-stu-id="20ae0-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="20ae0-111">Para ejecutar las funciones de servicio de registro centralizado con la Skype para Shell de administración de servidor empresarial, debe ser un miembro de la CsAdministrator o los grupos de seguridad de CsServerAdministrator acceso basado en roles (RBAC) del control o un rol RBAC personalizado que contiene cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="20ae0-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="20ae0-112">Para devolver una lista de todas las funciones de control (RBAC) de acceso basado en roles este cmdlet se ha asignado a (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el Skype para Shell de administración de servidor empresarial o Windows PowerShell símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="20ae0-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="20ae0-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="20ae0-113">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="20ae0-114">En el resto de este tema se centra en cómo definir proveedores, modificar un proveedor y lo que contiene una definición de proveedor para optimizar su resolución de problemas.</span><span class="sxs-lookup"><span data-stu-id="20ae0-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="20ae0-115">Hay dos formas para emitir los comandos de servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="20ae0-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="20ae0-116">Puede usar el CLSController.exe que se encuentra, de forma predeterminada, en el directorio C:\Program Files\Common Files\Skype para 2015\CLSAgent Business Server.</span><span class="sxs-lookup"><span data-stu-id="20ae0-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="20ae0-117">O bien, puede usar el Skype para Shell de administración de servidor empresarial para emitir los comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20ae0-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="20ae0-118">Mediante el uso de Windows PowerShell, puede definir nuevos proveedores para su uso en las sesiones de registro y tiene control completo sobre su creación, lo que recopilan, y en qué nivel recopilan datos.</span><span class="sxs-lookup"><span data-stu-id="20ae0-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="20ae0-p104">Tal y como se ha mencionado, los proveedores son tremendamente importantes, pero más importantes aún son los escenarios, ya que contienen toda la información necesaria para definir y ejecutar el seguimiento en los componentes que los proveedores representan. Si consideramos un escenario como un conjunto de proveedores, sería comparable (de forma muy vaga) a ejecutar un archivo por lotes que contiene cientos de comandos para recopilar una gran cantidad de información frente a emitir cientos de comandos de una sola vez en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="20ae0-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="20ae0-122">En lugar de que tenga que realizar profundamente profundiza en los detalles de los proveedores, el servicio de registro centralizado proporciona un número de escenarios que ya se han definido por usted.</span><span class="sxs-lookup"><span data-stu-id="20ae0-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="20ae0-123">Los escenarios proporcionados cubren la mayoría de los posibles problemas que se va a encontrar.</span><span class="sxs-lookup"><span data-stu-id="20ae0-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="20ae0-124">En algunos casos poco frecuentes, debe crear y definir los proveedores y asignarlas a escenarios.</span><span class="sxs-lookup"><span data-stu-id="20ae0-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="20ae0-125">Se recomienda encarecidamente que se familiarice con cada uno de los escenarios proporcionados antes de investigar la necesidad de crear escenarios y proveedores de nuevo.</span><span class="sxs-lookup"><span data-stu-id="20ae0-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="20ae0-126">Mientras se encuentre la información sobre la creación de proveedores aquí para familiarizarse con los escenarios de usan que los elementos de proveedor para recopilar información de seguimiento, no se proporcionan detalles sobre los proveedores de sí mismos en este momento.</span><span class="sxs-lookup"><span data-stu-id="20ae0-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="20ae0-127">Introducidos en el [Servicio de registro centralizado en Skype para profesionales de 2015](centralized-logging-service.md), los elementos clave de la definición de un proveedor para su uso en un escenario son:</span><span class="sxs-lookup"><span data-stu-id="20ae0-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="20ae0-128">**Proveedores de** Si está familiarizado con OCSLogger, los proveedores son los componentes que elija para indicar a OCSLogger el motor de seguimiento de qué debe recopilar los registros de.</span><span class="sxs-lookup"><span data-stu-id="20ae0-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="20ae0-129">Los proveedores son los mismos componentes (y, muchas veces, con los mismos nombres) que los de OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="20ae0-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="20ae0-130">Si no está familiarizado con OCSLogger, los proveedores son roles de servidor de componentes específicos que el servicio de registro centralizado puede recopilar los registros de.</span><span class="sxs-lookup"><span data-stu-id="20ae0-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="20ae0-131">En el caso del servicio centralizado de registro, el con CLSAgent es la parte de arquitectura del servicio de registro centralizado que está realizando el seguimiento de los componentes que se definen en la configuración de proveedores.</span><span class="sxs-lookup"><span data-stu-id="20ae0-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="20ae0-132">**Niveles de registro** OCSLogger proporciona la opción para elegir un número de niveles de detalle de los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="20ae0-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="20ae0-133">Esta característica es una parte integral del servicio de registro centralizado y escenarios y se define mediante el parámetro de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="20ae0-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="20ae0-134">Puede elegir entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="20ae0-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="20ae0-135">**Todos los** Recopila seguimiento de mensajes de tipo grave, error, advertencia, detallado e información de depuración en el registro para el proveedor definido.</span><span class="sxs-lookup"><span data-stu-id="20ae0-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="20ae0-136">**Graves** Recopila sólo los mensajes de seguimiento definidos como "Grave".</span><span class="sxs-lookup"><span data-stu-id="20ae0-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="20ae0-137">**Error** Recopila sólo los mensajes de seguimiento se definen como "Error" o "Error grave".</span><span class="sxs-lookup"><span data-stu-id="20ae0-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="20ae0-138">**Advertencia** Recopila sólo los mensajes de seguimiento de tipo "Warning", "Error" y "Grave".</span><span class="sxs-lookup"><span data-stu-id="20ae0-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="20ae0-139">**Info** Recopila sólo los mensajes de seguimiento que indiquen un mensaje informativo para el proveedor definido, además de grave, error y los mensajes de advertencia.</span><span class="sxs-lookup"><span data-stu-id="20ae0-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="20ae0-140">**Detallado** Recopila todos los mensajes de seguimiento de error grave, tipo, advertencia y detallado para el proveedor definido.</span><span class="sxs-lookup"><span data-stu-id="20ae0-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="20ae0-141">**Depurar** es básicamente un equivalente de 'All' - recopila seguimientos de tipo Error grave, Error, advertencia, información, detallado y depurar el proveedor definido.</span><span class="sxs-lookup"><span data-stu-id="20ae0-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="20ae0-142">**Marcas** OCSLogger proporciona la opción para elegir los indicadores para cada proveedor que definen qué tipo de información se puede recuperar desde los archivos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="20ae0-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="20ae0-143">Se pueden elegir las siguientes marcas según el proveedor:</span><span class="sxs-lookup"><span data-stu-id="20ae0-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="20ae0-144">**TF_Connection** Proporciona las entradas del registro relacionadas con la conexión.</span><span class="sxs-lookup"><span data-stu-id="20ae0-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="20ae0-145">Estos registros incluyen información sobre las conexiones establecidas con un componente en particular.</span><span class="sxs-lookup"><span data-stu-id="20ae0-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="20ae0-146">También puede incluir información de la red relevante (esto es, relacionada con los componentes sin el concepto de una conexión).</span><span class="sxs-lookup"><span data-stu-id="20ae0-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="20ae0-147">**TF_Security** Proporciona todas las entradas de registro y eventos relacionados con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="20ae0-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="20ae0-148">Por ejemplo, para SipStack existen eventos de seguridad, como error de validación de dominio y errores de autenticación o autorización de clientes.</span><span class="sxs-lookup"><span data-stu-id="20ae0-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="20ae0-149">**TF_Diag** Proporciona eventos de diagnóstico que puede usar para diagnosticar o solucionar problemas del componente.</span><span class="sxs-lookup"><span data-stu-id="20ae0-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="20ae0-150">Por el ejemplo, para SipStack, estos son errores de certificado, o errores o advertencias de DNS.</span><span class="sxs-lookup"><span data-stu-id="20ae0-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="20ae0-151">**TF_Protocol** Proporciona los mensajes de protocolo, como los mensajes SIP y combinar Pack de códec de la Comunidad.</span><span class="sxs-lookup"><span data-stu-id="20ae0-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="20ae0-152">**TF_Component** Habilita el registro de los componentes especificados como parte de los proveedores.</span><span class="sxs-lookup"><span data-stu-id="20ae0-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="20ae0-153">**Todos los** Establece todos los indicadores disponibles disponibles para el proveedor.</span><span class="sxs-lookup"><span data-stu-id="20ae0-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="20ae0-154">Para revisar la información acerca de los proveedores de escenario de servicio de registro centralizado existentes</span><span class="sxs-lookup"><span data-stu-id="20ae0-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="20ae0-155">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="20ae0-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="20ae0-156">Escriba lo siguiente si desea revisar la configuración de los proveedores existentes:</span><span class="sxs-lookup"><span data-stu-id="20ae0-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="20ae0-157">Por ejemplo, escriba lo siguiente para revisar la información sobre el operador de las conferencias globales:</span><span class="sxs-lookup"><span data-stu-id="20ae0-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="20ae0-158">El comando hace que se muestre una lista de proveedores con sus marcas, configuración y componentes asociados.</span><span class="sxs-lookup"><span data-stu-id="20ae0-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="20ae0-159">Si la información que se muestra no es suficiente o la lista es demasiado larga para el formato de lista de Windows PowerShell de forma predeterminada, puede mostrar información adicional mediante la definición de un método de resultados diferente.</span><span class="sxs-lookup"><span data-stu-id="20ae0-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="20ae0-160">Para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="20ae0-160">To do this, type:</span></span>
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="20ae0-161">La salida de este comando muestra a cada proveedor en un formato de cinco líneas; en cada una de ellas se indica el nombre del proveedor, el tipo de registro, el nivel de registro, las marcas, el GUID y el rol.</span><span class="sxs-lookup"><span data-stu-id="20ae0-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="20ae0-162">Para definir un nuevo proveedor de escenario del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="20ae0-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="20ae0-163">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="20ae0-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="20ae0-p113">Un proveedor de escenario consta de un componente sobre el que realizar el seguimiento, las marcas que se van a usar y el nivel de detalle al que se van a recopilar los datos. Esto se logra escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="20ae0-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="20ae0-166">Por ejemplo, una definición de proveedor de seguimiento en la que se define qué recopilar y con qué nivel de detalle del proveedor Lyss sería así:</span><span class="sxs-lookup"><span data-stu-id="20ae0-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="20ae0-167">-Nivel recopila grave, error, advertencia e información de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="20ae0-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="20ae0-168">Los indicadores utilizados son todos los definidos para el proveedor Lyss e incluyen TF_Connection, TF_Diag y TF_Protocol.After se define la variable $LyssProvider, puede usar con el cmdlet **New-CsClsScenario** para reunir seguimientos desde el proveedor Lyss.</span><span class="sxs-lookup"><span data-stu-id="20ae0-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="20ae0-169">Escriba lo siguiente para crear y asignar el proveedor a un nuevo escenario:</span><span class="sxs-lookup"><span data-stu-id="20ae0-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="20ae0-170">Donde $LyssProvider es la variable que contiene el escenario definido creado con **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="20ae0-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="20ae0-171">Para cambiar un proveedor existente de escenario de servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="20ae0-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="20ae0-172">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="20ae0-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="20ae0-173">Escriba lo siguiente para actualizar o cambiar la configuración de un proveedor existente:</span><span class="sxs-lookup"><span data-stu-id="20ae0-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="20ae0-174">Después, escriba lo siguiente para actualizar el escenario al que se va a asignar el proveedor:</span><span class="sxs-lookup"><span data-stu-id="20ae0-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="20ae0-175">El resultado final del comando es que el escenario site:Redmond/RedmondLyssInfo tendrá las marcas actualizadas y el nivel del proveedor que tenga asignado.</span><span class="sxs-lookup"><span data-stu-id="20ae0-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="20ae0-176">Puede ver el nuevo escenario con Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="20ae0-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="20ae0-177">Para obtener información detallada, vea [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="20ae0-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="20ae0-178">**New-ClsCsProvider** no se comprueba para determinar si los indicadores son válidos.</span><span class="sxs-lookup"><span data-stu-id="20ae0-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="20ae0-179">Asegúrese de que la ortografía de las marcas (por ejemplo, TF_DIAG o TF_CONNECTION) está escrita correctamente.</span><span class="sxs-lookup"><span data-stu-id="20ae0-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="20ae0-180">Si las marcas no están escritas correctamente, el proveedor no puede devolver la información de registro esperado.</span><span class="sxs-lookup"><span data-stu-id="20ae0-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="20ae0-181">Escriba lo siguiente si quiere agregar más proveedores a este escenario:</span><span class="sxs-lookup"><span data-stu-id="20ae0-181">If you want to add additional providers to this scenario, type the following:</span></span>

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="20ae0-182">Donde cada proveedor definido con la directiva Add ya definida mediante el proceso de **New-CsClsProvider** .</span><span class="sxs-lookup"><span data-stu-id="20ae0-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="20ae0-183">Para quitar un proveedor de escenario</span><span class="sxs-lookup"><span data-stu-id="20ae0-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="20ae0-184">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="20ae0-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="20ae0-185">Los cmdlets aquí suministrados permiten crear proveedores y actualizar los ya existentes.</span><span class="sxs-lookup"><span data-stu-id="20ae0-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="20ae0-186">Para quitar un proveedor, debe utilizar la directiva de reemplazo para el parámetro de proveedor a **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="20ae0-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="20ae0-187">La única forma de quitar un proveedor por completo consiste en reemplazarlo por un proveedor predefinido que tenga el mismo nombre y usar la directiva Update.</span><span class="sxs-lookup"><span data-stu-id="20ae0-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="20ae0-188">Por ejemplo, nuestro proveedor LyssProvider tiene definido un tipo de registro WPP, un nivel establecido en Debug y las marcas TF_CONNECTION y TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="20ae0-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="20ae0-189">Debe cambiar las marcas como "Todos".</span><span class="sxs-lookup"><span data-stu-id="20ae0-189">You need to change the flags to "All".</span></span> <span data-ttu-id="20ae0-190">Escriba lo siguiente para cambiar el proveedor:</span><span class="sxs-lookup"><span data-stu-id="20ae0-190">To change the provider, type the following:</span></span>
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="20ae0-191">Escriba lo siguiente si quiere quitar por completo un escenario y sus proveedores asociados:</span><span class="sxs-lookup"><span data-stu-id="20ae0-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="20ae0-192">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="20ae0-192">For example:</span></span>
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="20ae0-193">El cmdlet **Remove-CsClsScenario** no solicitar confirmación.</span><span class="sxs-lookup"><span data-stu-id="20ae0-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="20ae0-194">El escenario se elimina junto con los proveedores que tenga asignados.</span><span class="sxs-lookup"><span data-stu-id="20ae0-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="20ae0-195">Puede crear el escenario de nuevo si vuelve a ejecutar los comandos que usó para crearlo.</span><span class="sxs-lookup"><span data-stu-id="20ae0-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="20ae0-196">No existe ningún procedimiento para recuperar escenarios o proveedores.</span><span class="sxs-lookup"><span data-stu-id="20ae0-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="20ae0-197">Al quitar un escenario mediante el cmdlet **Remove-CsClsScenario** , quitar completamente el escenario del ámbito de aplicación.</span><span class="sxs-lookup"><span data-stu-id="20ae0-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="20ae0-198">Para usar los escenarios que creó y los proveedores que formaban parte de ellos, necesitará crear proveedores y asignarlos a un nuevo escenario.</span><span class="sxs-lookup"><span data-stu-id="20ae0-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="20ae0-199">Vea también</span><span class="sxs-lookup"><span data-stu-id="20ae0-199">See also</span></span>

[<span data-ttu-id="20ae0-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="20ae0-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="20ae0-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="20ae0-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="20ae0-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="20ae0-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="20ae0-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="20ae0-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="20ae0-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="20ae0-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)