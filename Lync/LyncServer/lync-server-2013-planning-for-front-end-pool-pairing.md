---
title: 'Lync Server 2013: Planeación de la emparejamiento de grupos de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 484a19b890602ea338f5e98a126a13582ce7e931
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522197"
---
# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="d3bbe-102">Planeación de la emparejamiento de grupos de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3bbe-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3bbe-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d3bbe-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d3bbe-104">Para las capacidades de recuperación ante desastres más adecuadas en Lync Server 2013, implemente pares de grupos de servidores front-end en dos sitios dispersos geográficamente.</span><span class="sxs-lookup"><span data-stu-id="d3bbe-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="d3bbe-105">Cada sitio contiene un grupo de servidores front-end emparejado con otro grupo correspondiente en el otro sitio.</span><span class="sxs-lookup"><span data-stu-id="d3bbe-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="d3bbe-106">Ambos sitios están activos y el servicio de copia de seguridad de Lync Server proporciona replicación de datos en tiempo real para mantener sincronizados los grupos.</span><span class="sxs-lookup"><span data-stu-id="d3bbe-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="d3bbe-107">El servicio de copia de seguridad es una nueva característica de Lync Server 2013, diseñada para admitir la solución de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="d3bbe-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="d3bbe-108">Se instala en un grupo de servidores front-end cuando se empareja el grupo de servidores con otro grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d3bbe-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="d3bbe-p102">Si el grupo de servidores de un sitio falla, puede realizar una conmutación por error de los usuarios de dicho grupo de servidores al grupo de servidores del otro sitio, que proporcionará servicios a todos los servidores de ambos grupos. Para la planificación de capacidad, cada grupo de servidores debe estar diseñado para gestionar las cargas de trabajo de todos los usuarios de ambos grupos en caso de desastre.</span><span class="sxs-lookup"><span data-stu-id="d3bbe-p102">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools. For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d3bbe-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d3bbe-111">In This Section</span></span>

  - [<span data-ttu-id="d3bbe-112">Opciones de emparejamiento de grupo admitidas y procedimientos recomendados para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3bbe-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="d3bbe-113">Relaciones de registrador de reserva en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3bbe-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="d3bbe-114">Tiempo de recuperación para la conmutación por error del grupo y la conmutación por recuperación del grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3bbe-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="d3bbe-115">Conmutación por error del almacén de administración central en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3bbe-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="d3bbe-116">Seguridad de datos de emparejamiento de grupo de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3bbe-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

