---
title: 'Lync Server 2013: creación de una topología perimetral y de Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d3e88cae787a47d1fe519cfbe5c27acf5ad821
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537277"
---
# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="747c1-102">Creación de una topología perimetral y de Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="747c1-102">Building an edge and Director topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="747c1-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="747c1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="747c1-104">La creación de la topología implica las siguientes tareas de planeación e implementación:</span><span class="sxs-lookup"><span data-stu-id="747c1-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="747c1-105">**Planeación**     Debe definir una topología adecuada para su organización e identificar los componentes necesarios para implementarla.</span><span class="sxs-lookup"><span data-stu-id="747c1-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="747c1-106">Estos son los pasos estándar del proceso de planeación.</span><span class="sxs-lookup"><span data-stu-id="747c1-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="747c1-107">La herramienta de planeación de Microsoft Lync Server 2013, que se proporciona con Lync Server 2013 facilita el inicio del proceso de planeación, así como la capacidad de realizar cambios fácilmente a medida que se finalizan los requisitos y los planes.</span><span class="sxs-lookup"><span data-stu-id="747c1-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="747c1-108">**Implementación**     de La topología que se define mediante el generador de topologías es esencial para la implementación de cualquier servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="747c1-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="747c1-109">Si no termina de definir y publicar la topología con el generador de topologías como parte de los esfuerzos de planeación, debe completarla y publicar la topología antes de implementar los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="747c1-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="747c1-110">No puede implementar componentes del servidor perimetral hasta que haya implementado al menos un grupo interno y debe instalar el generador de topologías para implementar un grupo de servidores interno.</span><span class="sxs-lookup"><span data-stu-id="747c1-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="747c1-111">Esta sección no cubre la instalación del generador de topologías porque es parte del proceso de instalación del grupo interno.</span><span class="sxs-lookup"><span data-stu-id="747c1-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="747c1-112">Para obtener más información sobre estas herramientas, consulte [Deployment Checklist for external User Access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="747c1-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="747c1-113">Si anteriormente usó el generador de topologías para definir una topología completa, incluida la topología perimetral, puede omitir las tareas <A href="lync-server-2013-define-your-edge-topology.md">definir la topología perimetral en Lync server 2013</A> y <A href="lync-server-2013-publish-your-topology.md">publicar la topología en Lync Server 2013</A> en esta sección, pero necesita completar la <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">topología exportar su Lync Server 2013 y copiarla en medios externos para la tarea de instalación perimetral</A> .</span><span class="sxs-lookup"><span data-stu-id="747c1-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="747c1-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="747c1-114">In This Section</span></span>

  - [<span data-ttu-id="747c1-115">Definir la topología perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="747c1-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="747c1-116">Definir topologías de Director opcionales en la topología para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="747c1-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="747c1-117">Publicar la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="747c1-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="747c1-118">Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral</span><span class="sxs-lookup"><span data-stu-id="747c1-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

