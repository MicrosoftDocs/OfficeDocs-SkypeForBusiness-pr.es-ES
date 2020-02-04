---
title: Prácticas recomendadas y opciones de emparejamiento de grupo compatibles con Lync Server 2013
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
ms.openlocfilehash: 9090fefba4b80f14382b9b43b5e9ced7cb36b2e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a><span data-ttu-id="befd0-102">Opciones de emparejamiento de bloque y procedimientos recomendados para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="befd0-102">Supported pool pairing options and best practices for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="befd0-103">_**Última modificación del tema:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="befd0-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="befd0-104">No hay restricciones en la distancia entre dos centros de datos que se van a incluir los grupos de frontales emparejados entre sí.</span><span class="sxs-lookup"><span data-stu-id="befd0-104">There is no restriction on the distance between two data centers that are to include Front End pools paired with each other.</span></span> <span data-ttu-id="befd0-105">Le recomendamos que use dos centros de datos en la misma región del mundo, con vínculos de alta velocidad entre ellos.</span><span class="sxs-lookup"><span data-stu-id="befd0-105">We recommend that you use two data centers in the same world region, with high-speed links between them.</span></span> <span data-ttu-id="befd0-106">Es mejor que los dos centros de datos estén lo suficientemente separados para evitar que se produzca un desastre único al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="befd0-106">It is best if the two data centers are separated enough to avoid a single disaster hitting both at the same time.</span></span>

<span data-ttu-id="befd0-107">Es posible tener dos centros de datos en todas las regiones del mundo, pero podría provocar una mayor pérdida de datos debido a la latencia en la replicación de datos.</span><span class="sxs-lookup"><span data-stu-id="befd0-107">Having two data centers across world regions is possible, but could incur higher data loss due to latency in data replication.</span></span>

<span data-ttu-id="befd0-108">Al planificar qué grupos de servidores vas a emparejar, necesitas tener en cuenta que solo se admiten los emparejamientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="befd0-108">When you plan which pools to pair, you must keep in mind that only the following pairings are supported:</span></span>

  - <span data-ttu-id="befd0-109">Los grupos de servidores de Enterprise Edition se pueden emparejar solo con otros grupos de servidores de Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="befd0-109">Enterprise Edition pools can be paired only with other Enterprise Edition pools.</span></span> <span data-ttu-id="befd0-110">De manera similar, los grupos de servidores de Standard Edition solo se pueden emparejar con otros grupos de servidores de Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="befd0-110">Similarly, Standard Edition pools can be paired only with other Standard Edition pools.</span></span>

  - <span data-ttu-id="befd0-111">Los grupos de servidores físicos se pueden emparejar solo con otros grupos de servidores físicos.</span><span class="sxs-lookup"><span data-stu-id="befd0-111">Physical pools can be paired only with other physical pools.</span></span> <span data-ttu-id="befd0-112">De manera similar, los grupos de servidores virtuales solo se pueden emparejar con otros grupos de servidores virtuales.</span><span class="sxs-lookup"><span data-stu-id="befd0-112">Similarly, virtual pools can be paired only with other virtual pools.</span></span>

  - <span data-ttu-id="befd0-113">Los grupos que están emparejados deben ejecutar el mismo sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="befd0-113">Pools that are paired together must be running the same operating system.</span></span>

<span data-ttu-id="befd0-p104">Ni el generador de topologías ni la validación de topología prohibirán el emparejamiento de dos grupos de servidores de un modo que no siga estas recomendaciones. Por ejemplo, el generador de topologías permite emparejar un grupo de servidores Enterprise Edition con un grupo de servidores Standard Edition. En realidad, estos tipos de emparejamientos no se admiten.</span><span class="sxs-lookup"><span data-stu-id="befd0-p104">Neither Topology Builder nor topology validation will prohibit pairing two pools in a way that does not follow these recommendations. For example, Topology Builder allows you to pair an Enterprise Edition pool with a Standard Edition pool. However, these types of pairings are not supported.</span></span>

<span data-ttu-id="befd0-117">Cada grupo de un par debe tener la capacidad de ofrecer a todos los usuarios de ambos grupos en caso de que se produzca un desastre.</span><span class="sxs-lookup"><span data-stu-id="befd0-117">Each pool in a pair should have the capacity to serve all users from both pools in the event of a disaster.</span></span>

<span data-ttu-id="befd0-118">Si empareja los grupos de servidores Enterprise Edition, también puede implementar una alta disponibilidad en los servidores back-end, pero para los pares de grupos Standard Edition solo están disponibles las medidas de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="befd0-118">If you pair Enterprise Edition pools, you can also implement high availability on the Back End Servers, but for pairs of Standard Edition pools only the disaster recovery measures are available.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

