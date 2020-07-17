---
title: Implementar el servidor perimetral piloto
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
description: En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Skype empresarial Server 2019. Los procesos de implementación y configuración de Skype empresarial Server 2019 son muy similares a los de Skype empresarial Server 2015. En esta sección solo se detallan los aspectos clave que hay que considerar al implementar el grupo piloto. Para obtener los pasos detallados, consulte Deploying external User Access in Skype for Business Server 2019 en la documentación sobre implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752872"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="e47f1-106">Implementar el servidor perimetral piloto</span><span class="sxs-lookup"><span data-stu-id="e47f1-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="e47f1-107">En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e47f1-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="e47f1-108">Los procesos de implementación y configuración de Skype empresarial Server 2019 son muy similares a los de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e47f1-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="e47f1-109">En esta sección solo se detallan los aspectos clave que hay que considerar al implementar el grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="e47f1-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="e47f1-p103">Al navegar por el asistente **Definir nuevo grupo de servidores perimetrales**, repase las principales opciones de configuración recogidas en cada paso. Observe que solo se muestran unas cuantas páginas de\*\*\*\* este asistente.</span><span class="sxs-lookup"><span data-stu-id="e47f1-p103">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="e47f1-112">Para definir un grupo de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="e47f1-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="e47f1-113">Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e47f1-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="e47f1-114">Navegue hasta el nodo Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e47f1-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="e47f1-115">haga clic con el botón secundario en **Grupos de servidores perimetrales** y en **Nuevo grupo de servidores perimetrales**.</span><span class="sxs-lookup"><span data-stu-id="e47f1-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Definir el cuadro de diálogo nuevo grupo de servidores perimetrales](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="e47f1-117">Un grupo de servidores perimetrales puede ser un **Grupo de varios equipos** o un **Grupo de un solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="e47f1-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Cuadro de diálogo definir el FQDN del grupo de servidores perimetrales](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="e47f1-119">En la página **Seleccionar características**, no habilite la federación ni la federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="e47f1-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="e47f1-120">La Federación y la Federación de XMPP se enrutan actualmente a través del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="e47f1-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="e47f1-121">Estas características se configurarán en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="e47f1-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="e47f1-122">Siga completando las siguientes páginas del asistente: **FQDN externos**, **definir la dirección IP interna**y **definir la dirección IP externa**.</span><span class="sxs-lookup"><span data-stu-id="e47f1-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="e47f1-123">En la página **definir el servidor del próximo salto** , seleccione el director para el próximo salto del grupo de servidores perimetrales heredados.</span><span class="sxs-lookup"><span data-stu-id="e47f1-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Cuadro de diálogo definir el próximo salto](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="e47f1-125">En la página **asociar grupos de servidores front-end o de mediación** , no asocie un grupo de servidores con este grupo de servidores perimetrales en este momento.</span><span class="sxs-lookup"><span data-stu-id="e47f1-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="e47f1-126">El tráfico multimedia externo se enruta actualmente a través del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="e47f1-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="e47f1-127">Definiremos esta configuración en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="e47f1-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Cuadro de diálogo asociar grupos de servidores front-end](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="e47f1-129">Haga clic en **Finalizar** y después en **Publicar** para publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="e47f1-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="e47f1-130">Siga los pasos de la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar los certificados e iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="e47f1-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="e47f1-131">Es muy importante que siga las instrucciones de los temas de la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="e47f1-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="e47f1-132">En esta sección solo se ha proporcionado cierta orientación sobre las opciones de configuración al instalar estos roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="e47f1-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="e47f1-133">Ahora debe tener un servidor perimetral heredado implementado en paralelo con una implementación de servidor perimetral de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e47f1-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="e47f1-134">Antes de pasar a la siguiente fase, confirme que ambas implementaciones funcionan correctamente, que los servicios se han iniciado y que puede administrar cada una de las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="e47f1-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

