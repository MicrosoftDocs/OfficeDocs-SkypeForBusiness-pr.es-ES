---
title: Comprobación del entorno heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implementar Skype para Business Server 2019 en un estado de coexistencia, debe comprobar que se han configurado e iniciado servicios heredados. Es importante identificar servicios clave y características que existen en el entorno heredado, antes de implementar un Skype para el grupo piloto Business Server 2019. Antes de implementar Microsoft Skype para Business Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredado, debe comprobar los servicios XMPP heredados se han configurado y se ha iniciado e identificar qué es la configuración de XMPP heredada de socio federado compatibilidad con.
ms.openlocfilehash: 0f9812efe966d72eba1eeead9d74780f2ba16661
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235117"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="0b026-105">Comprobación del entorno heredado</span><span class="sxs-lookup"><span data-stu-id="0b026-105">Verify the legacy environment</span></span>

<span data-ttu-id="0b026-106">Antes de implementar Skype para Business Server 2019 en un estado de coexistencia, debe comprobar que se han configurado e iniciado servicios heredados.</span><span class="sxs-lookup"><span data-stu-id="0b026-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="0b026-107">Es importante identificar servicios clave y características que existen en el entorno heredado antes de implementar un Skype para el grupo piloto Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0b026-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="0b026-108">Antes de implementar Microsoft Skype para Business Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredado, debe comprobar que se han configurado e iniciado los servicios XMPP heredados e identificar el socio XMPP heredado federado es compatible con la configuración.</span><span class="sxs-lookup"><span data-stu-id="0b026-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="0b026-109">Comprobar la implementación heredada implica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b026-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="0b026-110">Comprobar que se han iniciado los servicios heredados</span><span class="sxs-lookup"><span data-stu-id="0b026-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="0b026-111">Revisar la topología y los usuarios</span><span class="sxs-lookup"><span data-stu-id="0b026-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="0b026-112">Comprobar la federación y la configuración del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="0b026-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="0b026-113">Comprobar los servicios de XMPP y los socios federados</span><span class="sxs-lookup"><span data-stu-id="0b026-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="0b026-114">Compruebe que se han iniciado los servicios heredados</span><span class="sxs-lookup"><span data-stu-id="0b026-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="0b026-115">En el servidor front-heredado de End, navegue hasta el applet herramientas Administrativas\servicios.</span><span class="sxs-lookup"><span data-stu-id="0b026-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="0b026-116">Compruebe que los siguientes servicios se están ejecutando en el servidor Front-End:</span><span class="sxs-lookup"><span data-stu-id="0b026-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Lista de servicios que se ejecutan en el servidor Front-End](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="0b026-118">Revise la topología heredada en Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="0b026-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0b026-119">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0b026-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="0b026-120">Abra el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0b026-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0b026-121">Seleccione la **topología**.</span><span class="sxs-lookup"><span data-stu-id="0b026-121">Select **Topology**.</span></span> <span data-ttu-id="0b026-122">Compruebe que se enumeran los diversos servidores en su implementación heredada.</span><span class="sxs-lookup"><span data-stu-id="0b026-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Página de topología del Panel de control](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="0b026-124">Revise los usuarios heredados en Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="0b026-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0b026-125">Abra el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0b026-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="0b026-126">Seleccione **los usuarios**y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="0b026-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="0b026-127">Compruebe que la columna **Grupo de registradores** apunta al grupo de servidores heredado para cada usuario de la lista.</span><span class="sxs-lookup"><span data-stu-id="0b026-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Panel de control de lista de usuarios](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="0b026-129">Comprobar la configuración heredada de borde y federación</span><span class="sxs-lookup"><span data-stu-id="0b026-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="0b026-130">Iniciar el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="0b026-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="0b026-131">Seleccione **Descargar topología de la implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="0b026-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="0b026-132">Elija un nombre de archivo y guarde la topología con el tipo de archivo .tbxml predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0b026-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="0b026-133">Expanda el nodo de instalaciones heredadas para revelar los diversos roles de servidor de la implementación.</span><span class="sxs-lookup"><span data-stu-id="0b026-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="0b026-134">Seleccione el nodo del sitio y compruebe que se establece un valor de **asignación de ruta de federación de sitio** .</span><span class="sxs-lookup"><span data-stu-id="0b026-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Generador de topologías, ruta de federación del sitio](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="0b026-136">Seleccione el grupo de servidores de front-end de un servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="0b026-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="0b026-137">Determinar si se ha configurado un grupo de servidores perimetrales para los medios por debajo de **las asociaciones**.</span><span class="sxs-lookup"><span data-stu-id="0b026-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Generador de topología que muestra los servidores y grupos de servidores](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="0b026-139">Seleccione el grupo de servidores perimetrales e identifique si un grupo del próximo salto se ha configurado bajo **selección de próximo salto**.</span><span class="sxs-lookup"><span data-stu-id="0b026-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Generador de topologías, selección de próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="0b026-141">Compruebe el socio federado de XMPP heredado configuración</span><span class="sxs-lookup"><span data-stu-id="0b026-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="0b026-142">Desde el servidor XMPP heredado, navegue hasta el applet herramientas Administrativas\servicios.</span><span class="sxs-lookup"><span data-stu-id="0b026-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="0b026-143">Compruebe que se ha iniciado el servicio de puerta de enlace de XMPP de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="0b026-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Servicio de puerta de enlace XMPP de Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

