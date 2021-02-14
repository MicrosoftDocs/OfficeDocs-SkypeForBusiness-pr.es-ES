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
description: Antes de implementar Skype Empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado. Es importante identificar los servicios y características clave que existen en su entorno heredado, antes de implementar un grupo piloto de Skype Empresarial Server 2019. Antes de implementar XMPP de Microsoft Skype Empresarial Server 2019 en un estado de coexistencia con una implementación XMPP heredada, debe comprobar que los servicios XMPP heredados se han configurado e iniciado, e identificar qué socio federado admite la configuración XMPP heredada.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751682"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="842e7-105">Comprobar el entorno heredado</span><span class="sxs-lookup"><span data-stu-id="842e7-105">Verify the legacy environment</span></span>

<span data-ttu-id="842e7-106">Antes de implementar Skype Empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado.</span><span class="sxs-lookup"><span data-stu-id="842e7-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="842e7-107">Es importante identificar los servicios y características clave que existen en su entorno heredado antes de implementar un grupo piloto de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="842e7-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="842e7-108">Antes de implementar XMPP de Microsoft Skype Empresarial Server 2019 en un estado de coexistencia con una implementación XMPP heredada, debe comprobar que los servicios XMPP heredados se han configurado e iniciado, e identificar qué socio federado admite la configuración XMPP heredada.</span><span class="sxs-lookup"><span data-stu-id="842e7-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="842e7-109">La comprobación de la implementación heredada implica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="842e7-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="842e7-110">Comprobación de que se han iniciado los servicios heredados</span><span class="sxs-lookup"><span data-stu-id="842e7-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="842e7-111">Revisión de la topología y los usuarios</span><span class="sxs-lookup"><span data-stu-id="842e7-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="842e7-112">Comprobación de la configuración de federación y servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="842e7-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="842e7-113">Comprobación de servicios XMPP y socios federados</span><span class="sxs-lookup"><span data-stu-id="842e7-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="842e7-114">Comprobar que se han iniciado los servicios heredados</span><span class="sxs-lookup"><span data-stu-id="842e7-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="842e7-115">Desde el servidor front-end heredado, vaya al applet Herramientas administrativas\Servicios.</span><span class="sxs-lookup"><span data-stu-id="842e7-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="842e7-116">Compruebe que los servicios siguientes se están ejecutando en el servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="842e7-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Lista de servicios que se ejecutan en el servidor front-end](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="842e7-118">Revisar la topología heredada en el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="842e7-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="842e7-119">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins, o del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="842e7-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="842e7-120">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="842e7-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="842e7-121">Seleccione **Topología**.</span><span class="sxs-lookup"><span data-stu-id="842e7-121">Select **Topology**.</span></span> <span data-ttu-id="842e7-122">Compruebe que se muestran los distintos servidores de la implementación heredada.</span><span class="sxs-lookup"><span data-stu-id="842e7-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Página de topología del Panel de control](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="842e7-124">Revisar los usuarios heredados en el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="842e7-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="842e7-125">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="842e7-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="842e7-126">Seleccione **Usuarios y,** a continuación, haga clic **en Buscar**.</span><span class="sxs-lookup"><span data-stu-id="842e7-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="842e7-127">Compruebe que la columna **Grupo de registradores** apunta al grupo heredado para cada usuario enumerado.</span><span class="sxs-lookup"><span data-stu-id="842e7-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Lista de usuarios del Panel de control](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="842e7-129">Comprobar la configuración de federación y perimetral heredada</span><span class="sxs-lookup"><span data-stu-id="842e7-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="842e7-130">Inicie el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="842e7-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="842e7-131">Seleccione **Descargar una topología desde una implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="842e7-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="842e7-132">Elija un nombre de archivo y guarde la topología con el tipo de archivo .tbxml predeterminado.</span><span class="sxs-lookup"><span data-stu-id="842e7-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="842e7-133">Expanda el nodo de instalación heredado para mostrar los distintos roles de servidor de la implementación.</span><span class="sxs-lookup"><span data-stu-id="842e7-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="842e7-134">Seleccione el nodo de sitio y compruebe que se ha establecido un valor de asignación de ruta **de federación** de sitio.</span><span class="sxs-lookup"><span data-stu-id="842e7-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Generador de topologías, ruta de federación de sitios](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="842e7-136">Seleccione el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="842e7-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="842e7-137">Determinar si se ha configurado un grupo de servidores perimetrales para los medios debajo de **Asociaciones.**</span><span class="sxs-lookup"><span data-stu-id="842e7-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Generador de topologías que muestra servidores y grupos de servidores](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="842e7-139">Seleccione el grupo de servidores perimetrales e identifique si un grupo de servidores del próximo salto está configurado debajo **de la selección del próximo salto.**</span><span class="sxs-lookup"><span data-stu-id="842e7-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Generador de topologías, selección del próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="842e7-141">Comprobar la configuración de socios federados XMPP heredados</span><span class="sxs-lookup"><span data-stu-id="842e7-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="842e7-142">Desde el servidor XMPP heredado, desplácese al appletAdministrative Tools\Services.</span><span class="sxs-lookup"><span data-stu-id="842e7-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="842e7-143">Compruebe que se haya iniciado el servicio de puerta de enlace XMPP de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="842e7-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Servicio de puerta de enlace XMPP de Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

