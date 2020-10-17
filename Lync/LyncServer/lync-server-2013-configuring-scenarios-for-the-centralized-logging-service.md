---
title: 'Lync Server 2013: configuración de escenarios para el servicio de registro centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 505ae775e2735ba01bd02cd0104240ad8781f968
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502077"
---
# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="9008d-102">Configuración de escenarios para el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9008d-102">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9008d-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="9008d-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="9008d-104">Los escenarios definen el ámbito (es decir, global, sitio, grupo o equipo) y qué proveedores usar en el servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="9008d-104">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="9008d-105">Al usar escenarios, puede habilitar o deshabilitar el seguimiento de proveedores (por ejemplo, S4, SIPStack, mensajería instantánea y presencia).</span><span class="sxs-lookup"><span data-stu-id="9008d-105">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="9008d-106">Al configurar un escenario, puede agrupar todos los proveedores de una colección lógica determinada que aborda una condición para un problema concreto.</span><span class="sxs-lookup"><span data-stu-id="9008d-106">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="9008d-107">Si observa que es necesario modificar un escenario para satisfacer sus necesidades de registro y solución de problemas, las herramientas de depuración de Lync Server 2013 le proporcionan un módulo de Windows PowerShell denominado *ClsController. psm1* que contiene una función denominada *Edit-CsClsScenario*.</span><span class="sxs-lookup"><span data-stu-id="9008d-107">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Lync Server 2013 Debug Tools provides you a Windows PowerShell module named *ClsController.psm1* that contains a function named *Edit-CsClsScenario*.</span></span> <span data-ttu-id="9008d-108">El propósito del módulo es editar las propiedades del escenario en cuestión.</span><span class="sxs-lookup"><span data-stu-id="9008d-108">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="9008d-109">En este tema se muestran ejemplos del funcionamiento del módulo.</span><span class="sxs-lookup"><span data-stu-id="9008d-109">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="9008d-110">Las herramientas de depuración de Lync Server 2013 se descargan desde el siguiente vínculo: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span><span class="sxs-lookup"><span data-stu-id="9008d-110">The Lync Server 2013 Debug Tools are downloaded from the following link: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9008d-111">Para cualquier ámbito dado (sitio, global, grupo o equipo), puede ejecutar un máximo de dos escenarios en cualquier momento dado.</span><span class="sxs-lookup"><span data-stu-id="9008d-111">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="9008d-112">Para determinar qué escenarios se están ejecutando actualmente, use Windows PowerShell y <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span><span class="sxs-lookup"><span data-stu-id="9008d-112">To determine which scenarios are currently running, use Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span></span> <span data-ttu-id="9008d-113">Mediante el uso de Windows PowerShell y <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">set-CsClsScenario</A>, puede cambiar dinámicamente los escenarios que se están ejecutando.</span><span class="sxs-lookup"><span data-stu-id="9008d-113">By using Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="9008d-114">Puede modificar los escenarios que se ejecutan durante una sesión de registro para ajustar o refinar los datos que va a recopilar y de qué proveedores.</span><span class="sxs-lookup"><span data-stu-id="9008d-114">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span>



</div>

<span data-ttu-id="9008d-115">Para ejecutar las funciones del servicio de registro centralizado mediante el shell de administración de Lync Server, debe ser miembro de los grupos de seguridad CsAdministrator o CsServerAdministrator role-based access control (RBAC), o un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="9008d-115">To run the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="9008d-116">Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet, incluidos todos los roles RBAC personalizados que haya creado, ejecute el siguiente comando desde el shell de administración de Lync Server o el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9008d-116">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="9008d-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9008d-117">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="9008d-118">El resto de este tema se centra en cómo definir un escenario, modificar un escenario, recuperar los escenarios que se están ejecutando, quitar un escenario y especificar lo que contiene un escenario para optimizar la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="9008d-118">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="9008d-119">Hay dos formas de emitir comandos de servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="9008d-119">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="9008d-120">Puede usar el CLSController.exe ubicado, de forma predeterminada, en el directorio C: archivos \\ comunes de archivos de programa \\ \\ Microsoft Lync Server 2013 \\ CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="9008d-120">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="9008d-121">O bien, puede usar el shell de administración de Lync Server para emitir comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9008d-121">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="9008d-122">La diferencia importante es que, cuando se usa CLSController.exe en la línea de comandos, hay disponible una selección finita de escenarios.</span><span class="sxs-lookup"><span data-stu-id="9008d-122">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available.</span></span> <span data-ttu-id="9008d-123">Cuando usa Windows PowerShell, puede definir nuevos escenarios para usarlos en sus sesiones de registro.</span><span class="sxs-lookup"><span data-stu-id="9008d-123">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>

