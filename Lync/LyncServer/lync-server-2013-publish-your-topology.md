---
title: 'Lync Server 2013: publicar la topología'
description: 'Lync Server 2013: publique la topología.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4d27d2d3644eb1f174e2f3fab47197f2c122a97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571756"
---
# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="63a41-103">Publicar la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63a41-103">Publish your topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63a41-104">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="63a41-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="63a41-105">Cada vez que use el generador de topologías para compilar la topología, debe publicar la topología en una base de datos en el almacén de administración central para que los datos puedan usarse para implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63a41-105">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="63a41-106">Siga el procedimiento indicado a continuación para publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="63a41-106">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="63a41-107">Para publicar la topología</span><span class="sxs-lookup"><span data-stu-id="63a41-107">To publish the topology</span></span>

1.  <span data-ttu-id="63a41-108">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="63a41-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="63a41-109">En el generador de topologías, en el árbol de la consola, haga clic con el botón secundario en **Lync 2013**y, a continuación, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="63a41-109">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="63a41-110">En la página **principal** del Asistente, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="63a41-110">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="63a41-111">En la página **Generador de topologías ha encontrado un almacén de administración de configuración**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="63a41-111">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="63a41-112">En la página **Crear otras bases de datos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="63a41-112">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="63a41-113">Cuando el estado indica que la creación de bases de datos se ha realizado correctamente, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="63a41-113">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="63a41-114">Para visualizar el registro, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="63a41-114">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="63a41-115">Para cerrar el asistente, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="63a41-115">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="63a41-116">Si se trata de una nueva instalación de un servidor perimetral o un grupo de servidores perimetrales, debe exportar la configuración del servidor perimetral desde un servidor front-end existente, un grupo de servidores front-end o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="63a41-116">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="63a41-117">Para exportar la configuración, consulte <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral</A>.</span><span class="sxs-lookup"><span data-stu-id="63a41-117">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="63a41-118">Importará el archivo de configuración desde el medio externo o el recurso compartido de red durante la fase de instalación e implementación de los servidores perimetrales mediante el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="63a41-118">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="63a41-119">Una vez que los servidores perimetrales están operativos y la base de datos de almacenamiento de administración de configuración local se replica con la implementación interna, las actualizaciones posteriores de la configuración de Lync Server 2013 se publicarán y replicarán en los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="63a41-119">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

