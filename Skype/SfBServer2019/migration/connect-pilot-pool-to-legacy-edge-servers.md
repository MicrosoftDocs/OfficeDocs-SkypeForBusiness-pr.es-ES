---
title: Conecte el grupo de servidores piloto a los servidores perimetrales heredados
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
description: Después de implementar Skype Empresarial Server 2019, debe configurar una ruta de federación para su sitio. Para usar la ruta federada que está utilizando la instalación heredada, Skype Empresarial Server 2019 debe configurarse para usar esta ruta.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753930"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="acf34-104">Conecte el grupo de servidores piloto a los servidores perimetrales heredados</span><span class="sxs-lookup"><span data-stu-id="acf34-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="acf34-105">Después de implementar Skype Empresarial Server 2019, debe configurar una ruta de federación para su sitio.</span><span class="sxs-lookup"><span data-stu-id="acf34-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="acf34-106">Para usar la ruta federada que está utilizando la instalación heredada, Skype Empresarial Server 2019 debe configurarse para usar esta ruta.</span><span class="sxs-lookup"><span data-stu-id="acf34-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="acf34-107">Para habilitar el sitio de Skype Empresarial Server 2019 para que use el director y el servidor perimetral de la implementación heredada, use topology Builder para asociar el grupo de servidores perimetrales heredado.</span><span class="sxs-lookup"><span data-stu-id="acf34-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="acf34-108">Para asociar el grupo de servidores perimetrales heredados usando el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="acf34-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="acf34-109">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="acf34-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="acf34-110">Seleccione su sitio, que está directamente debajo del **nodo de Skype Empresarial Server.**</span><span class="sxs-lookup"><span data-stu-id="acf34-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="acf34-111">En el menú **Acciones**, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="acf34-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="acf34-112">En el panel izquierdo, seleccione **Ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="acf34-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="acf34-113">En **Asignación de ruta** de federación de sitio, seleccione Habilitar federación **SIP** y, a continuación, seleccione el director heredado o el servidor perimetral heredado si no aparece ningún director.</span><span class="sxs-lookup"><span data-stu-id="acf34-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="acf34-114">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="acf34-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="acf34-115">En el Generador de topologías, en el nodo de Skype Empresarial Server 2019, vaya al servidor **Standard Edition** o a los grupos de servidores **front-end de Enterprise Edition,** haga clic con el botón secundario en el grupo y, a continuación, haga clic en Editar **propiedades.**</span><span class="sxs-lookup"><span data-stu-id="acf34-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="acf34-116">En **Asociaciones**, active la casilla situada junto a **Grupo de servidores perimetrales asociados (para componentes multimedia)**.</span><span class="sxs-lookup"><span data-stu-id="acf34-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="acf34-117">En la lista, seleccione el servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="acf34-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="acf34-118">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="acf34-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="acf34-119">En **el Generador de** topologías, seleccione el nodo superior, Skype Empresarial **Server**.</span><span class="sxs-lookup"><span data-stu-id="acf34-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="acf34-120">En el menú **Acción**, haga clic en **Publicar topología** y en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="acf34-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="acf34-121">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="acf34-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

