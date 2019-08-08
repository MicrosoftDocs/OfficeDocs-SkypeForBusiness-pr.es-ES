---
title: Conecte el grupo de servidores piloto a los servidores perimetrales heredados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de implementar Skype empresarial Server 2019, debe configurar una ruta de Federación para el sitio. Para poder usar la ruta federada que usa la instalación heredada, Skype empresarial Server 2019 debe estar configurado para usar esta ruta.
ms.openlocfilehash: 7a5a65e1488d5a119e3d11affbbaa9995a06626e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239227"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="67a80-104">Conecte el grupo de servidores piloto a los servidores perimetrales heredados</span><span class="sxs-lookup"><span data-stu-id="67a80-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="67a80-105">Después de implementar Skype empresarial Server 2019, debe configurar una ruta de Federación para el sitio.</span><span class="sxs-lookup"><span data-stu-id="67a80-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="67a80-106">Para poder usar la ruta federada que usa la instalación heredada, Skype empresarial Server 2019 debe estar configurado para usar esta ruta.</span><span class="sxs-lookup"><span data-stu-id="67a80-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="67a80-107">Para permitir que el sitio de Skype empresarial Server 2019 use el director y el servidor perimetral de la implementación heredada, use el generador de topología para asociar el grupo perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="67a80-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="67a80-108">Para asociar el grupo perimetral heredado mediante el generador de topología</span><span class="sxs-lookup"><span data-stu-id="67a80-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="67a80-109">Abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="67a80-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="67a80-110">Seleccione su sitio, que se encuentra directamente debajo del nodo **de Skype empresarial Server** .</span><span class="sxs-lookup"><span data-stu-id="67a80-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="67a80-111">En el menú **acciones** , haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="67a80-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="67a80-112">En el panel de la izquierda, seleccione **ruta de Federación**.</span><span class="sxs-lookup"><span data-stu-id="67a80-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="67a80-113">En **asignación**de la ruta de Federación de sitios, seleccione **Habilitar Federación SIP**y, a continuación, seleccione el director heredado o el servidor perimetral heredado si no se muestra ningún director.</span><span class="sxs-lookup"><span data-stu-id="67a80-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="67a80-114">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="67a80-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="67a80-115">En el generador de topologías, en el nodo de Skype empresarial Server 2019, vaya a los grupos de servidores **Standard Edition** o **Enterprise Edition**, haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="67a80-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="67a80-116">En **asociaciones**, active la casilla situada junto a **asociar grupo perimetral (para componentes multimedia)**.</span><span class="sxs-lookup"><span data-stu-id="67a80-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="67a80-117">En la lista, seleccione el servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="67a80-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="67a80-118">Haga clic en **Aceptar** para cerrar la página **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="67a80-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="67a80-119">En el **generador**de topologías, seleccione el nodo de nivel superior, **Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="67a80-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="67a80-120">En el menú **acción** , haga clic en **publicar topología**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="67a80-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="67a80-121">Cuando finalice el **Asistente para la publicación** , haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="67a80-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

