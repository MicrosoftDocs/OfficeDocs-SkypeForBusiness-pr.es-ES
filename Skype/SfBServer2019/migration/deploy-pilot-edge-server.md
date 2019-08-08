---
title: Implementar el servidor perimetral piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En este tema se destacan las opciones de configuración que debería conocer antes de implementar el servidor perimetral de Skype empresarial Server 2019. Los procesos de implementación y configuración de Skype empresarial Server 2019 son muy similares a los de Skype empresarial Server 2015. Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación de un grupo piloto. Para conocer los pasos detallados, vea implementar el acceso de usuarios externos en Skype empresarial Server 2019 en la documentación de implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.
ms.openlocfilehash: b416ba38646d05f3d10a7d2643c01924fe57020a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238391"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="5b78a-106">Implementar el servidor perimetral piloto</span><span class="sxs-lookup"><span data-stu-id="5b78a-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="5b78a-107">En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5b78a-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="5b78a-108">Los procesos de implementación y configuración de Skype empresarial Server 2019 son muy similares a los de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5b78a-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="5b78a-109">Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación de un grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="5b78a-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="5b78a-110">Mientras navega por el asistente **definir nuevo grupo de bordes** , revise la configuración de clave que se muestra en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="5b78a-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="5b78a-111">Observe que solo se muestran algunas páginas del asistente **definir nuevo grupo de bordes** .</span><span class="sxs-lookup"><span data-stu-id="5b78a-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="5b78a-112">Para definir un grupo de límites</span><span class="sxs-lookup"><span data-stu-id="5b78a-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="5b78a-113">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5b78a-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="5b78a-114">Vaya al nodo de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5b78a-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="5b78a-115">Haga clic con \*\*\*\* el botón secundario en agrupaciones perimetrales y haga clic en **nuevo borde**.</span><span class="sxs-lookup"><span data-stu-id="5b78a-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Definir el cuadro de diálogo nuevo grupo perimetral](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="5b78a-117">Un grupo de servidores perimetrales puede ser un **grupo de varios equipos** o un **único grupo de equipos**.</span><span class="sxs-lookup"><span data-stu-id="5b78a-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Definir el cuadro de diálogo FQDN del grupo de bordes](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="5b78a-119">En la página **seleccionar características** , no habilite la Federación ni la Federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="5b78a-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="5b78a-120">La Federación y la Federación de XMPP actualmente se enrutan a través del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="5b78a-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="5b78a-121">Estas características se configurarán en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="5b78a-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="5b78a-122">Siga completando las siguientes páginas del asistente: **FQDN externos**, **defina la dirección IP interna**y **defina la dirección IP externa**.</span><span class="sxs-lookup"><span data-stu-id="5b78a-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="5b78a-123">En la página **definir el servidor del próximo salto** , seleccione el director para el próximo salto del grupo de servidores perimetrales heredados.</span><span class="sxs-lookup"><span data-stu-id="5b78a-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Definir el cuadro de diálogo siguiente del salto](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="5b78a-125">En la página **asociar grupos de servicios de media o front-end** , no asocie un grupo con este grupo de límites en este momento.</span><span class="sxs-lookup"><span data-stu-id="5b78a-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="5b78a-126">El tráfico multimedia externo está enrutado a través del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="5b78a-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="5b78a-127">Esta configuración se configurará en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="5b78a-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Cuadro de diálogo asociar grupos front-end](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="5b78a-129">Haga clic en **Finalizar**y, a continuación, **publique** la topología.</span><span class="sxs-lookup"><span data-stu-id="5b78a-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="5b78a-130">Siga los pasos que se indican en la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar certificados e iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="5b78a-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="5b78a-131">Es muy importante seguir las directrices de los temas de la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="5b78a-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="5b78a-132">En esta sección se proporciona una mera información sobre las opciones de configuración al instalar estos roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="5b78a-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="5b78a-133">Ahora debe tener un servidor perimetral heredado implementado en paralelo con una implementación de servidor perimetral de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5b78a-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="5b78a-134">Compruebe que las implementaciones se ejecutan correctamente y que se inician los servicios, y puede administrar cada implementación antes de pasar a la siguiente fase.</span><span class="sxs-lookup"><span data-stu-id="5b78a-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

