---
title: 'Lync Server 2013: creación de una topología perimetral y de Director'
description: 'Lync Server 2013: creación de una topología perimetral y de director.'
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
ms.openlocfilehash: bcb2d422136cf0a421c68ebc2adba50f03c5cc85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569276"
---
# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="c11e8-103">Creación de una topología perimetral y de Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c11e8-103">Building an edge and Director topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c11e8-104">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c11e8-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c11e8-105">La creación de la topología implica las siguientes tareas de planeación e implementación:</span><span class="sxs-lookup"><span data-stu-id="c11e8-105">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="c11e8-106">**Planeación**     Debe definir una topología adecuada para su organización e identificar los componentes necesarios para implementarla.</span><span class="sxs-lookup"><span data-stu-id="c11e8-106">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="c11e8-107">Estos son los pasos estándar del proceso de planeación.</span><span class="sxs-lookup"><span data-stu-id="c11e8-107">These are standard steps in the planning process.</span></span> <span data-ttu-id="c11e8-108">La herramienta de planeación de Microsoft Lync Server 2013, que se proporciona con Lync Server 2013 facilita el inicio del proceso de planeación, así como la capacidad de realizar cambios fácilmente a medida que se finalizan los requisitos y los planes.</span><span class="sxs-lookup"><span data-stu-id="c11e8-108">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="c11e8-109">**Implementación**     de La topología que se define mediante el generador de topologías es esencial para la implementación de cualquier servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c11e8-109">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="c11e8-110">Si no termina de definir y publicar la topología con el generador de topologías como parte de los esfuerzos de planeación, debe completarla y publicar la topología antes de implementar los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="c11e8-110">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="c11e8-111">No puede implementar componentes del servidor perimetral hasta que haya implementado al menos un grupo interno y debe instalar el generador de topologías para implementar un grupo de servidores interno.</span><span class="sxs-lookup"><span data-stu-id="c11e8-111">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="c11e8-112">Esta sección no cubre la instalación del generador de topologías porque es parte del proceso de instalación del grupo interno.</span><span class="sxs-lookup"><span data-stu-id="c11e8-112">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="c11e8-113">Para obtener más información sobre estas herramientas, consulte [Deployment Checklist for external User Access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="c11e8-113">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c11e8-114">Si anteriormente usó el generador de topologías para definir una topología completa, incluida la topología perimetral, puede omitir las tareas <A href="lync-server-2013-define-your-edge-topology.md">definir la topología perimetral en Lync server 2013</A> y <A href="lync-server-2013-publish-your-topology.md">publicar la topología en Lync Server 2013</A> en esta sección, pero necesita completar la <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">topología exportar su Lync Server 2013 y copiarla en medios externos para la tarea de instalación perimetral</A> .</span><span class="sxs-lookup"><span data-stu-id="c11e8-114">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c11e8-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c11e8-115">In This Section</span></span>

  - [<span data-ttu-id="c11e8-116">Definir la topología perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c11e8-116">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="c11e8-117">Definir topologías de Director opcionales en la topología para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c11e8-117">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="c11e8-118">Publicar la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c11e8-118">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="c11e8-119">Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral</span><span class="sxs-lookup"><span data-stu-id="c11e8-119">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

