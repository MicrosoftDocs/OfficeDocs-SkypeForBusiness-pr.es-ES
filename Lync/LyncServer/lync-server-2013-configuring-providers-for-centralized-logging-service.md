---
title: 'Lync Server 2013: configuración de proveedores para el servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ba3d903b1d4a33048f5a66738897408c36a94e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="4538f-102">Configuración de proveedores para el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4538f-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4538f-103">_**Última modificación del tema:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="4538f-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="4538f-104">Los conceptos y la configuración de los *proveedores* en el servicio de registro centralizado son uno de los más importantes que se deben comprender.</span><span class="sxs-lookup"><span data-stu-id="4538f-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="4538f-105">Los *proveedores* se asignan directamente a los componentes del rol de servidor de Lync Server en el modelo de seguimiento de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4538f-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="4538f-106">El proveedor define los componentes de un 2013 de Lync Server en los que se realizará un seguimiento, el tipo de mensajes (por ejemplo, fatal, error o Warning) que se van a recopilar y las\_marcas (por\_ejemplo, TF Connection o TF Diag).</span><span class="sxs-lookup"><span data-stu-id="4538f-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="4538f-107">Los proveedores son los componentes que se pueden rastrear en cada rol de servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4538f-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="4538f-108">Si usa proveedores, deberá establecer el nivel y el tipo de seguimiento de los componentes (S4, SIPStack, MI y presencia, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="4538f-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="4538f-109">El proveedor definido se usa en un escenario para agrupar a todos los proveedores de una colección lógica determinada que abordan un problema concreto.</span><span class="sxs-lookup"><span data-stu-id="4538f-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="4538f-110">Para ejecutar las funciones del servicio de registro centralizado con el shell de administración de Lync Server, debe ser miembro de los grupos de seguridad CsAdministrator o CsServerAdministrator role-based access control (RBAC), o un rol RBAC personalizado que contenga cualquiera de Estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="4538f-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="4538f-111">Para devolver una lista de todos los roles de control de acceso basado en roles (RBAC) a los que se ha asignado este cmdlet (incluido cualquier otro rol RBAC personalizado que usted mismo haya creado), ejecute el siguiente comando desde el shell de administración de Lync Server o el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4538f-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="4538f-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4538f-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="4538f-113">El resto de este tema se centra en cómo definir proveedores, modificar un proveedor y qué contiene una definición de proveedor para optimizar la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="4538f-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="4538f-114">Hay dos formas de emitir comandos de servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="4538f-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="4538f-115">Puede usar el CLSController. exe que se encuentra, de manera predeterminada, en el directorio C:\\archivos de\\programa archivos\\comunes Microsoft Lync Server\\2013 CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="4538f-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="4538f-116">O bien, puede usar el shell de administración de Lync Server para emitir comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4538f-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="4538f-117">La diferencia importante es que cuando se utiliza CLSController. exe en la línea de comandos, hay una selección finita de escenarios disponibles en los que los proveedores ya están definidos y no son modificables, pero puede definir el nivel de registro.</span><span class="sxs-lookup"><span data-stu-id="4538f-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="4538f-118">Con Windows PowerShell, puede definir nuevos proveedores para usarlos en sus sesiones de registro y tener un control completo sobre su creación, lo que recopilan y el nivel en el que recopilan datos.</span><span class="sxs-lookup"><span data-stu-id="4538f-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="4538f-p104">Tal y como se ha mencionado, los proveedores son tremendamente importantes, pero más importantes aún son los escenarios, ya que contienen toda la información necesaria para definir y ejecutar el seguimiento en los componentes que los proveedores representan. Si consideramos un escenario como un conjunto de proveedores, sería comparable (de forma muy vaga) a ejecutar un archivo por lotes que contiene cientos de comandos para recopilar una gran cantidad de información frente a emitir cientos de comandos de una sola vez en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4538f-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="4538f-122">En lugar de tener que profundizar profundamente en los detalles de los proveedores, el servicio de registro centralizado proporciona una serie de escenarios que ya están definidos para usted.</span><span class="sxs-lookup"><span data-stu-id="4538f-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="4538f-123">Los escenarios proporcionados cubren la gran mayoría de los posibles problemas que se encuentren.</span><span class="sxs-lookup"><span data-stu-id="4538f-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="4538f-124">En raras ocasiones, es posible que necesite crear y definir proveedores y asignarlos a los escenarios.</span><span class="sxs-lookup"><span data-stu-id="4538f-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="4538f-125">Le recomendamos encarecidamente que se familiarice con cada uno de los escenarios que se proporcionan antes de investigar la necesidad de crear nuevos proveedores y escenarios.</span><span class="sxs-lookup"><span data-stu-id="4538f-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="4538f-126">Mientras que la información sobre la creación de proveedores se encuentra aquí para familiarizarse con la forma en que los escenarios usan los elementos del proveedor para recopilar información de seguimiento, los detalles de los propios proveedores no se proporcionan en este momento.</span><span class="sxs-lookup"><span data-stu-id="4538f-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="4538f-127">Se incorporó en [información general del servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), los elementos clave de la definición de un proveedor para usarlo en un escenario son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4538f-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="4538f-128">**Proveedores**   si está familiarizado con OCSLogger, los proveedores son los componentes que elija para determinar OCSLogger de qué debe recopilar los registros el motor de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4538f-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="4538f-129">Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="4538f-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="4538f-130">Si no está familiarizado con OCSLogger, los proveedores son componentes específicos de roles de servidor de los que el servicio de registro centralizado puede recopilar registros.</span><span class="sxs-lookup"><span data-stu-id="4538f-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="4538f-131">En el caso del servicio de registro centralizado, CLSAgent es la parte de la arquitectura del servicio de registro centralizado que realiza el seguimiento de los componentes que se definen en la configuración de los proveedores.</span><span class="sxs-lookup"><span data-stu-id="4538f-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="4538f-132">**Los niveles**   de registro OCSLogger proporcionan la opción de elegir un número de niveles de detalle para los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="4538f-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="4538f-133">Esta característica forma parte integral del servicio de registro centralizado y los escenarios, y se define mediante el parámetro **Type** .</span><span class="sxs-lookup"><span data-stu-id="4538f-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="4538f-134">Se puede elegir entre las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4538f-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="4538f-135">**All**   recopila mensajes de seguimiento de tipo error irrecuperable, error, advertencia e información en el registro para el proveedor definido.</span><span class="sxs-lookup"><span data-stu-id="4538f-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="4538f-136">**Fatal**   recopila solo los mensajes de seguimiento que indican un error para el proveedor definido.</span><span class="sxs-lookup"><span data-stu-id="4538f-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="4538f-137">**Error**   recopila solo los mensajes de seguimiento que indican un error para el proveedor definido, además de los mensajes irrecuperables.</span><span class="sxs-lookup"><span data-stu-id="4538f-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="4538f-138">**ADVERTENCIA**   recopila solo los mensajes de seguimiento que indican una advertencia para el proveedor definido, además de los mensajes de error y de errores irrecuperables.</span><span class="sxs-lookup"><span data-stu-id="4538f-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="4538f-139">**Información**   recopila solo los mensajes de seguimiento que indican un mensaje informativo para el proveedor definido, además de los mensajes de error, de errores y de advertencia.</span><span class="sxs-lookup"><span data-stu-id="4538f-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="4538f-140">**Verbose**   recopila todos los mensajes de seguimiento de tipo error, advertencia e información del proveedor definido.</span><span class="sxs-lookup"><span data-stu-id="4538f-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="4538f-141">**Flags**   OCSLogger proporcionó la opción de elegir marcas para cada proveedor que definió el tipo de información que podía recuperar de los archivos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4538f-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="4538f-142">Se pueden elegir las siguientes marcas según el proveedor:</span><span class="sxs-lookup"><span data-stu-id="4538f-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="4538f-143">**TF\_Connection**   proporciona entradas de registro relacionadas con la conexión.</span><span class="sxs-lookup"><span data-stu-id="4538f-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="4538f-144">Estos registros incluyen información sobre las conexiones establecidas con un componente en particular.</span><span class="sxs-lookup"><span data-stu-id="4538f-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="4538f-145">También pueden incluir información de nivel de red relevante (esto es, relacionada con componentes sin concepto de conexión).</span><span class="sxs-lookup"><span data-stu-id="4538f-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="4538f-146">**TF\_Security**   proporciona todos los eventos/entradas de registro relacionadas con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="4538f-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="4538f-147">Por ejemplo, para SipStack existen eventos de seguridad como error de validación de dominio y errores de autenticación/autorización de clientes.</span><span class="sxs-lookup"><span data-stu-id="4538f-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="4538f-148">**TF\_Diag**   proporciona eventos de diagnóstico que puede usar para diagnosticar o solucionar problemas del componente.</span><span class="sxs-lookup"><span data-stu-id="4538f-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="4538f-149">Siguiendo con el ejemplo de SipStack, existen errores de certificado y errores/advertencias de DNS.</span><span class="sxs-lookup"><span data-stu-id="4538f-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="4538f-150">**TF\_Protocol**   proporciona mensajes de protocolo, como mensajes de SIP y del paquete de códecs de comunidad combinada.</span><span class="sxs-lookup"><span data-stu-id="4538f-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="4538f-151">**TF\_Component**   habilita el registro de los componentes especificados como parte de los proveedores.</span><span class="sxs-lookup"><span data-stu-id="4538f-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="4538f-152">**All**   establece todas las marcas disponibles para el proveedor.</span><span class="sxs-lookup"><span data-stu-id="4538f-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="4538f-153">Para revisar la información sobre los proveedores de escenario del servicio de registro centralizado existente</span><span class="sxs-lookup"><span data-stu-id="4538f-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="4538f-154">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4538f-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4538f-155">Escriba lo siguiente si desea revisar la configuración de los proveedores existentes:</span><span class="sxs-lookup"><span data-stu-id="4538f-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="4538f-156">Por ejemplo, escriba lo siguiente para revisar la información sobre las conferencias globales:</span><span class="sxs-lookup"><span data-stu-id="4538f-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="4538f-157">El comando hace que se muestre una lista de proveedores con sus marcas, configuraciones y componentes correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4538f-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="4538f-158">Si la información que se muestra no es suficiente o la lista es demasiado larga para el formato de lista predeterminado de Windows PowerShell, puede mostrar información adicional definiendo un método de salida diferente.</span><span class="sxs-lookup"><span data-stu-id="4538f-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="4538f-159">Para ello, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4538f-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="4538f-160">El resultado de este comando muestra a cada proveedor en un formato de cinco líneas, en cada una de las cuales se indica el nombre de proveedor, tipo de registro, nivel de registro, marcas, GUID y rol.</span><span class="sxs-lookup"><span data-stu-id="4538f-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="4538f-161">Para definir un nuevo proveedor de escenarios del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="4538f-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="4538f-162">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4538f-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4538f-p113">Un proveedor de escenario consta de un componente sobre el que realizar el seguimiento, las marcas que se van a usar y el nivel de detalle al que se van a recopilar los datos. Esto se logran escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4538f-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="4538f-165">Por ejemplo, una definición de proveedor de seguimiento en la que se define qué recopilar y con qué nivel de detalle del proveedor Lyss sería así:</span><span class="sxs-lookup"><span data-stu-id="4538f-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="4538f-166">–Level recopila los mensajes de error, error irrecuperable, advertencia y de carácter informativos.</span><span class="sxs-lookup"><span data-stu-id="4538f-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="4538f-167">Las marcas usadas son todas las que se han definido para el proveedor Lyss e incluyen\_TF Connection,\_TF Diag and\_TF Protocol.</span><span class="sxs-lookup"><span data-stu-id="4538f-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="4538f-168">Después de definir la variable $LyssProvider, puede usarla con el cmdlet **New-CsClsScenario** para recopilar seguimiento del proveedor Lyss.</span><span class="sxs-lookup"><span data-stu-id="4538f-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="4538f-169">Escriba lo siguiente para crear y asignar el proveedor a un nuevo escenario:</span><span class="sxs-lookup"><span data-stu-id="4538f-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="4538f-170">Donde $LyssProvider es la variable que contiene el escenario definido creado con **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="4538f-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="4538f-171">Para cambiar un proveedor de escenarios del servicio de registro centralizado existente</span><span class="sxs-lookup"><span data-stu-id="4538f-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="4538f-172">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4538f-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4538f-173">Escriba lo siguiente para actualizar o cambiar la configuración de un proveedor existente:</span><span class="sxs-lookup"><span data-stu-id="4538f-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="4538f-174">Después, escriba lo siguiente para actualizar el escenario al que se va a asignar el proveedor:</span><span class="sxs-lookup"><span data-stu-id="4538f-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="4538f-175">El resultado final del comando es que el sitio de escenario:Redmond/RedmondLyssInfo tendrá las marcas actualizadas y el nivel del proveedor que tenga asignado.</span><span class="sxs-lookup"><span data-stu-id="4538f-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="4538f-176">Puede ver el nuevo escenario con Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="4538f-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="4538f-177">Para obtener información, consulte [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span><span class="sxs-lookup"><span data-stu-id="4538f-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="4538f-178"><STRONG>New-ClsCsProvider</STRONG> no realiza una comprobación para determinar si las marcas son válidas.</span><span class="sxs-lookup"><span data-stu-id="4538f-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="4538f-179">Asegúrese de que la ortografía de las marcas (por ejemplo, TF_DIAG o TF_CONNECTION) está escrita correctamente.</span><span class="sxs-lookup"><span data-stu-id="4538f-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="4538f-180">Si las marcas no se escriben correctamente, el proveedor no puede devolver la información de registro esperada.</span><span class="sxs-lookup"><span data-stu-id="4538f-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="4538f-181">Escriba lo siguiente si quiere agregar más proveedores a este escenario:</span><span class="sxs-lookup"><span data-stu-id="4538f-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="4538f-182">Donde cada proveedor definido con la directiva Add ya se ha definido a través del proceso de **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="4538f-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="4538f-183">Para quitar un proveedor de escenario</span><span class="sxs-lookup"><span data-stu-id="4538f-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="4538f-184">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4538f-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4538f-185">Los cmdlets aquí suministrados permiten crear proveedores y actualizar los ya existentes.</span><span class="sxs-lookup"><span data-stu-id="4538f-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="4538f-186">Para eliminar un proveedor, debe usar la directiva Replace del parámetro Provider de **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="4538f-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="4538f-187">La única forma de eliminar un proveedor por completo consiste en reemplazarlo por un proveedor predefinido que tenga el mismo nombre y usar la directiva Update.</span><span class="sxs-lookup"><span data-stu-id="4538f-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="4538f-188">Por ejemplo, nuestro proveedor LyssProvider se define con WPP como el tipo de registro, Level establecido en Debug y Flags set es\_TF Connection y\_TF diag.</span><span class="sxs-lookup"><span data-stu-id="4538f-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="4538f-189">Deberá cambiar las marcas a “All”.</span><span class="sxs-lookup"><span data-stu-id="4538f-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="4538f-190">Escriba lo siguiente para cambiar el proveedor:</span><span class="sxs-lookup"><span data-stu-id="4538f-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="4538f-191">Escriba lo siguiente si quiere eliminar por completo un escenario y sus proveedores correspondientes:</span><span class="sxs-lookup"><span data-stu-id="4538f-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="4538f-192">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4538f-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="4538f-193">El cmdlet <STRONG>Remove-CsClsScenario</STRONG> no pide confirmación.</span><span class="sxs-lookup"><span data-stu-id="4538f-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="4538f-194">El escenario se elimina junto con los proveedores que tenga asignados.</span><span class="sxs-lookup"><span data-stu-id="4538f-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="4538f-195">Puede crear el escenario de nuevo si vuelve a ejecutar los comandos que usó para crearlo.</span><span class="sxs-lookup"><span data-stu-id="4538f-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="4538f-196">No existe ningún procedimiento para recuperar escenarios o proveedores.</span><span class="sxs-lookup"><span data-stu-id="4538f-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="4538f-197">Cuando se elimina un escenario con el cmdlet **Remove-CsClsScenario**, se quita por completo del ámbito.</span><span class="sxs-lookup"><span data-stu-id="4538f-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="4538f-198">Para usar los escenarios que creó y los proveedores que formaban parte de ellos, deberá crear nuevos proveedores y asignarlos a un nuevo escenario.</span><span class="sxs-lookup"><span data-stu-id="4538f-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4538f-199">Vea también</span><span class="sxs-lookup"><span data-stu-id="4538f-199">See Also</span></span>


[<span data-ttu-id="4538f-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="4538f-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="4538f-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="4538f-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="4538f-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="4538f-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="4538f-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="4538f-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="4538f-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="4538f-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

