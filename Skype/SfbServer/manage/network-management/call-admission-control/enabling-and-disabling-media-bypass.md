---
title: Habilitar y deshabilitar la omisión de medios
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Use los procedimientos de este artículo para habilitar o deshabilitar la omisión de medios mediante el Panel de control de Skype Empresarial Server.
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816500"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="106f8-103">Habilitar y deshabilitar la omisión de medios en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="106f8-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="106f8-104">Use los procedimientos de este artículo para habilitar o deshabilitar la omisión de medios mediante el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="106f8-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="106f8-105">Habilitar la omisión de medios de red</span><span class="sxs-lookup"><span data-stu-id="106f8-105">Enable network media bypass</span></span> 

<span data-ttu-id="106f8-106">La configuración de omisión de medios se aplica globalmente en una implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="106f8-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="106f8-107">Con el desvío de medios, las llamadas pueden omitir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="106f8-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="106f8-108">Para obtener más información acerca de cuándo usar la omisión de medios, vea [Planear la omisión de medios.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="106f8-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="106f8-109">Puede habilitar y configurar la omisión de medios desde el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="106f8-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="106f8-110">Para habilitar y configurar el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="106f8-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="106f8-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="106f8-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="106f8-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="106f8-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="106f8-113">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Global**.</span><span class="sxs-lookup"><span data-stu-id="106f8-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="106f8-p102">En la página **Global**, haga clic en la configuración **Global**. En todos los casos hay solo una configuración y siempre se llama Global.</span><span class="sxs-lookup"><span data-stu-id="106f8-p102">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="106f8-116">En el menú **Editar**, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="106f8-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="106f8-117">En la página **Editar configuración global**, haga clic en la casilla **Habilitar desvío de medios**.</span><span class="sxs-lookup"><span data-stu-id="106f8-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="106f8-118">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="106f8-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="106f8-119">**Omitir siempre**   Seleccione esta opción para intentar la omisión de medios en todas las llamadas.</span><span class="sxs-lookup"><span data-stu-id="106f8-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="106f8-120">Esta opción no estará disponible si se ha habilitado el control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="106f8-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="106f8-121">Si el CAC no está habilitado, seleccione esta opción en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="106f8-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="106f8-122">No es necesario controlar el ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="106f8-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="106f8-123">No se necesita una configuración específica para saber cuándo debe producirse el desvío.</span><span class="sxs-lookup"><span data-stu-id="106f8-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="106f8-124">Existe plena conectividad entre las puertas de enlace y los clientes.</span><span class="sxs-lookup"><span data-stu-id="106f8-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="106f8-125">**Usar la configuración de sitios y regiones**   Si el CAC está habilitado, esta opción está seleccionada de forma predeterminada y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="106f8-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="106f8-126">Cuando se selecciona esta opción, los sitios y regiones de configuración de red se usarán para determinar cuando resulta posible el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="106f8-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="106f8-127">Si selecciona esta opción, puede optar por habilitar el desvío para sitios que no se han asignado.</span><span class="sxs-lookup"><span data-stu-id="106f8-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="106f8-128">Haga clic en la casilla **Habilitar desvío para sitios sin asignar** solamente si dispone de uno o más sitios grandes asociados con la misma región que no tenga restricciones de ancho de banda (por ejemplo, un sitio central grande) y si dispone también de algunos sitios de sucursal asociados con la misma región que no tienen restricciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="106f8-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="106f8-129">Cuando habilita el desvío para sitios sin asignar, la configuración se simplifica porque solo especifica subredes asociadas con los sitios de sucursal en lugar de tener que especificar todas las subredes asociadas a todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="106f8-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="106f8-130">Se recomienda no seleccionar la casilla **Habilitar desvío para sitios sin asignar** si se ha habilitado el CAC.</span><span class="sxs-lookup"><span data-stu-id="106f8-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="106f8-131">Haga clic en **Confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="106f8-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="106f8-132">Deshabilitar la omisión de medios de red</span><span class="sxs-lookup"><span data-stu-id="106f8-132">Disable network media bypass</span></span>

<span data-ttu-id="106f8-133">La configuración de omisión de medios se aplica globalmente en una implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="106f8-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="106f8-134">Con el desvío de medios, las llamadas pueden omitir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="106f8-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="106f8-135">Para obtener más información acerca de cuándo usar la omisión de medios, vea [Planear la omisión de medios.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="106f8-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="106f8-136">Puede deshabilitar la omisión de medios desde el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="106f8-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="106f8-137">Para deshabilitar el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="106f8-137">To disable media bypass</span></span>

1.  <span data-ttu-id="106f8-138">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="106f8-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="106f8-139">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="106f8-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="106f8-140">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Global**.</span><span class="sxs-lookup"><span data-stu-id="106f8-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="106f8-p106">En la página **Global**, haga clic en la configuración **Global**. En todos los casos hay solo una configuración y siempre se llama Global.</span><span class="sxs-lookup"><span data-stu-id="106f8-p106">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="106f8-143">En el menú **Editar**, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="106f8-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="106f8-144">En la página  **Editar configuración global**, desactive la casilla  **Habilitar desvío de medios**.</span><span class="sxs-lookup"><span data-stu-id="106f8-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="106f8-145">Haga clic en  **Confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="106f8-145">Click **Commit** to save your changes.</span></span>

  
