---
title: 'Lync Server 2013: habilitar o deshabilitar la depuración de datos archivados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f74963f080c244f375bac0ea00ab152e89cc2723
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a><span data-ttu-id="2b1ee-102">Habilitación o deshabilitación de la purga de datos archivados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b1ee-102">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b1ee-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2b1ee-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2b1ee-104">En el panel de control de 2013 de Lync Server, se usan configuraciones de archivado para habilitar y deshabilitar la purga y configurar la forma en que se implementa la purga.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable purging and configure how purging is implemented.</span></span> <span data-ttu-id="2b1ee-105">Esto incluye las siguientes configuraciones de archivado:</span><span class="sxs-lookup"><span data-stu-id="2b1ee-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="2b1ee-106">Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="2b1ee-107">Unas configuraciones en el nivel de sitio y de grupo que se pueden crear y usar para especificar cómo se implementa el archivado en sitios o grupos determinados.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="2b1ee-108">Las configuraciones de archivado se instalan inicialmente al implementar el archivado, pero podrá cambiar, agregar y eliminar las configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="2b1ee-109">Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b1ee-110">Para usar el archivado para los usuarios hospedados en Lync Server 2013, debe configurar las directivas de archivado para especificar si desea habilitar el archivado para las comunicaciones internas, para las comunicaciones externas o para ambos.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-110">To use archiving for users who are homed on Lync Server 2013 you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="2b1ee-111">De manera predeterminada, el archivado no está habilitado para las comunicaciones ni internas, ni externas.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="2b1ee-112">Antes de habilitar el archivado en ninguna directiva, debe especificar las configuraciones de archivado apropiadas para su implementación y, si lo desea, para sitios y grupos de servidores concretos, como se describe en este apartado.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="2b1ee-113">Para obtener más información sobre cómo habilitar el archivado, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuración y asignación de directivas de archivado en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="2b1ee-114">Si decide después de implementar el archivado que desea usar la integración de Microsoft Exchange para almacenar los datos y archivos de archivado en servidores de Exchange 2013 y todos los usuarios están alojados en los servidores de Exchange 2013, debe quitar la configuración de la base de datos de SQL Server. de la topología.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="2b1ee-115">Debe usar el generador de topologías para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="2b1ee-116">Para obtener más información, consulte <A href="lync-server-2013-changing-archiving-database-options.md">cambiar las opciones de base de datos de archivado en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a><span data-ttu-id="2b1ee-117">Para habilitar o deshabilitar la depuración para el archivado</span><span class="sxs-lookup"><span data-stu-id="2b1ee-117">To enable or disable purging for archiving</span></span>

1.  <span data-ttu-id="2b1ee-118">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2b1ee-119">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2b1ee-120">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2b1ee-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2b1ee-121">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="2b1ee-122">Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada de la lista de configuraciones de archivado, en **Editar** y en **Mostrar detalles**. A continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b1ee-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="2b1ee-123">Para habilitar la depuración, active la casilla **Habilitar purgado de los datos de archivado** y, a continuación, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2b1ee-123">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
        
          - <span data-ttu-id="2b1ee-124">Para purgar todos los registros, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y, a continuación, especifique el número de días.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-124">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="2b1ee-125">Para purgar solo los datos que se han exportado, haga clic en **depurar solo datos de archivado exportados**.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-125">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
      - <span data-ttu-id="2b1ee-126">Para deshabilitar la depuración, desactive la casilla **Habilitar purgado de los datos de archivado** .</span><span class="sxs-lookup"><span data-stu-id="2b1ee-126">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>

5.  <span data-ttu-id="2b1ee-127">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-127">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2b1ee-128">Habilitación o deshabilitación de la purga de datos de archivado con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b1ee-128">Enabling or Disabling the Purging of Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2b1ee-129">La habilitación y deshabilitación de la purga automatizada de datos de archivado se puede administrar con Windows PowerShell y el cmdlet **set-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2b1ee-129">Enabling and disabling the automated purging of archiving data can be managed by using Windows PowerShell and the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="2b1ee-130">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2b1ee-131">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="2b1ee-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a><span data-ttu-id="2b1ee-132">Para habilitar la purga de todos los datos de archivado</span><span class="sxs-lookup"><span data-stu-id="2b1ee-132">To enable the purging of all archiving data</span></span>

  - <span data-ttu-id="2b1ee-133">Para habilitar la purga de todos los datos de archivado, establezca la propiedad **EnablePurging** en true ($true).</span><span class="sxs-lookup"><span data-stu-id="2b1ee-133">To enable the purging of all archiving data set the **EnablePurging** property to true ($True).</span></span> <span data-ttu-id="2b1ee-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2b1ee-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    <span data-ttu-id="2b1ee-135">Después de ejecutar este comando, todos los días que Lync Server depurará todos los registros de archivado con una antigüedad superior al valor especificado para la propiedad **KeepArchivingDataForDays** .</span><span class="sxs-lookup"><span data-stu-id="2b1ee-135">After this command is run, then every day Lync Server will purge all archiving records older than the value specified for the **KeepArchivingDataForDays** property.</span></span>

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a><span data-ttu-id="2b1ee-136">Para habilitar la purga sólo de los datos de archivado exportados</span><span class="sxs-lookup"><span data-stu-id="2b1ee-136">To enable the purging only of exported archiving data</span></span>

  - <span data-ttu-id="2b1ee-137">Para limitar la purga a los registros de archivado que se han exportado a un archivo de datos (mediante el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), también debe establecer la propiedad PurgeExportedArchivesOnly en True ($true).</span><span class="sxs-lookup"><span data-stu-id="2b1ee-137">To limit purging to archiving records that have been exported to a data file (by using the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet) you must also set the PurgeExportedArchivesOnly property to True ($True).</span></span> <span data-ttu-id="2b1ee-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2b1ee-138">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    <span data-ttu-id="2b1ee-139">Después de ejecutar este comando, Lync Server solo purgará los registros de archivado que cumplan dos criterios: 1) son más antiguos que el valor especificado para la propiedad **KeepArchivingDataForDays** ; y 2) que se han exportado mediante el cmdlet **Export-CsArchivingData** .</span><span class="sxs-lookup"><span data-stu-id="2b1ee-139">After this command is run, Lync Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the **KeepArchivingDataForDays** property; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a><span data-ttu-id="2b1ee-140">Para deshabilitar la purga de todos los datos de archivado</span><span class="sxs-lookup"><span data-stu-id="2b1ee-140">To disable the purging of all archiving data</span></span>

  - <span data-ttu-id="2b1ee-141">Para deshabilitar la depuración automatizada de los registros de archivado, establezca la propiedad **EnablePurging** en False ($false).</span><span class="sxs-lookup"><span data-stu-id="2b1ee-141">To disable the automated purging of archiving records, set the **EnablePurging** property to False ($False).</span></span> <span data-ttu-id="2b1ee-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2b1ee-142">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

<span data-ttu-id="2b1ee-143">Para obtener más información, incluidas las opciones adicionales para purgar los datos de archivado, consulte el tema de ayuda del cmdlet [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="2b1ee-143">For more information, including additional options for purging archiving data, see the help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b1ee-144">Consulta también</span><span class="sxs-lookup"><span data-stu-id="2b1ee-144">See Also</span></span>


[<span data-ttu-id="2b1ee-145">Cómo funciona el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b1ee-145">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="2b1ee-146">Configuración y asignación de directivas de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b1ee-146">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[<span data-ttu-id="2b1ee-147">Administración de las opciones de configuración de archivado en Lync Server 2013 para la organización, los sitios y los grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="2b1ee-147">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