<span data-ttu-id="9008d-124">Como se ha incluido en [información general del servicio de registro centralizado en Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), los elementos de un escenario son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9008d-124">As introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the elements of a scenario are:</span></span>

  - <span data-ttu-id="9008d-125">**Proveedores**     Si está familiarizado con OCSLogger, los proveedores son los componentes que elija para determinar OCSLogger de qué debe recopilar los registros el motor de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9008d-125">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="9008d-126">Los proveedores son los mismos componentes y en muchos casos tienen los mismos nombres que los componentes de OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="9008d-126">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="9008d-127">Si no está familiarizado con OCSLogger, los proveedores son componentes específicos de roles de servidor de los que el servicio de registro centralizado puede recopilar registros.</span><span class="sxs-lookup"><span data-stu-id="9008d-127">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="9008d-128">Para obtener más información sobre la configuración de los proveedores, consulte [configuración de proveedores para el servicio de registro centralizado en Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span><span class="sxs-lookup"><span data-stu-id="9008d-128">For details about the configuration of providers, see [Configuring providers for Centralized Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span></span>

  - <span data-ttu-id="9008d-129">**Identidad**     El parámetro – Identity establece el ámbito y el nombre del escenario.</span><span class="sxs-lookup"><span data-stu-id="9008d-129">**Identity**   The parameter –Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="9008d-130">Por ejemplo, puede establecer un ámbito “global” e identificar el escenario como “LyssServiceScenario”.</span><span class="sxs-lookup"><span data-stu-id="9008d-130">For example, you could set a scope of “global” and identify the scenario with “LyssServiceScenario”.</span></span> <span data-ttu-id="9008d-131">Cuando se combinan ambos, se define la identidad, que en este caso sería “global/LyssServiceScenario”.</span><span class="sxs-lookup"><span data-stu-id="9008d-131">When you combine the two, you define the Identity (for example, “global/LyssServiceScenario”).</span></span>
    
    <span data-ttu-id="9008d-p107">Si lo desea, puede usar los parámetros –Name y –Parent. Si utiliza el parámetro Name, que únicamente sirve para identificar el escenario, también deberá usar el parámetro Parent para agregar el escenario a "global" o a "site".</span><span class="sxs-lookup"><span data-stu-id="9008d-p107">Optionally, you can use the –Name and –Parent parameters. You define the Name parameter to uniquely identify the scenario. If you use Name, you must also use Parent to add the scenario to either global or site.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9008d-135">Si usa los parámetros Name y Parent, no puede usar el parámetro <STRONG>–Identity</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9008d-135">If you use the Name and Parent parameters, you cannot use the <STRONG>–Identity</STRONG> parameter.</span></span>

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="9008d-136">Para crear un escenario con el cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="9008d-136">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="9008d-137">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9008d-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9008d-138">Para crear un escenario para una sesión de registro, utilice [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) y defina el nombre del escenario (es decir, un nombre de identificación único).</span><span class="sxs-lookup"><span data-stu-id="9008d-138">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="9008d-139">Elija un tipo de formato de registro de WPP (es decir, el preprocesador de seguimiento del software de Windows; es el predeterminado), EventLog (el formato de registro de eventos de Windows) o IISLog (el archivo de formato basado en el formato de archivo de registro de IIS).</span><span class="sxs-lookup"><span data-stu-id="9008d-139">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="9008d-140">A continuación, defina Level y Flags tal como se definen en este tema los niveles de registro y las etiquetas, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9008d-140">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="9008d-141">Para este escenario de muestra, utilizaremos LyssProvider como variable del proveedor.</span><span class="sxs-lookup"><span data-stu-id="9008d-141">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="9008d-142">Para crear un escenario con las opciones especificadas, escriba:</span><span class="sxs-lookup"><span data-stu-id="9008d-142">To create a scenario using the options defined, type:</span></span>
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    <span data-ttu-id="9008d-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9008d-143">For example:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    <span data-ttu-id="9008d-144">Formato alternativo en el que se usan –Name y –Parent:</span><span class="sxs-lookup"><span data-stu-id="9008d-144">The alternate format using –Name and –Parent:</span></span>
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="9008d-145">Para crear un escenario con varios proveedores con el cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="9008d-145">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="9008d-146">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9008d-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9008d-147">Por cada ámbito puede haber un máximo de dos escenarios.</span><span class="sxs-lookup"><span data-stu-id="9008d-147">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="9008d-148">Sin embargo, el número de proveedores no está limitado.</span><span class="sxs-lookup"><span data-stu-id="9008d-148">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="9008d-149">Para este ejemplo, supongamos que ha creado tres proveedores y que desea asignarlos al escenario que está definiendo.</span><span class="sxs-lookup"><span data-stu-id="9008d-149">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="9008d-150">Los nombres de la variable "provider" son LyssProvider, ABServerProvider y SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="9008d-150">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="9008d-151">Para definir y asignar varios proveedores a un escenario, escriba lo siguiente en un shell de administración de Lync Server o un símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9008d-151">To define and assign multiple providers to a scenario, type the following at a Lync Server Management Shell or Windows PowerShell command prompt:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9008d-152">Como se conoce en Windows PowerShell, la Convención para crear una tabla hash de valores con <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> se conoce como <EM>expansión</EM>.</span><span class="sxs-lookup"><span data-stu-id="9008d-152">As it is known in Windows PowerShell, the convention for creating a hash table of values using <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> is known as <EM>splatting</EM>.</span></span> <span data-ttu-id="9008d-153">Para obtener más información sobre expansión en Windows PowerShell, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A> .</span><span class="sxs-lookup"><span data-stu-id="9008d-153">For details about splatting in Windows PowerShell, see <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="9008d-154">Para modificar un escenario existente con el cmdlet Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="9008d-154">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="9008d-155">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9008d-155">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9008d-p111">Por cada ámbito puede haber un máximo de dos escenarios. Puede cambiar los escenarios que estén en ejecución en cualquier momento, incluso si hay una sesión de captura de registros en proceso. Si redefine los escenarios que se están ejecutándose, la sesión de registro actual dejará de usar el escenario que se haya quitado y comenzará a usar el escenario nuevo. No obstante, la información de registro que se capturó con el escenario que se haya quitado se mantendrá en los registros capturados. Para definir un escenario nuevo, introduzca lo siguiente (asumiendo que se definió un proveedor con el nombre “S4Provider”):</span><span class="sxs-lookup"><span data-stu-id="9008d-p111">You are limited to two scenarios per scope. You can change which scenarios are running at any time, even when a logging capture session is in process. If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario. However, the logging information that was captured with the removed scenario remains in the captured logs. To define a new scenario, do the following (that is, assuming the addition of an already defined provider named “S4Provider”):</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    <span data-ttu-id="9008d-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9008d-161">For example:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    <span data-ttu-id="9008d-p112">Si desea reemplazar los proveedores, defina un único proveedor o bien una lista de proveedores separados entre sí por comas para cambiar el conjunto actual. Si solo desea reemplazar uno de los proveedores, agregue los proveedores actuales a los nuevos para crear un conjunto de proveedores distinto que contenga tanto los proveedores existentes como los nuevos. Para reemplazar todos los proveedores con un conjunto nuevo, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9008d-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    <span data-ttu-id="9008d-165">Por ejemplo, para reemplazar el conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, el código sería:</span><span class="sxs-lookup"><span data-stu-id="9008d-165">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    <span data-ttu-id="9008d-166">Para reemplazar solo el proveedor $LyssProvider del conjunto actual de $LyssProvider, $ABServerProvider y $SIPStackProvider con $LyssServiceProvider, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9008d-166">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="9008d-167">Para quitar un escenario existente con el cmdlet Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="9008d-167">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="9008d-168">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9008d-168">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9008d-169">Si desea quitar un escenario que se definió previamente, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9008d-169">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    <span data-ttu-id="9008d-170">Por ejemplo, para reemplazar el escenario definido con site:Redmond/LyssServiceScenario, el código sería:</span><span class="sxs-lookup"><span data-stu-id="9008d-170">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

