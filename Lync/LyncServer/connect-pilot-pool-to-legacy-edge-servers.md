---
title: Conecte el grupo de servidores piloto a los servidores perimetrales heredados
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d12a67b0ba102fdacea66b6196bafe32d89c9d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503107"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="4489e-102">Conecte el grupo de servidores piloto a los servidores perimetrales heredados</span><span class="sxs-lookup"><span data-stu-id="4489e-102">Connect pilot pool to legacy Edge Servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4489e-103">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="4489e-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="4489e-104">Después de implementar Lync Server 2013, debe configurar una ruta de Federación para el sitio.</span><span class="sxs-lookup"><span data-stu-id="4489e-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="4489e-105">Para poder usar la ruta federada que usa Lync Server 2010, Lync Server 2013 debe estar configurado para usar esta ruta.</span><span class="sxs-lookup"><span data-stu-id="4489e-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="4489e-106">Para habilitar el sitio de Lync Server 2013 para usar el director y el servidor perimetral de la implementación de Lync Server 2010, use el generador de topologías para asociar el grupo de servidores perimetrales heredados.</span><span class="sxs-lookup"><span data-stu-id="4489e-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="4489e-107">Para asociar el grupo de servidores perimetrales heredado con el Generador de topologías:</span><span class="sxs-lookup"><span data-stu-id="4489e-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="4489e-108">Abra el **Generador de topologías**.</span><span class="sxs-lookup"><span data-stu-id="4489e-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="4489e-109">Seleccione el sitio, que se encuentra justo debajo del nodo **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4489e-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="4489e-110">En el menú **Acciones**, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4489e-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="4489e-111">En el panel izquierdo, seleccione **Ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="4489e-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="4489e-112">En **asignación de ruta de Federación del sitio**, seleccione **Habilitar Federación SIP**y, a continuación, seleccione el Director de Lync Server 2010 o el servidor perimetral de Lync Server 2010 si no aparece ningún director.</span><span class="sxs-lookup"><span data-stu-id="4489e-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="4489e-113">![Editar propiedades, página Ruta de Federación](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Editar propiedades, página Ruta de Federación")</span><span class="sxs-lookup"><span data-stu-id="4489e-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="4489e-114">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4489e-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="4489e-115">En el generador de topologías, en el nodo Lync Server 2013, vaya a los grupos de servidores **front-end** **Standard Edition** o Enterprise Edition, haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4489e-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="4489e-116">En **Asociaciones**, active la casilla situada junto a **Grupo de servidores perimetrales asociados (para componentes multimedia)**.</span><span class="sxs-lookup"><span data-stu-id="4489e-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="4489e-117">En la lista, seleccione el servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="4489e-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="4489e-118">![Cuadro de diálogo Editar propiedades, selección del perímetro heredado](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Cuadro de diálogo Editar propiedades, selección del perímetro heredado")</span><span class="sxs-lookup"><span data-stu-id="4489e-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="4489e-119">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4489e-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="4489e-120">En el **Generador de topologías**, seleccione el nodo superior, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4489e-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="4489e-121">En el menú **Acciones**, haga clic en **Publicar topología** y en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4489e-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="4489e-122">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4489e-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

