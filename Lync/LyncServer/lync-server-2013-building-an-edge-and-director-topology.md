---
title: 'Lync Server 2013: Creación de una topología perimetral y de director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae45053e8d9c01cd484da8a052304712f04a06fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="618d3-102">Creación de una topología perimetral y de director Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="618d3-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="618d3-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="618d3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="618d3-104">La creación de la topología implica las siguientes tareas de planificación e implementación:</span><span class="sxs-lookup"><span data-stu-id="618d3-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="618d3-105">**Planificación**   debe definir una topología adecuada para su organización e identificar los componentes necesarios para implementarlo.</span><span class="sxs-lookup"><span data-stu-id="618d3-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="618d3-106">Estos son pasos estándar en el proceso de planificación.</span><span class="sxs-lookup"><span data-stu-id="618d3-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="618d3-107">La herramienta de planeación de Microsoft Lync Server 2013, que se proporciona con Lync Server 2013 facilita el inicio del proceso de planeación, así como la capacidad de realizar cambios fácilmente a medida que se finalizan los requisitos y los planes.</span><span class="sxs-lookup"><span data-stu-id="618d3-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="618d3-108">**Implementación**   la topología que define con el generador de topología es esencial para la implementación de cualquier servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="618d3-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="618d3-109">Si no finaliza la definición y publicación de la topología mediante el generador de topologías como parte de sus tareas de planeación, debe completarla y publicar la topología antes de implementar los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="618d3-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="618d3-110">No puede implementar componentes de servidor perimetral hasta que haya implementado al menos un grupo interno y debe instalar el generador de topología para implementar un grupo interno.</span><span class="sxs-lookup"><span data-stu-id="618d3-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="618d3-111">En esta sección no se trata la instalación del generador de topologías porque es parte del proceso de instalación del grupo interno.</span><span class="sxs-lookup"><span data-stu-id="618d3-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="618d3-112">Para obtener más información sobre estas herramientas, vea [lista de comprobación de la implementación para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="618d3-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="618d3-113">Si anteriormente usó el generador de topología para definir una topología completa, incluida la topología perimetral, puede omitir las tareas <A href="lync-server-2013-define-your-edge-topology.md">definir la topología perimetral de Lync server 2013</A> y <A href="lync-server-2013-publish-your-topology.md">publicar la topología en Lync Server 2013</A> en esta sección, pero necesita para completar la <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">topología de exportación de Lync Server 2013 y copiarla en medios externos para la tarea de instalación perimetral</A> .</span><span class="sxs-lookup"><span data-stu-id="618d3-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="618d3-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="618d3-114">In This Section</span></span>

  - [<span data-ttu-id="618d3-115">Definir la topología perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="618d3-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="618d3-116">Definir topologías de Director opcionales en la topología para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="618d3-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="618d3-117">Publicar una topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="618d3-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="618d3-118">Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral</span><span class="sxs-lookup"><span data-stu-id="618d3-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

