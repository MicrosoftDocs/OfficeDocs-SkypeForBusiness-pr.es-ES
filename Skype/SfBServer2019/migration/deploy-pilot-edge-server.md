---
title: Implementar el servidor perimetral piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este tema resalta las opciones de configuración que deben tener en cuenta antes de implementar su Skype para servidor perimetral de Business Server 2019. Los procesos de implementación y configuración de Skype para Business Server 2019 son muy similares a Skype para Business Server 2015. Esta sección resalta sólo puntos clave que debe tener en cuenta como parte de la implementación del grupo piloto. Para obtener instrucciones detalladas, vea implementar el acceso de usuarios externos en Skype para Business Server 2019 en la documentación de implementación, que se describe el proceso de implementación y también se proporciona información de configuración para el acceso de usuarios externos.
ms.openlocfilehash: 5b755d0ba8802c47a176cb3375a87b6523f35fad
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876201"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="f6731-106">Implementar el servidor perimetral piloto</span><span class="sxs-lookup"><span data-stu-id="f6731-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="f6731-107">En este tema resalta las opciones de configuración que deben tener en cuenta antes de implementar su Skype para servidor perimetral de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f6731-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="f6731-108">Los procesos de implementación y configuración de Skype para Business Server 2019 son muy similares a Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f6731-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="f6731-109">Esta sección resalta sólo puntos clave que debe tener en cuenta como parte de la implementación del grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="f6731-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="f6731-110">Al desplazarse por el Asistente para **Definir nuevo grupo perimetral** , revise las opciones de configuración de clave que se muestra en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="f6731-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="f6731-111">Tenga en cuenta que se muestran sólo algunas páginas del Asistente para **Definir nuevo grupo de servidores de borde** .</span><span class="sxs-lookup"><span data-stu-id="f6731-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="f6731-112">Para definir un grupo de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="f6731-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="f6731-113">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f6731-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="f6731-114">Navegue hasta el Skype para Business Server 2019 nodo.</span><span class="sxs-lookup"><span data-stu-id="f6731-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="f6731-115">Haga clic en **grupos de servidores perimetrales**y haga clic en **grupo de servidores perimetrales de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f6731-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Definir el cuadro de diálogo nuevo grupo de servidores perimetrales](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="f6731-117">Un grupo de servidores perimetrales puede ser un **grupo de varios equipos** o **grupo de servidores de un solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="f6731-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Definir el cuadro de diálogo de FQDN del grupo de servidores perimetrales](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="f6731-119">En la página **Seleccionar características** , no habilitar la federación o la federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="f6731-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="f6731-120">Federación y la federación XMPP se ambos actualmente enrutan a través del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="f6731-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="f6731-121">Estas características se configurarán en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="f6731-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="f6731-122">Siga completando las siguientes páginas del asistente: **FQDN externos**, **definir la dirección IP interna**y **definir la dirección IP externa**.</span><span class="sxs-lookup"><span data-stu-id="f6731-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="f6731-123">En la página **definir el servidor del próximo salto** , seleccione el Director para el próximo salto del grupo de servidores perimetrales heredado.</span><span class="sxs-lookup"><span data-stu-id="f6731-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Definir el cuadro de diálogo próximo salto](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="f6731-125">En la página **asociar Front-End o grupos de servidores de mediación** , no se asocia un grupo de servidores con este grupo de servidores perimetrales en este momento.</span><span class="sxs-lookup"><span data-stu-id="f6731-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="f6731-126">Actualmente se enruta el tráfico de medios externos a través del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="f6731-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="f6731-127">Esta configuración se configurarán en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="f6731-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Asociar el cuadro de diálogo de grupos de servidores Front-End](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="f6731-129">Haga clic en **Finalizar**y, a continuación, en **Publicar** la topología.</span><span class="sxs-lookup"><span data-stu-id="f6731-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="f6731-130">Siga los pasos descritos en la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar los certificados e iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="f6731-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="f6731-131">Es muy importante que siga las instrucciones que aparecen en los temas de la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f6731-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="f6731-132">En esta sección se proporciona simplemente algunas instrucciones en Opciones de configuración al instalar estas funciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="f6731-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="f6731-133">Ahora debería tener un servidor perimetral heredado implementado en paralelo con un Skype para la implementación del servidor perimetral de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f6731-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="f6731-134">Compruebe que tanto las implementaciones se ejecutan correctamente, se inician los servicios, y puede administrar cada implementación antes de pasar a la siguiente fase.</span><span class="sxs-lookup"><span data-stu-id="f6731-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

