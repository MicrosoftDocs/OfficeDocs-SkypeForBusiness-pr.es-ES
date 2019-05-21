---
title: Habilitar y deshabilitar la omisión de medios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Use los procedimientos de este artículo para habilitar o deshabilitar la omisión de medios con el panel de control de Skype empresarial Server.
ms.openlocfilehash: acfa963e71f3c3b89d0e79648d00871b1ab44616
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279588"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="fec61-103">Habilitar y deshabilitar la omisión de medios en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="fec61-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="fec61-104">Use los procedimientos de este artículo para habilitar o deshabilitar la omisión de medios con el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fec61-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="fec61-105">Habilitar omisión de medios de red</span><span class="sxs-lookup"><span data-stu-id="fec61-105">Enable network media bypass</span></span> 

<span data-ttu-id="fec61-106">La configuración de omisión de medios se aplica globalmente en una implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fec61-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="fec61-107">La omisión de medios permite que las llamadas omitan el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="fec61-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="fec61-108">Para obtener información sobre Cuándo usar la omisión de elementos multimedia, consulte [planear la omisión de medios](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="fec61-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="fec61-109">Puede habilitar y configurar la omisión de medios desde el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fec61-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="fec61-110">Para habilitar y configurar la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="fec61-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="fec61-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="fec61-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fec61-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fec61-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fec61-113">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **global**.</span><span class="sxs-lookup"><span data-stu-id="fec61-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="fec61-114">En la página **global** , haga clic en la configuración **global** .</span><span class="sxs-lookup"><span data-stu-id="fec61-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="fec61-115">Siempre hay una sola configuración y siempre se denomina global.</span><span class="sxs-lookup"><span data-stu-id="fec61-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="fec61-116">En el menú **Editar** , haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="fec61-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="fec61-117">En la página **Editar configuración global** , haga clic en la casilla de verificación **Habilitar omisión de medios** .</span><span class="sxs-lookup"><span data-stu-id="fec61-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="fec61-118">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fec61-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="fec61-119">**Omitir siempre seleccione**   esta opción para intentar la omisión de medios en todas las llamadas.</span><span class="sxs-lookup"><span data-stu-id="fec61-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="fec61-120">Esta opción no estará disponible si el control de admisión de llamada (CAC) está habilitado.</span><span class="sxs-lookup"><span data-stu-id="fec61-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="fec61-121">Si CAC no está habilitado, seleccione esta opción en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="fec61-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="fec61-122">No es necesario el control del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="fec61-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="fec61-123">No es necesario que la configuración específica determine Cuándo debe pasar el bypass.</span><span class="sxs-lookup"><span data-stu-id="fec61-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="fec61-124">Hay conectividad completa entre las puertas de enlace y los clientes.</span><span class="sxs-lookup"><span data-stu-id="fec61-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="fec61-125">**Usar la configuración**   de sitios y regiones si CAC está habilitado, esta opción está seleccionada de forma predeterminada y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="fec61-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="fec61-126">Cuando esta opción está seleccionada, se usarán regiones y sitios de configuración de red para determinar cuándo es posible la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="fec61-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="fec61-127">Si selecciona esta opción, puede habilitar el omisión de sitios que no están asignados.</span><span class="sxs-lookup"><span data-stu-id="fec61-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="fec61-128">Haga clic en la casilla **de verificación Habilitar el omisión de sitios no asignados** solo si tiene uno o varios sitios grandes asociados a la misma región que no tienen restricciones de ancho de banda (por ejemplo, un sitio central grande) y también tiene algunos sitios de rama asociados con el la misma región que tiene restricciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="fec61-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="fec61-129">Cuando habilita el bypass para sitios no asignados, la configuración se simplifica porque especifica solo las subredes asociadas a las sucursales en lugar de tener que especificar todas las subredes asociadas a todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="fec61-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="fec61-130">Le recomendamos que no active la casilla **Habilitar omisión para sitios no asignados** si CAC está habilitado.</span><span class="sxs-lookup"><span data-stu-id="fec61-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="fec61-131">Haga clic en **confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="fec61-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="fec61-132">Deshabilitar omisión de medios de red</span><span class="sxs-lookup"><span data-stu-id="fec61-132">Disable network media bypass</span></span>

<span data-ttu-id="fec61-133">La configuración de omisión de medios se aplica globalmente en una implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fec61-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="fec61-134">La omisión de medios permite que las llamadas omitan el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="fec61-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="fec61-135">Para obtener información sobre Cuándo usar la omisión de elementos multimedia, consulte [planear la omisión de medios](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="fec61-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="fec61-136">Puede deshabilitar la omisión de medios desde el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fec61-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="fec61-137">Para deshabilitar la omisión de medios</span><span class="sxs-lookup"><span data-stu-id="fec61-137">To disable media bypass</span></span>

1.  <span data-ttu-id="fec61-138">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="fec61-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fec61-139">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fec61-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fec61-140">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **global**.</span><span class="sxs-lookup"><span data-stu-id="fec61-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="fec61-141">En la página **global** , haga clic en la configuración **global** .</span><span class="sxs-lookup"><span data-stu-id="fec61-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="fec61-142">Siempre hay una sola configuración y siempre se denomina global.</span><span class="sxs-lookup"><span data-stu-id="fec61-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="fec61-143">En el menú **Editar** , haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="fec61-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="fec61-144">En la página **Editar configuración global** , desactive la casilla **Habilitar omisión de medios** .</span><span class="sxs-lookup"><span data-stu-id="fec61-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="fec61-145">Haga clic en **confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="fec61-145">Click **Commit** to save your changes.</span></span>

  
