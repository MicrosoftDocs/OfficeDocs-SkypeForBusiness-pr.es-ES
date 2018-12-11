---
title: Habilitar y deshabilitar el desvío de medios
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Use los procedimientos de este artículo para habilitar o deshabilitar el desvío de medios mediante el uso de la Skype para el Panel de Control de servidor empresarial.
ms.openlocfilehash: f595ab5380575f34c0a470cb58c82459841ee4d7
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222761"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="4e6ae-103">Habilitación y deshabilitación de medios de omisión de Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="4e6ae-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="4e6ae-104">Use los procedimientos de este artículo para habilitar o deshabilitar el desvío de medios mediante el uso de la Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="4e6ae-105">Habilitar desvío de medios de red</span><span class="sxs-lookup"><span data-stu-id="4e6ae-105">Enable network media bypass</span></span> 

<span data-ttu-id="4e6ae-106">Configuración de desvío de medios se aplica globalmente a través de un Skype para la implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="4e6ae-107">Desvío de medios permite que las llamadas a omitir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="4e6ae-108">Para obtener más información acerca de cuándo se deben usar desvío de medios, vea [Plan para los medios de desvío](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="4e6ae-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="4e6ae-109">Puede habilitar y configurar el desvío de medios desde el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="4e6ae-110">Para habilitar y configurar el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="4e6ae-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="4e6ae-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4e6ae-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4e6ae-113">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Global**.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="4e6ae-114">En la página **Global** , haga clic en la configuración **Global** .</span><span class="sxs-lookup"><span data-stu-id="4e6ae-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="4e6ae-115">Siempre hay sólo una configuración, y siempre se denomina Global.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="4e6ae-116">En el menú **Edición** , haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="4e6ae-117">En la página **Editar configuración Global** , haga clic en la casilla de verificación **Habilitar el desvío de medios** .</span><span class="sxs-lookup"><span data-stu-id="4e6ae-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="4e6ae-118">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4e6ae-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="4e6ae-119">**Omitir siempre**   Seleccione esta opción para intentar medios desvío en todas las llamadas.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="4e6ae-120">Esta opción no estará disponible si está habilitado el control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="4e6ae-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="4e6ae-121">Si no está habilitado el CAC, seleccione esta opción en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="4e6ae-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="4e6ae-122">No es necesario para el control del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="4e6ae-123">No es necesario para una configuración específica para determinar cuándo debe producirse el desvío.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="4e6ae-124">Existe plena conectividad entre las puertas de enlace y los clientes.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="4e6ae-125">**Usar los sitios y configuración de la región**   CAC si está habilitado, esta opción está seleccionada de manera predeterminada y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="4e6ae-126">Cuando se selecciona esta opción, se usará para determinar cuándo es posible desvío de medios regiones y sitios de la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="4e6ae-127">Si selecciona esta opción, puede elegir habilitar el desvío para sitios que no están asignados.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="4e6ae-128">Haga clic en la casilla de verificación **Habilitar el desvío para sitios sin asignar** sólo si tiene uno o más grandes sitios asociados con la misma región que no tienen restricciones de ancho de banda (por ejemplo, un sitio central grande) y también tiene algunos sitios de sucursal asociadas con la misma región que tienen restricciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="4e6ae-129">Cuando se habilita el desvío para sitios sin asignar, configuración se simplifica porque especificar sólo las subredes asociadas con los sitios de sucursal, en lugar de tener que especificar todas las subredes asociadas con todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="4e6ae-130">Se recomienda que no active la casilla de verificación **Habilitar el desvío para sitios sin asignar** si está habilitado el CAC.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="4e6ae-131">Haga clic en **Confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="4e6ae-132">Deshabilitar el desvío de medios de red</span><span class="sxs-lookup"><span data-stu-id="4e6ae-132">Disable network media bypass</span></span>

<span data-ttu-id="4e6ae-133">Configuración de desvío de medios se aplica globalmente a través de un Skype para la implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="4e6ae-134">Desvío de medios permite que las llamadas a omitir el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="4e6ae-135">Para obtener más información acerca de cuándo se deben usar desvío de medios, vea [Plan para los medios de desvío](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="4e6ae-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="4e6ae-136">Puede deshabilitar el desvío de medios desde el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="4e6ae-137">Para deshabilitar el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="4e6ae-137">To disable media bypass</span></span>

1.  <span data-ttu-id="4e6ae-138">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4e6ae-139">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4e6ae-140">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Global**.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="4e6ae-141">En la página **Global** , haga clic en la configuración **Global** .</span><span class="sxs-lookup"><span data-stu-id="4e6ae-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="4e6ae-142">Siempre hay sólo una configuración, y siempre se denomina Global.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="4e6ae-143">En el menú **Edición** , haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="4e6ae-144">En la página **Editar configuración Global** , desactive la casilla de verificación **Habilitar el desvío de medios** .</span><span class="sxs-lookup"><span data-stu-id="4e6ae-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="4e6ae-145">Haga clic en **Confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="4e6ae-145">Click **Commit** to save your changes.</span></span>

  