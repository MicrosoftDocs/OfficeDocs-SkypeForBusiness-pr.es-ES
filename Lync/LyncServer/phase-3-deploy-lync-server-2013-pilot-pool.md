---
title: 'Fase 3: implementar el grupo piloto de Lync Server 2013'
description: 'Fase 3: implementar el grupo piloto de Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Phase 3: Deploy Lync Server 2013 pilot pool'
ms:assetid: f12b1517-fb56-4ded-8323-57aa9fc9ea48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205367(v=OCS.15)
ms:contentKeyID: 48185778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f72f0cdd2e7d3b9e29891a4adc0ab0551539f465
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571166"
---
# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="57af9-103">Fase 3: implementar el grupo piloto de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57af9-103">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57af9-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="57af9-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="57af9-105">En esta sección se describen los pasos necesarios para implementar un grupo piloto de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57af9-105">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="57af9-106">La implementación de Lync Server 2013 requiere el uso del generador de topologías para definir la topología y los componentes que desea implementar, preparar el entorno para la implementación de los componentes de Lync Server 2013, publicar el diseño de la topología en el primer servidor front-end y, a continuación, instalar y configurar el software Lync Server 2013 para los componentes de la implementación.</span><span class="sxs-lookup"><span data-stu-id="57af9-106">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="57af9-107">Una vez completada, la implementación del grupo piloto de Lync Server 2013 coexistirá con un grupo existente de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="57af9-107">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="57af9-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="57af9-108">In This Section</span></span>

  - [<span data-ttu-id="57af9-109">Preparar Active Directory para Lync Server</span><span class="sxs-lookup"><span data-stu-id="57af9-109">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="57af9-110">Descargar una topología desde una implementación existente</span><span class="sxs-lookup"><span data-stu-id="57af9-110">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="57af9-111">Implementar el grupo piloto de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57af9-111">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="57af9-112">Comprobar la coexistencia del grupo de servidores piloto con el grupo de servidores heredado</span><span class="sxs-lookup"><span data-stu-id="57af9-112">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="57af9-113">Conecte el grupo de servidores piloto a los servidores perimetrales heredados</span><span class="sxs-lookup"><span data-stu-id="57af9-113">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="57af9-114">Configurar certificados y directivas de acceso por puerta de enlace XMPP</span><span class="sxs-lookup"><span data-stu-id="57af9-114">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

