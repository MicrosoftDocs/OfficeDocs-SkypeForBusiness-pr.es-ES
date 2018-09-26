---
title: Conectar el grupo piloto a servidores perimetrales heredados
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de la implementación de Skype para 2019 de servidor empresarial, debe configurar una ruta de federación para su sitio. Para poder usar la ruta federada que está siendo utilizada por la instalación heredada, Skype para Business Server 2019 debe configurarse para utilizar esta ruta.
ms.openlocfilehash: 6766034cf54fd867c9b270324cb1db8ad2d644d5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030570"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="ef480-104">Conectar el grupo piloto a servidores perimetrales heredados</span><span class="sxs-lookup"><span data-stu-id="ef480-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="ef480-105">Después de la implementación de Skype para 2019 de servidor empresarial, debe configurar una ruta de federación para su sitio.</span><span class="sxs-lookup"><span data-stu-id="ef480-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="ef480-106">Para poder usar la ruta federada que está siendo utilizada por la instalación heredada, Skype para Business Server 2019 debe configurarse para utilizar esta ruta.</span><span class="sxs-lookup"><span data-stu-id="ef480-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="ef480-107">Para habilitar la Skype para Business Server 2019 sitios usar el Director y el servidor perimetral de la implementación heredada, use el generador de topología para asociar el grupo de servidores perimetrales heredado.</span><span class="sxs-lookup"><span data-stu-id="ef480-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="ef480-108">Para asociar el grupo de servidores perimetrales heredado mediante el generador de topología</span><span class="sxs-lookup"><span data-stu-id="ef480-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="ef480-109">Abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ef480-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="ef480-110">Seleccione su sitio, que se encuentra justo debajo del nodo de **Skype para Business Server** .</span><span class="sxs-lookup"><span data-stu-id="ef480-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="ef480-111">En el menú **acciones** , haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ef480-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="ef480-112">En el panel izquierdo, seleccione **ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="ef480-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="ef480-113">En **asignación de ruta de federación de sitio**, seleccione **Habilitar federación SIP**y, a continuación, seleccione el Director heredado o el servidor perimetral heredado si se muestra ningún Director.</span><span class="sxs-lookup"><span data-stu-id="ef480-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="ef480-114">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="ef480-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="ef480-115">En el generador, bajo el Skype para Business Server 2019 nodo, desplácese hasta el **servidor Standard Edition** o **grupos de servidores Front-End de Enterprise Edition**, (ratón) en el grupo de servidores y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ef480-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="ef480-116">En **asociaciones**, active la casilla de verificación situada junto a **grupo de servidores perimetrales asociados (para componentes multimedia)**.</span><span class="sxs-lookup"><span data-stu-id="ef480-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="ef480-117">En la lista, seleccione el servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="ef480-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="ef480-118">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="ef480-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="ef480-119">En **El generador de topología**, seleccione el nodo de nivel superior, **Skype para Business Server**.</span><span class="sxs-lookup"><span data-stu-id="ef480-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="ef480-120">En el menú **acción** , haga clic en **Publicar topología**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ef480-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="ef480-121">Cuando se complete el **Asistente para la publicación** , haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ef480-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

