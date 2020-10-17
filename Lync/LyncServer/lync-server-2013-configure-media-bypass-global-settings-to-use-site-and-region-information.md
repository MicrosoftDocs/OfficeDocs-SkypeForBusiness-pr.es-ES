---
title: Configurar las opciones globales de omisión de medios para usar información de sitio y región
description: Configure las opciones globales de omisión de medios para usar información de sitio y región.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a65dcec966030262d6d0fb5530b94f2411003c7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559806"
---
# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="b342d-103">Configurar las opciones globales de omisión de medios en Lync Server 2013 para usar la información de sitio y región</span><span class="sxs-lookup"><span data-stu-id="b342d-103">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b342d-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b342d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b342d-105">En este tema se asume que ya ha configurado el desvío de medios para todas las conexiones basadas en troncos desde el servidor de mediación a un servidor del mismo nivel (una puerta de enlace de la red telefónica conmutada (RTC), un sistema IP-PBX, o un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet (ITSP)) para un servicio o sitio específico para el que desea que los medios se desvíen del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="b342d-105">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="b342d-106">En este tema también se da por hecho que se han definido todos los sitios centrales y los sitios de sucursal en el generador de topologías de forma que coincidan con la región de red, el sitio de red y la configuración de subred que haya llevado a cabo siguiendo los pasos descritos en <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or Modify a Network region in Lync server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or 2013 Modify</A>a Network site <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">in Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="b342d-106">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="b342d-107">Si no coinciden, el desvío de medios no se realizará.</span><span class="sxs-lookup"><span data-stu-id="b342d-107">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="b342d-p102">Además de la habilitación del desvío de medios para conexiones individuales basadas en troncos asociadas a un servidor del mismo nivel, también deberá configurar opciones globales. Si usa los pasos que se muestran en este tema para configurar las opciones globales para el desvío de medios, se asume que una de las siguientes situaciones, o ambas, repercutirán en su configuración:</span><span class="sxs-lookup"><span data-stu-id="b342d-p102">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings. If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="b342d-110">*No* tiene buena conectividad entre los extremos de Lync Server y los homólogos para los que configuró el desvío de medios en la conexión troncal.</span><span class="sxs-lookup"><span data-stu-id="b342d-110">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="b342d-111">El control de admisión de llamadas (CAC) para la administración del ancho de banda está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b342d-111">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b342d-112">Para obtener más información acerca de las consideraciones para el control de admisión de llamadas y el desvío de medios, consulte la sección "control de admisión de llamadas de conexiones RTC" en servidor de omisión y mediación de <A href="lync-server-2013-media-bypass-and-mediation-server.md">medios en Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="b342d-112">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="b342d-p103">La información de región de red y sitio de red se comparte entre las características de Enterprise Voice avanzadas del control de admisión de llamadas y el desvío de medios cuando ambos están habilitados. Por consiguiente, si ya ha configurado el control de admisión de llamadas, no es necesario que realice el siguiente procedimiento para editar la información de región y sitio específica para el desvío de medios. Siga los pasos de este procedimiento si todavía no ha configurado los sitios y regiones de red para el control de admisión de llamadas y desea cambiar las opciones del desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="b342d-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="b342d-116">O bien, siga estos pasos si desea usar la información de sitio y región al tomar la decisión de desvío, pero no pretende habilitar el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b342d-116">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="b342d-117">En este caso, los vínculos restringidos de ancho de banda tendrán que representarse mediante directivas entre sitios de red, tal y como se describe en [Create Network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b342d-117">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="b342d-118">En este caso, las restricciones del ancho de banda real no son tan importantes, ya que no se ha habilitado el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b342d-118">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="b342d-119">En su lugar, se usan estos vínculos para que las subredes de división especifiquen cuáles son las que no presentan límites de ancho de banda y pueden usar, por consiguiente, el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="b342d-119">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="b342d-120">Tenga en cuenta que esto también es posible cuando se ha habilitado tanto el control de admisión de llamadas como el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="b342d-120">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="b342d-121">Además, para que el desvío funcione correctamente, debe existir coherencia entre un sitio definido en el generador de topologías y, como se define al configurar regiones de red y sitios de red.</span><span class="sxs-lookup"><span data-stu-id="b342d-121">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="b342d-122">Por ejemplo, si tiene un sitio de sucursal que ha definido en el generador de topologías que tiene solo una puerta de enlace RTC implementada, dicho sitio de sucursal debe configurarse con una directiva de telefonía IP empresarial que permita a los usuarios de sitios de sucursal tener sus llamadas RTC enrutadas a través de la puerta de enlace RTC en el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="b342d-122">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="b342d-123">Configurar la información de sitio y región para el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="b342d-123">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="b342d-124">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b342d-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b342d-125">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b342d-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b342d-126">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="b342d-126">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="b342d-127">Haga doble clic en la configuración **Global** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="b342d-127">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="b342d-128">En la página **Editar configuración global**, seleccione la casilla **Habilitar desvío de medios**.</span><span class="sxs-lookup"><span data-stu-id="b342d-128">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="b342d-129">Haga clic en **Usar la configuración de sitios y regiones**.</span><span class="sxs-lookup"><span data-stu-id="b342d-129">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="b342d-130">Si es necesario, seleccione la casilla **Habilitar desvío para sitios sin asignar**.</span><span class="sxs-lookup"><span data-stu-id="b342d-130">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b342d-p107">Seleccione esta casilla solamente si dispone de uno o más sitios grandes asociados a la misma región que no tenga restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunas sucursales asociadas con la misma región que no tienen restricciones de ancho de banda. Cuando habilita el desvío para sitios sin asignar, la configuración se simplifica ya que solo especifica subredes asociadas con las sucursales, en lugar de tener que especificar todas las subredes asociadas a todos los sitios. Se recomienda no activar esta casilla si se ha habilitado el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b342d-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="b342d-134">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b342d-134">Click **Commit**.</span></span>

<span data-ttu-id="b342d-135">A continuación, agregue subredes al sitio de red, como se describe en [asociar subredes con sitios de red para el desvío de medios en Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="b342d-135">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="b342d-136">(Los procedimientos reales para la Asociación de subredes con sitios de red se describen en [asociar una subred con un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)). Una vez que haya asociado todas las subredes a los sitios de red, se completará la implementación de la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="b342d-136">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b342d-137">Si todavía no ha creado regiones de red y sitios de red, deberá crearlos en primer lugar para poder continuar con la implementación del desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="b342d-137">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="b342d-138">Para obtener más información, consulte <A href="lync-server-2013-create-or-modify-a-network-region.md">crear o modificar una región de red en Lync server 2013</A> y <A href="lync-server-2013-create-or-modify-a-network-site.md">crear o modificar un sitio de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b342d-138">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b342d-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b342d-139">See Also</span></span>


[<span data-ttu-id="b342d-140">Asociar subredes con sitios de red para el desvío de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b342d-140">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

