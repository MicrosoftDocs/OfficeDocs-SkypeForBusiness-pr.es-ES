---
title: Lync Server 2013 opciones de emparejamiento de grupo admitidas y procedimientos recomendados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90e1c28e6c16a7008232ef65d91cd252a3e2855f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524017"
---
# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="938bd-102">Opciones de emparejamiento de grupo admitidas y procedimientos recomendados para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="938bd-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="938bd-103">_**Última modificación del tema:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="938bd-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="938bd-p101">No hay ninguna restricción en la distancia entre dos centros de datos que están para incluir grupos de servidores front-end emparejados entre sí. Se recomienda usar dos centros de datos de la misma región del mundo, con vínculos de alta velocidad entre ellos. Es mejor si los dos centros de datos están separados lo suficiente como para evitar un desastre si se golpean ambos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="938bd-p101">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other. We recommend that you use two data centers in the same world region, with high-speed links between them. It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="938bd-107">Tener dos centros de datos en regiones del mundo, es posible, pero podría provocar una pérdida de datos mayor debido a la latencia de replicación de datos.</span><span class="sxs-lookup"><span data-stu-id="938bd-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="938bd-108">Al planear qué grupos de servidores emparejar, debe tener en cuenta que solo se admiten las parejas siguientes:</span><span class="sxs-lookup"><span data-stu-id="938bd-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="938bd-p102">Los grupos de servidores de Enterprise Edition se pueden emparejar solo con otros grupos de servidores de Enterprise Edition. De manera similar, los grupos de servidores de Standard Edition solo se pueden emparejar con otros grupos de servidores de Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="938bd-p102">Enterprise Edition pools can be paired only with other Enterprise Edition pools. Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="938bd-p103">Los grupos de servidores físicos se pueden emparejar solo con otros grupos de servidores físicos. De manera similar, los grupos de servidores virtuales solo se pueden emparejar con otros grupos de servidores virtuales.</span><span class="sxs-lookup"><span data-stu-id="938bd-p103">Physical pools can be paired only with other physical pools. Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="938bd-113">Los grupos que están emparejados juntos deben ejecutar el mismo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="938bd-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="938bd-114">Ningún Generador de topologías ni ninguna validación de topología prohibirá el emparejamiento de dos grupos de servidores de forma que no siga estas recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="938bd-114">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations.</span></span> <span data-ttu-id="938bd-115">Por ejemplo, el Generador de topologías permite emparejar un grupo de servidores de Enterprise Edition con un grupo de servidores de Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="938bd-115">For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool.</span></span> <span data-ttu-id="938bd-116">Sin embargo, no se admiten estos tipos de emparejamientos.</span><span class="sxs-lookup"><span data-stu-id="938bd-116">However, these types of pairings are not supported.</span></span>

<span data-ttu-id="938bd-117">Cada grupo de servidores en un par debe tener la capacidad para servir a todos los usuarios de ambos grupos de servidores en caso de desastre</span><span class="sxs-lookup"><span data-stu-id="938bd-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="938bd-118">Si empareja grupos de servidores de Enterprise Edition, también puede implementar alta disponibilidad en los servidores back-end, pero para los pares de grupos de servidores de Standard Edition solo están disponibles las medidas de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="938bd-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

