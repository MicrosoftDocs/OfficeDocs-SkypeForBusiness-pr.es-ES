---
title: Comprobar el entorno heredado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Antes de implementar Skype empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado. Es importante identificar los servicios y características clave que existen en el entorno heredado antes de implementar un grupo piloto de Skype empresarial Server 2019. Antes de implementar Microsoft Skype empresarial Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se hayan configurado e iniciado y que identifiquen qué socio federado admite la configuración de XMPP heredado.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751682"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="c0cde-105">Comprobar el entorno heredado</span><span class="sxs-lookup"><span data-stu-id="c0cde-105">Verify the legacy environment</span></span>

<span data-ttu-id="c0cde-106">Antes de implementar Skype empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado.</span><span class="sxs-lookup"><span data-stu-id="c0cde-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="c0cde-107">Es importante identificar los servicios y características clave que existen en el entorno heredado antes de implementar un grupo piloto de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c0cde-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="c0cde-108">Antes de implementar Microsoft Skype empresarial Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se han configurado e iniciado, e identificar qué socio federado es compatible con la configuración de XMPP heredado.</span><span class="sxs-lookup"><span data-stu-id="c0cde-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="c0cde-109">La comprobación de la implementación heredada supone lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0cde-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="c0cde-110">Comprobar que se han iniciado los servicios heredados</span><span class="sxs-lookup"><span data-stu-id="c0cde-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="c0cde-111">Revisión de la topología y los usuarios</span><span class="sxs-lookup"><span data-stu-id="c0cde-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="c0cde-112">Comprobación de la configuración de la Federación y el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="c0cde-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="c0cde-113">Comprobación de los servicios XMPP y socios federados</span><span class="sxs-lookup"><span data-stu-id="c0cde-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="c0cde-114">Comprobar que se han iniciado los servicios heredados</span><span class="sxs-lookup"><span data-stu-id="c0cde-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="c0cde-115">Desde el servidor front-end heredado, navegue hasta el applet herramientas administrativo.</span><span class="sxs-lookup"><span data-stu-id="c0cde-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="c0cde-116">Compruebe que los servicios siguientes se están ejecutando en el servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="c0cde-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Lista de servicios que se ejecutan en el servidor front-end](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c0cde-118">Revisión de la topología heredada en el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c0cde-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c0cde-119">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins, o del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c0cde-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="c0cde-120">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c0cde-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c0cde-121">Seleccione **Topología**.</span><span class="sxs-lookup"><span data-stu-id="c0cde-121">Select **Topology**.</span></span> <span data-ttu-id="c0cde-122">Compruebe que se muestran los diversos servidores de la implementación heredada.</span><span class="sxs-lookup"><span data-stu-id="c0cde-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Página de topología del panel de control](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c0cde-124">Revisar usuarios heredados en el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c0cde-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c0cde-125">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c0cde-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="c0cde-126">Seleccione **usuarios**y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="c0cde-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="c0cde-127">Compruebe que la columna **grupo de registrador** apunta al grupo heredado para cada usuario enumerado.</span><span class="sxs-lookup"><span data-stu-id="c0cde-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Panel de control, enumerar usuarios](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="c0cde-129">Comprobar la configuración de la Federación y el servidor perimetral heredados</span><span class="sxs-lookup"><span data-stu-id="c0cde-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="c0cde-130">Inicie el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="c0cde-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="c0cde-131">Seleccione **Descargar una topología desde una implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="c0cde-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="c0cde-132">Elija un nombre de archivo y guarde la topología con el tipo de archivo default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="c0cde-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="c0cde-133">Expanda el nodo instalaciones heredadas para mostrar los distintos roles de servidor en la implementación.</span><span class="sxs-lookup"><span data-stu-id="c0cde-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="c0cde-134">Seleccione el nodo de sitio y compruebe que se haya establecido un valor de **asignación de ruta de Federación de sitio** .</span><span class="sxs-lookup"><span data-stu-id="c0cde-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Generador de topologías, ruta de Federación del sitio](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="c0cde-136">Seleccione el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="c0cde-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="c0cde-137">Determinar si un grupo de servidores perimetrales se ha configurado para los medios por debajo de las **asociaciones**.</span><span class="sxs-lookup"><span data-stu-id="c0cde-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Generador de topologías que muestra servidores y grupos de servidores](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="c0cde-139">Seleccione el grupo de servidores perimetrales e identifique si un grupo de servidores de próximo salto se configura por debajo de la selección de próximo **salto**.</span><span class="sxs-lookup"><span data-stu-id="c0cde-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Generador de topologías, selección de próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="c0cde-141">Comprobar la configuración del socio federado de XMPP heredado</span><span class="sxs-lookup"><span data-stu-id="c0cde-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="c0cde-142">Desde el servidor XMPP heredado, desplácese al appletAdministrative Tools\Services.</span><span class="sxs-lookup"><span data-stu-id="c0cde-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="c0cde-143">Compruebe que se haya iniciado el servicio de puerta de enlace XMPP de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="c0cde-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Servicio de puerta de enlace XMPP de Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

