---
title: 'Lync Server 2013: habilitar o deshabilitar el modo crítico para bloquear o permitir sesiones de mensajería instantánea y Web si se produce un error de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="456d7-102">Habilitar o deshabilitar el modo crítico en Lync Server 2013 para bloquear o permitir sesiones de mensajería instantánea y Web si se produce un error de archivado</span><span class="sxs-lookup"><span data-stu-id="456d7-102">Enabling or disabling critical mode in Lync Server 2013 to block or allow IM and web conferencing sessions if Archiving fails</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="456d7-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="456d7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="456d7-104">En el panel de control de Lync Server 2013, se usan configuraciones de archivado para habilitar y deshabilitar el modo crítico.</span><span class="sxs-lookup"><span data-stu-id="456d7-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable critical mode.</span></span> <span data-ttu-id="456d7-105">Esto incluye las siguientes configuraciones de archivado:</span><span class="sxs-lookup"><span data-stu-id="456d7-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="456d7-106">Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="456d7-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="456d7-107">Configuraciones de nivel de sitio y de grupo opcionales que puede crear y usar para especificar cómo se implementa el archivado para grupos o sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="456d7-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="456d7-108">Inicialmente, debe configurar las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="456d7-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="456d7-109">Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, implementación documentación u operación.</span><span class="sxs-lookup"><span data-stu-id="456d7-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="456d7-110">Para usar el archivado, debe configurar las directivas de archivado para especificar si desea habilitar el archivado de las comunicaciones internas, de las comunicaciones externas o de ambos para los usuarios alojados en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="456d7-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="456d7-111">De forma predeterminada, el archivado no está habilitado para las comunicaciones internas o externas.</span><span class="sxs-lookup"><span data-stu-id="456d7-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="456d7-112">Antes de habilitar el archivado en cualquier directiva, debe especificar las configuraciones de archivado apropiadas para su implementación y, opcionalmente, para determinados sitios y grupos, tal y como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="456d7-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="456d7-113">Para obtener más información sobre cómo habilitar el archivado, vea <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar y asignar directivas de archivado en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="456d7-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="456d7-114">Si decide que después de implementar el archivado desea usar la integración de Exchange Server para almacenar datos y archivos en servidores de Exchange 2013 y todos los usuarios están alojados en los servidores de Exchange 2013, debe quitar la configuración de la base de datos de SQL Server de su topología.</span><span class="sxs-lookup"><span data-stu-id="456d7-114">If you decide after you deploy Archiving that you want to use Exchange Server integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="456d7-115">Para ello, debe usar el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="456d7-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="456d7-116">Para obtener más información, vea <A href="lync-server-2013-changing-archiving-database-options.md">cambiar las opciones de base de datos de archivado en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="456d7-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a><span data-ttu-id="456d7-117">Para habilitar o deshabilitar el bloqueo de las sesiones de mensajería instantánea y conferencias web si falla el archivado</span><span class="sxs-lookup"><span data-stu-id="456d7-117">To enable or disable blocking of IM and web conferencing sessions if archiving fails</span></span>

1.  <span data-ttu-id="456d7-118">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="456d7-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="456d7-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="456d7-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="456d7-120">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="456d7-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="456d7-121">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="456d7-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="456d7-122">Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado; haga clic en **Editar**, en **Mostrar detalles** y, luego, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="456d7-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>

5.  <span data-ttu-id="456d7-123">Para configurar el comportamiento del archivado cuando se produzca un error, active o desactive la casilla **Bloquear sesiones de mensajería instantánea o conferencias web si no se pueden archivar**.</span><span class="sxs-lookup"><span data-stu-id="456d7-123">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>

6.  <span data-ttu-id="456d7-124">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="456d7-124">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="456d7-125">Habilitar y deshabilitar el modo crítico mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="456d7-125">Enabling and Disabling Critical Mode by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="456d7-126">Puede habilitar o deshabilitar el modo crítico con el cmdlet **set-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="456d7-126">You can enable or disable critical mode using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="456d7-127">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="456d7-127">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="456d7-128">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="456d7-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-critical-mode"></a><span data-ttu-id="456d7-129">Para habilitar el modo crítico</span><span class="sxs-lookup"><span data-stu-id="456d7-129">To enable critical mode</span></span>

  - <span data-ttu-id="456d7-130">Para habilitar el modo crítico, establezca el valor de la propiedad BlockOnArchiveFailure en true ($True).</span><span class="sxs-lookup"><span data-stu-id="456d7-130">To enable critical mode, set the value of the BlockOnArchiveFailure property to True ($True).</span></span> <span data-ttu-id="456d7-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="456d7-131">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a><span data-ttu-id="456d7-132">Para deshabilitar el modo crítico</span><span class="sxs-lookup"><span data-stu-id="456d7-132">To disable critical mode</span></span>

  - <span data-ttu-id="456d7-133">Para deshabilitar el modo crítico, establece el valor de la propiedad BlockOnArchiveFailure en false ($False).</span><span class="sxs-lookup"><span data-stu-id="456d7-133">To disable critical mode, set the value of the BlockOnArchiveFailure property to False ($False).</span></span> <span data-ttu-id="456d7-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="456d7-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

<span data-ttu-id="456d7-135">Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="456d7-135">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="456d7-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="456d7-136">See Also</span></span>


[<span data-ttu-id="456d7-137">Cambiar las opciones de base de datos de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="456d7-137">Changing Archiving database options in Lync Server 2013</span></span>](lync-server-2013-changing-archiving-database-options.md)  


[<span data-ttu-id="456d7-138">Cómo funciona el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="456d7-138">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="456d7-139">Administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos</span><span class="sxs-lookup"><span data-stu-id="456d7-139">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

