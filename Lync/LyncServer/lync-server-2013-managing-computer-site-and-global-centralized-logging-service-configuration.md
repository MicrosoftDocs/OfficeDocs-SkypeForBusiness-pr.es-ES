---
title: Administración de la configuración del servicio de registro centralizado de equipo, sitio y global
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d33a67b0b7e8c7e2771fbdc1055d003717dbb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="b680f-102">Administración de equipos, sitios y configuración del servicio de registro centralizado global en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b680f-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b680f-103">_**Última modificación del tema:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="b680f-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="b680f-104">El servicio de registro centralizado se puede ejecutar en un ámbito que incluya un solo equipo, un grupo de equipos, en un ámbito de sitio (es decir, un sitio definido, como el sitio Redmond, que contiene una colección de equipos y grupos de servidores de la implementación) o en un ámbito global (es decir, , todos los equipos y grupos de la implementación).</span><span class="sxs-lookup"><span data-stu-id="b680f-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="b680f-105">Para configurar el ámbito del servicio de registro centralizado mediante el shell de administración de Lync Server, debe ser miembro de los grupos de seguridad CsAdministrator o CsServerAdministrator role-based access control (RBAC), o un rol RBAC personalizado que contenga cualquiera de estos dos grupos.</span><span class="sxs-lookup"><span data-stu-id="b680f-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="b680f-106">Para devolver una lista de todos los roles RBAC a los que se ha asignado este cmdlet (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando desde el shell de administración de Lync Server o el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b680f-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="b680f-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b680f-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="b680f-108">Windows PowerShell proporciona más opciones y opciones de configuración adicionales que no están disponibles mediante CLSController. exe.</span><span class="sxs-lookup"><span data-stu-id="b680f-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="b680f-109">CLSController ofrece un método rápido y conciso de ejecutar comandos, pero está limitado al conjunto de comandos disponible para CLSController.</span><span class="sxs-lookup"><span data-stu-id="b680f-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="b680f-110">Windows PowerShell no está limitado solo al comando disponible para el procesador de comandos de la CLSController y proporciona un conjunto más amplio de comandos y un conjunto más amplio de opciones.</span><span class="sxs-lookup"><span data-stu-id="b680f-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="b680f-111">Por ejemplo, CLSController.exe proporciona las opciones de ámbito -computers y -pools.</span><span class="sxs-lookup"><span data-stu-id="b680f-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="b680f-112">Con Windows PowerShell, puede indicar equipos o grupos en la mayoría de los comandos y, cuando define nuevos escenarios (CLSController tiene un número finito de escenarios que no son modificables por el usuario), puede definir un ámbito global o de sitio.</span><span class="sxs-lookup"><span data-stu-id="b680f-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="b680f-113">Esta eficaz característica de Windows PowerShell permite definir un escenario de un sitio o un ámbito global, pero limita el registro real a un equipo o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="b680f-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="b680f-114">Existen diferencias fundamentales entre los comandos de la línea de comandos que se pueden ejecutar en Windows PowerShell o CLSController.</span><span class="sxs-lookup"><span data-stu-id="b680f-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="b680f-115">Windows PowerShell proporciona un método enriquecido para configurar y definir escenarios y reutilizarlos de forma significativa para los escenarios de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="b680f-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="b680f-116">Aunque CLSController ofrece una manera rápida y eficaz de ejecutar comandos y obtener resultados, el conjunto de comandos de CLSController se limita al número finito de comandos que hay disponibles en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b680f-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="b680f-117">A diferencia de los cmdlets de Windows PowerShell, CLSController no puede definir nuevos escenarios, administrar ámbitos en un sitio o nivel global, y muchas otras limitaciones de un conjunto de comandos finito que no se pueden configurar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="b680f-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="b680f-118">Aunque CLSController proporciona un medio para una ejecución rápida, Windows PowerShell ofrece un medio para extender la funcionalidad del servicio de registro centralizado más allá de lo que es posible con CLSController.</span><span class="sxs-lookup"><span data-stu-id="b680f-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="b680f-119">Se puede definir un ámbito de un solo equipo durante la ejecución de un comando [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) y [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) mediante el parámetro – Computers.</span><span class="sxs-lookup"><span data-stu-id="b680f-119">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) command using the –Computers parameter.</span></span> <span data-ttu-id="b680f-120">El parámetro –Computers acepta una lista separada por comas de nombres de dominio completos (FQDN) del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="b680f-120">The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="b680f-121">También puede especificar –Pools y una lista separada por comas de los grupos donde quiera ejecutar los comandos de registro.</span><span class="sxs-lookup"><span data-stu-id="b680f-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="b680f-122">Los ámbitos de sitio y global se definen en los cmdlets del servicio de registro **nuevo-**, **set-** y **Remove-** centralizados.</span><span class="sxs-lookup"><span data-stu-id="b680f-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="b680f-123">En los siguientes ejemplos se muestra cómo establecer un ámbito de sitio y un ámbito global.</span><span class="sxs-lookup"><span data-stu-id="b680f-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b680f-124">Los comandos mostrados pueden contener parámetros y conceptos tratados en otras secciones.</span><span class="sxs-lookup"><span data-stu-id="b680f-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="b680f-125">Los comandos de ejemplo pretenden mostrar el uso del parámetro <STRONG>–Identity</STRONG> para definir el ámbito, y los demás parámetros se incluyen para completar la información y para especificar el ámbito.</span><span class="sxs-lookup"><span data-stu-id="b680f-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="b680f-126">Para obtener más información sobre los cmdlets de <STRONG>Set-CsClsConfiguration</STRONG>, consulte <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="b680f-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="b680f-127">Para recuperar la configuración actual del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="b680f-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="b680f-128">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b680f-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b680f-129">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b680f-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="b680f-130">Use los cmdlets **New-CsClsConfiguration** y **Set-CsClsConfiguration** para crear una nueva configuración o para actualizar una configuración existente.</span><span class="sxs-lookup"><span data-stu-id="b680f-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="b680f-131">Al ejecutar **Get-CsClsConfiguration**, se muestra información similar a la siguiente captura de pantalla, en la que la implementación tiene actualmente la configuración global predeterminada, pero no hay ninguna configuración de sitio definida:</span><span class="sxs-lookup"><span data-stu-id="b680f-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="b680f-132">![Resultado de ejemplo de Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Resultado de ejemplo de Get-CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="b680f-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="b680f-133">Para recuperar la configuración actual del servicio de registro centralizado desde el almacén local del equipo</span><span class="sxs-lookup"><span data-stu-id="b680f-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="b680f-134">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b680f-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b680f-135">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b680f-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="b680f-136">Cuando se usa el primer ejemplo en el que **Get-CsClsConfiguration** no especifica ningún parámetro, el comando hace referencia al almacén de administración central para los datos.</span><span class="sxs-lookup"><span data-stu-id="b680f-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="b680f-137">Si especifica el parámetro – LocalStore, el comando hace referencia al equipo LocalStore en lugar del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="b680f-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="b680f-138">Para recuperar la lista de los escenarios actualmente definidos</span><span class="sxs-lookup"><span data-stu-id="b680f-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="b680f-139">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b680f-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b680f-140">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b680f-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="b680f-141">Por ejemplo, para recuperar los escenarios definidos en el ámbito global:</span><span class="sxs-lookup"><span data-stu-id="b680f-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="b680f-142">El cmdlet **Get-CsClsConfiguration** siempre muestra los escenarios que forman parte de la configuración de un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="b680f-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="b680f-143">En la mayoría de los casos, no se muestran todos los escenarios y están truncados.</span><span class="sxs-lookup"><span data-stu-id="b680f-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="b680f-144">El comando usado aquí enumera todos los escenarios e información parcial acerca de los proveedores, la configuración y los indicadores que se utilizan.</span><span class="sxs-lookup"><span data-stu-id="b680f-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="b680f-145">Para actualizar un ámbito global para el servicio de registro centralizado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b680f-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="b680f-146">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b680f-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b680f-147">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b680f-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="b680f-148">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b680f-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="b680f-p109">El comando indica a CLSAgent en cada equipo y grupo de la implementación que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando afectará a los equipos y grupos de todos los sitios, y establecerá el valor de sustitución del registro de seguimiento en 40 megabytes.</span><span class="sxs-lookup"><span data-stu-id="b680f-p109">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="b680f-151">Para actualizar un ámbito de sitio para el servicio de registro centralizado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b680f-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="b680f-152">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b680f-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b680f-153">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b680f-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="b680f-154">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b680f-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b680f-p110">Como se indica en el ejemplo, la ubicación predeterminada de los archivos de registro es %TEMP%\Tracing. Sin embargo, como es CLSAgent quien realmente escribe en el archivo y CLSAgent se ejecuta como un servicio de red, la variable %TEMP% se expande a %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="b680f-p110">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="b680f-p111">El comando indica a CLSAgent en cada equipo y grupo del sitio Redmond que establezca el tamaño del valor de sustitución en el archivo de seguimiento en 40 megabytes. El comando no afectará a los equipos y grupos de los demás sitios, y continuarán usando el valor de sustitución del registro de seguimiento definido de forma predeterminada (20 megabytes) o al inicio de la sesión de registro.</span><span class="sxs-lookup"><span data-stu-id="b680f-p111">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="b680f-159">Para crear una nueva configuración del servicio de registro centralizado</span><span class="sxs-lookup"><span data-stu-id="b680f-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="b680f-160">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b680f-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b680f-161">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b680f-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b680f-162">New-CsClsConfiguration proporciona acceso a un gran número de opciones de configuración opcionales.</span><span class="sxs-lookup"><span data-stu-id="b680f-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="b680f-163">Para obtener más información sobre las opciones de configuración, consulte <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> y <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding centralizated Logging Services Configuration Settings in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b680f-163">For details about the configuration options, see <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="b680f-164">Por ejemplo, para crear una nueva configuración que define una carpeta de red para archivos de caché, el período de tiempo de sustitución para los archivos de registro y el tamaño de sustitución para los archivos de registro, escribiría:</span><span class="sxs-lookup"><span data-stu-id="b680f-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="b680f-165">Debe planear cuidadosamente la creación de nuevas configuraciones y cómo definir nuevas propiedades para el servicio de registro centralizado.</span><span class="sxs-lookup"><span data-stu-id="b680f-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="b680f-166">Debe tener precaución a la hora de realizar cambios y asegurarse de que comprende cómo afectan a su capacidad para registrar correctamente escenarios de problemas.</span><span class="sxs-lookup"><span data-stu-id="b680f-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="b680f-167">Debe realizar cambios en la configuración que mejoren su capacidad para administrar los registros y establecer un tamaño y un período de sustitución que permitan resolver el problema cuando se produzca.</span><span class="sxs-lookup"><span data-stu-id="b680f-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="b680f-168">Para quitar una configuración del servicio de registro centralizado existente</span><span class="sxs-lookup"><span data-stu-id="b680f-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="b680f-169">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b680f-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b680f-170">Escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b680f-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="b680f-171">Por ejemplo, para quitar la configuración del servicio de registro centralizado que ha creado para aumentar el tiempo de sustitución del archivo de registro, aumente el tamaño del archivo de registro de sustitución y establezca la ubicación de la caché del archivo de registro en un recurso compartido de red de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b680f-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b680f-172">Esta es la nueva configuración que se creó en el procedimiento "para crear una nueva configuración del servicio de registro centralizado".</span><span class="sxs-lookup"><span data-stu-id="b680f-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="b680f-173">Si decide quitar una configuración en el nivel de sitio, el sitio usará la configuración global.</span><span class="sxs-lookup"><span data-stu-id="b680f-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b680f-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="b680f-174">See Also</span></span>


[<span data-ttu-id="b680f-175">Información general sobre el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b680f-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="b680f-176">Administración de las opciones de configuración del servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b680f-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="b680f-177">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b680f-177">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="b680f-178">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b680f-178">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="b680f-179">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b680f-179">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="b680f-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b680f-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