<span data-ttu-id="9008d-171">El cmdlet **Remove-CsClsScenario** quita el escenario especificado, pero los datos de seguimiento que se hayan capturado seguirán disponibles en los registros para su consulta.</span><span class="sxs-lookup"><span data-stu-id="9008d-171">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a><span data-ttu-id="9008d-172">Para cargar y descargar el cmdlet Edit-CsClsScenario con el módulo ClsController.psm1</span><span class="sxs-lookup"><span data-stu-id="9008d-172">To load and unload the Edit-CsClsScenario cmdlet using the ClsController.psm1 module</span></span>

1.  <span data-ttu-id="9008d-173">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9008d-173">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9008d-174">El módulo ClsController. psm1 se proporciona como una descarga web independiente.</span><span class="sxs-lookup"><span data-stu-id="9008d-174">The ClsController.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="9008d-175">El módulo es parte de las herramientas de depuración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9008d-175">The module is part of the Lync Server 2013 Debugging tools.</span></span> <span data-ttu-id="9008d-176">De forma predeterminada, las herramientas de depuración se instalan en el directorio C:\Archivos de Files\Lync Server 2013 \ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="9008d-176">By default, the debugging tools are installed in the directory C:\Program Files\Lync Server 2013\Debugging Tools.</span></span>

    
    </div>

