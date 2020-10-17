---
title: 'Lync Server 2013: habilitar el desvío de medios de red'
description: 'Lync Server 2013: habilitar el desvío de medios de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1218376903aa42e1ea55205e3a9e8d16aade9a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546556"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="e9738-103">Habilitación del desvío de medios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9738-103">Enabling network media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9738-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e9738-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e9738-105">La configuración del desvío de medios se aplica globalmente en una implementación de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9738-105">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="e9738-106">Con el desvío de medios, las llamadas pueden omitir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="e9738-106">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="e9738-107">Para obtener información detallada sobre Cuándo usar la omisión de medios, consulte [planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la sección planeación.</span><span class="sxs-lookup"><span data-stu-id="e9738-107">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="e9738-108">Puede habilitar y configurar la omisión de medios desde el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9738-108">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="e9738-109">Para habilitar y configurar el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="e9738-109">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="e9738-110">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e9738-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e9738-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9738-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e9738-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e9738-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e9738-113">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Global**.</span><span class="sxs-lookup"><span data-stu-id="e9738-113">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="e9738-p103">En la página **Global**, haga clic en la configuración **Global**. En todos los casos hay solo una configuración y siempre se llama Global.</span><span class="sxs-lookup"><span data-stu-id="e9738-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="e9738-116">En el menú **Editar**, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="e9738-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="e9738-117">En la página **Editar configuración global**, haga clic en la casilla **Habilitar desvío de medios**.</span><span class="sxs-lookup"><span data-stu-id="e9738-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="e9738-118">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e9738-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="e9738-119">**Omitir siempre**     Seleccione esta opción para intentar la omisión de medios en todas las llamadas.</span><span class="sxs-lookup"><span data-stu-id="e9738-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="e9738-120">Esta opción no estará disponible si se ha habilitado el control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="e9738-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="e9738-121">Si el CAC no está habilitado, seleccione esta opción en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9738-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="e9738-122">No es necesario controlar el ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="e9738-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="e9738-123">No se necesita una configuración específica para saber cuándo debe producirse el desvío.</span><span class="sxs-lookup"><span data-stu-id="e9738-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="e9738-124">Existe plena conectividad entre las puertas de enlace y los clientes.</span><span class="sxs-lookup"><span data-stu-id="e9738-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="e9738-125">**Usar configuración**     de sitios y regiones Si el CAC está habilitado, esta opción está seleccionada de forma predeterminada y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="e9738-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="e9738-126">Cuando se selecciona esta opción, los sitios y regiones de configuración de red se usarán para determinar cuando resulta posible el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="e9738-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="e9738-127">Si selecciona esta opción, puede optar por habilitar el desvío para sitios que no se han asignado.</span><span class="sxs-lookup"><span data-stu-id="e9738-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="e9738-128">Haga clic en la casilla **Habilitar desvío para sitios sin asignar** solamente si dispone de uno o más sitios grandes asociados con la misma región que no tenga restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunos sitios de sucursal asociados con la misma región que no tienen restricciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="e9738-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="e9738-129">Cuando habilita el desvío para sitios sin asignar, la configuración se simplifica porque solo especifica subredes asociadas con los sitios de sucursal en lugar de tener que especificar todas las subredes asociadas a todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="e9738-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="e9738-130">Se recomienda no seleccionar la casilla **Habilitar desvío para sitios sin asignar** si se ha habilitado el CAC.</span><span class="sxs-lookup"><span data-stu-id="e9738-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="e9738-131">Haga clic en **Confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="e9738-131">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e9738-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9738-132">See Also</span></span>


[<span data-ttu-id="e9738-133">Deshabilitar el desvío de medios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9738-133">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="e9738-134">Opciones de omisión de medios globales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9738-134">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="e9738-135">Planeación de la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9738-135">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

