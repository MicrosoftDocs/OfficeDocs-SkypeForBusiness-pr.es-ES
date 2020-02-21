---
title: Conectar el grupo piloto a servidores perimetrales heredados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48d2450d468ae6a28faef4c1fcacf577262c42f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="20668-102">Conectar el grupo piloto a servidores perimetrales heredados</span><span class="sxs-lookup"><span data-stu-id="20668-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20668-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="20668-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="20668-104">Después de implementar Lync Server 2013, no se configura ninguna ruta de Federación para este sitio.</span><span class="sxs-lookup"><span data-stu-id="20668-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="20668-105">Para poder usar la ruta federada que usa Office Communications Server 2007 R2, Lync Server 2013 debe estar configurado para usar esta ruta.</span><span class="sxs-lookup"><span data-stu-id="20668-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="20668-106">Para habilitar el sitio de Lync Server 2013 para usar el director y el servidor perimetral de BackCompatSite, use el generador de topologías para asociar el grupo de servidores perimetrales heredados.</span><span class="sxs-lookup"><span data-stu-id="20668-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="20668-107">Para asociar el grupo perimetral heredado mediante el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="20668-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="20668-108">Abra la topología del grupo piloto en Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="20668-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="20668-109">Seleccione su sitio de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20668-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="20668-110">En el menú **Acción**, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="20668-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="20668-111">En **asignación de ruta de Federación del sitio**, seleccione **Habilitar Federación SIP**y, a continuación, seleccione el director de Office Communications Server 2007 R2 o el servidor perimetral de Office Communications Server 2007 R2 si no hay ningún director en la lista.</span><span class="sxs-lookup"><span data-stu-id="20668-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="20668-112">![Cuadro de diálogo Editar propiedades, página Ruta de Federación](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página Ruta de Federación")</span><span class="sxs-lookup"><span data-stu-id="20668-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="20668-113">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="20668-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="20668-114">En el generador de topologías, en el nodo Lync Server 2013, vaya a los grupos de servidores **front-end** **Standard Edition** o Enterprise Edition, haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="20668-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="20668-115">En **Asociaciones**, active la casilla que se encuentra junto a **Grupo de servidores perimetrales asociados (para componentes multimedia)**.</span><span class="sxs-lookup"><span data-stu-id="20668-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="20668-116">En la lista, seleccione la interfaz del servidor perimetral de la BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="20668-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="20668-117">![Cuadro de diálogo Editar propiedades, página general](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página general")</span><span class="sxs-lookup"><span data-stu-id="20668-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="20668-118">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="20668-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="20668-119">En el **Generador de topologías**, seleccione el nodo superior, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="20668-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="20668-120">En el menú **Acciones**, haga clic en **Publicar topología** y en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="20668-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="20668-121">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="20668-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