2.  <span data-ttu-id="9008d-177">En Windows PowerShell, escriba:</span><span class="sxs-lookup"><span data-stu-id="9008d-177">From the Windows PowerShell, type:</span></span>
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="9008d-178">La correcta carga del módulo le devuelve al símbolo del sistema de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9008d-178">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="9008d-179">Para confirmar que el módulo está cargado y que Edit-CsClsScenario está disponible, escriba <CODE>Get-Help Edit-CsClsScenario</CODE> .</span><span class="sxs-lookup"><span data-stu-id="9008d-179">To confirm that the module is loaded and that Edit-CsClsScenario is available, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="9008d-180">Debería ver una muestra general de la sintaxis de EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="9008d-180">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span>

    
    </div>

3.  <span data-ttu-id="9008d-181">Para descargar los módulos, escriba:</span><span class="sxs-lookup"><span data-stu-id="9008d-181">To unload the modules, type:</span></span>
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="9008d-182">La descarga correcta del módulo le devuelve al símbolo del sistema de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9008d-182">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="9008d-183">Para confirmar que el módulo se ha descargado, escriba <CODE>Get-Help Edit-CsClsScenario</CODE> .</span><span class="sxs-lookup"><span data-stu-id="9008d-183">To confirm that the module is unloaded, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="9008d-184">Windows PowerShell intentará buscar la ayuda para el cmdlet y se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="9008d-184">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="9008d-185">Para quitar un proveedor existente de un escenario con el módulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="9008d-185">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="9008d-186">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9008d-186">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9008d-187">Para quitar un proveedor del escenario AlwaysOn, escriba:</span><span class="sxs-lookup"><span data-stu-id="9008d-187">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    <span data-ttu-id="9008d-188">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9008d-188">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    <span data-ttu-id="9008d-p116">ScenarioName y ProviderName son parámetros de posición (es decir, es necesario que se definan en una posición determinada en la línea de comandos). El nombre de los parámetros no tiene que definirse explícitamente si el nombre del escenario ocupa el segundo lugar y el proveedor ocupa el tercero tomando como referencia el nombre del cmdlet, que aparece en primer lugar. Teniendo en cuenta esta información, el comando anterior quedaría así:</span><span class="sxs-lookup"><span data-stu-id="9008d-p116">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    <span data-ttu-id="9008d-p117">La colocación posicional de los valores de parámetro solo se aplica a –Scenario y –Provider. Todos los demás parámetros se deben definir explícitamente.</span><span class="sxs-lookup"><span data-stu-id="9008d-p117">The positional placing of the parameter values applies only to –Scenario and –Provider. All other parameters must be explicitly defined.</span></span>

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="9008d-194">Para agregar un proveedor a un escenario con el módulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="9008d-194">To add a provider to a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="9008d-195">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9008d-195">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9008d-196">Para agregar un proveedor al escenario AlwaysOn, escriba:</span><span class="sxs-lookup"><span data-stu-id="9008d-196">To add a provider to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    <span data-ttu-id="9008d-197">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9008d-197">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    <span data-ttu-id="9008d-198">\-LogLevel puede ser del tipo error, error, ADVERTENCIA, información, detallado, depurar o todos.</span><span class="sxs-lookup"><span data-stu-id="9008d-198">\-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="9008d-199">– Flags puede ser cualquiera de las marcas admitidas por el proveedor, como TF \_ Component, TF \_ diag.</span><span class="sxs-lookup"><span data-stu-id="9008d-199">–Flags can be any of the flags that the provider supports, such as TF\_COMPONENT, TF\_DIAG.</span></span> <span data-ttu-id="9008d-200">– LAS marcas también pueden ser del valor ALL</span><span class="sxs-lookup"><span data-stu-id="9008d-200">–Flags can also be of value ALL</span></span>
    
    <span data-ttu-id="9008d-p119">El ejemplo anterior también se puede introducir usando la característica de colocación posicional del cmdlet. Por ejemplo, para agregar el proveedor ChatServer al escenario AlwaysOn, el código quedaría así:</span><span class="sxs-lookup"><span data-stu-id="9008d-p119">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

