---
title: Comprobar el entorno heredado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implementar Skype empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado. Es importante identificar los servicios clave y las características que existen en su entorno heredado antes de implementar un grupo de pruebas piloto de Skype empresarial Server 2019. Antes de implementar Microsoft Skype empresarial Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se han configurado e iniciado, e identificar a qué socio federado se encuentra la configuración de XMPP heredada. dando.
ms.openlocfilehash: 4c648dbbadeca50c12eb6047958ef63066ed7a3a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243778"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="27e3f-105">Comprobar el entorno heredado</span><span class="sxs-lookup"><span data-stu-id="27e3f-105">Verify the legacy environment</span></span>

<span data-ttu-id="27e3f-106">Antes de implementar Skype empresarial Server 2019 en un estado de coexistencia, debe comprobar que los servicios heredados se han configurado e iniciado.</span><span class="sxs-lookup"><span data-stu-id="27e3f-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="27e3f-107">Es importante identificar los servicios clave y las características que existen en el entorno heredado antes de implementar un grupo de pruebas piloto de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="27e3f-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="27e3f-108">Antes de implementar Microsoft Skype empresarial Server 2019 XMPP en un estado de coexistencia con una implementación de XMPP heredada, debe comprobar que los servicios de XMPP heredado se han configurado e iniciado, e identificar a qué socio federado el XMPP heredado. es compatible con la configuración.</span><span class="sxs-lookup"><span data-stu-id="27e3f-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="27e3f-109">La comprobación de la implementación heredada conlleva lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27e3f-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="27e3f-110">Comprobar que los servicios heredados se han iniciado</span><span class="sxs-lookup"><span data-stu-id="27e3f-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="27e3f-111">Revisar la topología y los usuarios</span><span class="sxs-lookup"><span data-stu-id="27e3f-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="27e3f-112">Comprobar la configuración del servidor perimetral y la Federación</span><span class="sxs-lookup"><span data-stu-id="27e3f-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="27e3f-113">Verificación de los servicios XMPP y los socios federados</span><span class="sxs-lookup"><span data-stu-id="27e3f-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="27e3f-114">Comprobar que los servicios heredados se han iniciado</span><span class="sxs-lookup"><span data-stu-id="27e3f-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="27e3f-115">Desde el servidor front-end heredado, navegue hasta el applet Tools\Services administrativo.</span><span class="sxs-lookup"><span data-stu-id="27e3f-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="27e3f-116">Compruebe que se están ejecutando los siguientes servicios en el servidor front-end:</span><span class="sxs-lookup"><span data-stu-id="27e3f-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Lista de servicios que se ejecutan en el servidor front-end](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="27e3f-118">Revisar la topología heredada en el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="27e3f-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="27e3f-119">Inicie sesión en el servidor front-end con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o miembro del rol administrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="27e3f-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="27e3f-120">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="27e3f-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="27e3f-121">Seleccione **topología**.</span><span class="sxs-lookup"><span data-stu-id="27e3f-121">Select **Topology**.</span></span> <span data-ttu-id="27e3f-122">Compruebe que se muestran los diversos servidores de su implementación heredada.</span><span class="sxs-lookup"><span data-stu-id="27e3f-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Página de topología del panel de control](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="27e3f-124">Revisar los usuarios heredados en el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="27e3f-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="27e3f-125">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="27e3f-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="27e3f-126">Seleccione **usuarios**y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="27e3f-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="27e3f-127">Compruebe que la columna **registrar grupo** apunta a la agrupación heredada para cada usuario de la lista.</span><span class="sxs-lookup"><span data-stu-id="27e3f-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Panel de control con una lista de usuarios](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="27e3f-129">Comprobar la configuración de la Federación y los límites heredados</span><span class="sxs-lookup"><span data-stu-id="27e3f-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="27e3f-130">Iniciar el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="27e3f-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="27e3f-131">Seleccione **Descargar topología de la implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="27e3f-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="27e3f-132">Elija un nombre de archivo y guarde la topología con el tipo de archivo default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="27e3f-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="27e3f-133">Expanda el nodo instalaciones heredadas para mostrar los distintos roles de servidor en la implementación.</span><span class="sxs-lookup"><span data-stu-id="27e3f-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="27e3f-134">Seleccione el nodo de sitio y compruebe que se ha establecido un valor de **asignación de enrutamiento de Federación de sitios** .</span><span class="sxs-lookup"><span data-stu-id="27e3f-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Generador de topologías, ruta de Federación de sitios](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="27e3f-136">Seleccione el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="27e3f-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="27e3f-137">Determine si un grupo de servidores perimetrales se ha configurado para los medios por debajo de las **asociaciones**.</span><span class="sxs-lookup"><span data-stu-id="27e3f-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Generador de topología que muestra servidores y pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="27e3f-139">Seleccione el grupo de bordes y identifique si un grupo de saltos siguiente está configurado por debajo de la **selección de próximos saltos**.</span><span class="sxs-lookup"><span data-stu-id="27e3f-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Generador de topologías, selección del próximo salto](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="27e3f-141">Comprobar la configuración heredada del socio XMPP federado</span><span class="sxs-lookup"><span data-stu-id="27e3f-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="27e3f-142">Desde el servidor XMPP heredado, vaya al applet Tools\Services administrativo.</span><span class="sxs-lookup"><span data-stu-id="27e3f-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="27e3f-143">Compruebe que se ha iniciado el servicio de puerta de enlace XMPP de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="27e3f-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Servicio de puerta de enlace XMPP de Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

