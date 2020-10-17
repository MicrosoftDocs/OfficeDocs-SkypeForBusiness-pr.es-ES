---
title: Lync Server 2013 topologías de cambios
description: Lync Server 2013 la topología de cambios.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 562766eae939e4510a0d3af20e40b4731c361040
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549106"
---
# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="a9a4b-103">Cambios en la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9a4b-103">Topology changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9a4b-104">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a9a4b-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a9a4b-105">Los requisitos y consideraciones de la topología para Lync Server 2013 son diferentes de los de versiones anteriores, como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-105">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="a9a4b-106">Nueva arquitectura para grupos de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="a9a4b-106">New Front End Pools Architecture</span></span>

<span data-ttu-id="a9a4b-107">En Lync Server 2013, la arquitectura de los grupos de servidores front-end Enterprise Edition ha cambiado a una arquitectura de sistemas distribuidos.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-107">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="a9a4b-p101">Con esta nueva arquitectura, base de datos back-end ya no es el almacén de datos en tiempo real de un grupo de servidores. La información sobre un usuario en particular se guarda en tres servidores front-end del grupo. Para cada usuario habrá un servidor front-end que actuará como servidor de información principal y otros dos servidores front-end que actuarán como réplicas. Si uno de los servidores front-end deja de funcionar, se ascenderá automáticamente al rol de principal a otro de los dos servidores que sirven de réplica.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-p101">With this new architecture, the Back End database is no longer the real-time data store in a pool. Information about a particular user is kept on three Front End Servers in the pool. For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas. If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="a9a4b-112">Esto ocurre en segundo plano y los administradores no necesitan saber qué servidores front-end son los principales para qué usuarios.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-112">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="a9a4b-113">Esta distribución del almacenamiento de datos mejora el rendimiento y la escalabilidad en el grupo, y elimina el único punto de error de un único servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-113">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="a9a4b-114">El servidor back-end se utiliza como almacén de copias de seguridad para datos de usuarios y conferencias y es también el almacén principal para otras bases de datos como la de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-114">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="a9a4b-115">Estas mejoras significan, además, que cambia la forma de planear y mantener los grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-115">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="a9a4b-116">Se recomienda que todos los grupos de servidores front-end Enterprise Edition incluyan al menos tres servidores front-end para proporcionar el número completo de réplicas para las que está diseñada la arquitectura de grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-116">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="a9a4b-117">Además, debe seguir determinados procedimientos al agregar servidores a un grupo de servidores front-end, quitar servidores de él o actualizar servidores.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-117">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="a9a4b-118">Para obtener más información, vea [topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="a9a4b-118">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="a9a4b-119">Cambios en la topología de roles de servidor</span><span class="sxs-lookup"><span data-stu-id="a9a4b-119">Server Role Topology Changes</span></span>

<span data-ttu-id="a9a4b-120">Algunos roles de servidor que anteriormente se ejecutaban en servidores aparte se han consolidado en el rol de servidor front-end y esto permite ahorrar en costes de hardware.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-120">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="a9a4b-121">En Lync Server 2013, el servidor de conferencia A/V siempre se combina con el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-121">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="a9a4b-p104">Ahora, los front-end de Supervisión y Archivado se instalan siempre con el servidor front-end. Supervisión y Archivado siguen necesitando cada uno una base de datos back-end independiente, que puede instalarse en el mismo servidor que la base de datos back-end del grupo de servidores front-end o bien puede hospedarse en servidores back-end aparte.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-p104">The front ends for both Monitoring and Archiving are now always collocated with Front End Server. Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="a9a4b-124">El servidor de chat persistente ahora es un rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-124">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="a9a4b-125">En Microsoft Lync Server 2010, el servidor de chat en grupo era una aplicación de confianza de terceros para Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a9a4b-125">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="a9a4b-126">En Lync Server 2013, la funcionalidad del servidor de chat persistente se implementa con tres nuevos roles de servidor:</span><span class="sxs-lookup"><span data-stu-id="a9a4b-126">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="a9a4b-127">**PersistentChatService:** Servicios principales del servidor de chat persistente implementados como rol front-end</span><span class="sxs-lookup"><span data-stu-id="a9a4b-127">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="a9a4b-128">**PersistentChatStore:** Rol de servidor back-end</span><span class="sxs-lookup"><span data-stu-id="a9a4b-128">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="a9a4b-129">**PersistentChatComplianceStore:** Rol de servidor back-end para el cumplimiento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a9a4b-129">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

