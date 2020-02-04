---
title: 'Lync Server 2013: Planear la combinación de grupos de servidores front-end'
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
ms.openlocfilehash: d85f6e19f3aa74c09a522e737d1223095f17d7c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="d642a-102">Planear la combinación de grupos de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d642a-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d642a-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d642a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d642a-104">Para obtener las mejores capacidades de recuperación ante desastres de Lync Server 2013, implemente pares de grupos de servidores front-end en dos sitios dispersos geográficamente.</span><span class="sxs-lookup"><span data-stu-id="d642a-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="d642a-105">Cada sitio contiene un grupo front-end en el que se empareja una agrupación frontal correspondiente en el otro sitio.</span><span class="sxs-lookup"><span data-stu-id="d642a-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="d642a-106">Ambos sitios están activos y el servicio de copia de seguridad de Lync Server proporciona replicación de datos en tiempo real para mantener las agrupaciones sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="d642a-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="d642a-107">El servicio de copia de seguridad es una característica nueva de Lync Server 2013, diseñada para admitir la solución de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="d642a-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="d642a-108">Se instala en un grupo de servidores front-end cuando se empareja el grupo con otro grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d642a-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="d642a-109">Si se produce un error en el grupo de un sitio, puede realizar la conmutación por error a los usuarios de ese grupo en la agrupación del otro sitio, que proporciona servicios a todos los usuarios de ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="d642a-109">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="d642a-110">Para fines de planeación de capacidad, cada grupo debe estar diseñado para controlar las cargas de trabajo de todos los usuarios en ambos grupos en caso de que se produzca un desastre.</span><span class="sxs-lookup"><span data-stu-id="d642a-110">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d642a-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d642a-111">In This Section</span></span>

  - [<span data-ttu-id="d642a-112">Opciones de emparejamiento de bloque y procedimientos recomendados para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d642a-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="d642a-113">Relaciones del registrador de copia de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d642a-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="d642a-114">Tiempo de recuperación para la conmutación por error y por recuperación del grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d642a-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="d642a-115">Conmutación por error del almacén de administración central en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d642a-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="d642a-116">Seguridad de datos en el emparejamiento de grupos de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d642a-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

