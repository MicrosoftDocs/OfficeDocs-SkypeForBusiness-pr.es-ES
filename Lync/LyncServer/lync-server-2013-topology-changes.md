---
title: 'Lync Server 2013: Cambios en la topología'
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
ms.openlocfilehash: c4453a9b5b8a5fcd60eaad1e437fd4800caddfba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="dd071-102">Cambios en la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd071-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd071-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="dd071-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="dd071-104">Los requisitos de topología y las consideraciones para Lync Server 2013 son diferentes de los de las versiones anteriores, tal y como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="dd071-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="dd071-105">Nueva arquitectura de pools front end</span><span class="sxs-lookup"><span data-stu-id="dd071-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="dd071-106">En Lync Server 2013, la arquitectura de los grupos de aplicaciones para el usuario de Enterprise Edition ha cambiado a una arquitectura de sistemas distribuidos.</span><span class="sxs-lookup"><span data-stu-id="dd071-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="dd071-107">Con esta nueva arquitectura, la base de datos back-end ya no es el almacén de datos en tiempo real en un grupo.</span><span class="sxs-lookup"><span data-stu-id="dd071-107">With this new architecture, the Back End database is no longer the real-time data store in a pool.</span></span> <span data-ttu-id="dd071-108">La información sobre un usuario en particular se mantiene en tres servidores front-end en el grupo.</span><span class="sxs-lookup"><span data-stu-id="dd071-108">Information about a particular user is kept on three Front End Servers in the pool.</span></span> <span data-ttu-id="dd071-109">Para cada usuario, un servidor front-end actúa como el maestro para la información del usuario y otros dos servidores front-end actúan como réplicas.</span><span class="sxs-lookup"><span data-stu-id="dd071-109">For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas.</span></span> <span data-ttu-id="dd071-110">Si un servidor front-end deja de funcionar, otro servidor front-end que sirve como réplica se promueve automáticamente a Master.</span><span class="sxs-lookup"><span data-stu-id="dd071-110">If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="dd071-111">Esto sucede en segundo plano y los administradores no necesitan saber qué servidores front-end son los patrones para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="dd071-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="dd071-112">Esta distribución de almacenamiento de datos mejora el rendimiento y la escalabilidad dentro del grupo y elimina el punto único de falla de un único servidor de servicios de fondo.</span><span class="sxs-lookup"><span data-stu-id="dd071-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="dd071-113">El servidor back-end sirve como almacenamiento de copia de seguridad de datos de usuarios y de conferencia, y también el almacenamiento principal de otras bases de datos, como la base de datos de grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="dd071-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="dd071-114">Estas mejoras también significan que hay cambios en la forma en que se planean y mantienen los grupos.</span><span class="sxs-lookup"><span data-stu-id="dd071-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="dd071-115">Le recomendamos que todos los grupos de aplicaciones para el usuario de Enterprise Edition incluyan al menos tres servidores front-end, para proporcionar el número completo de réplicas para las que está diseñada la arquitectura del grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dd071-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="dd071-116">Además, debe seguir ciertos procedimientos al agregar servidores a un grupo de servidores front-end, quitar servidores de él o actualizar servidores.</span><span class="sxs-lookup"><span data-stu-id="dd071-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="dd071-117">Para obtener más información, vea [topologías y componentes para servidores front-end, mensajería instantánea y presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="dd071-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="dd071-118">Cambios en la topología de roles del servidor</span><span class="sxs-lookup"><span data-stu-id="dd071-118">Server Role Topology Changes</span></span>

<span data-ttu-id="dd071-119">Algunos roles de servidor que se ejecutaban previamente en servidores independientes se consolidan ahora en el rol de servidor front-end, lo que le permite ahorrar en costos de hardware</span><span class="sxs-lookup"><span data-stu-id="dd071-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="dd071-120">En Lync Server 2013, el servidor de conferencia A/V siempre se encuentra en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="dd071-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="dd071-121">Los front-ends para la supervisión y el archivado ahora se colocan siempre con el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="dd071-121">The front ends for both Monitoring and Archiving are now always collocated with Front End Server.</span></span> <span data-ttu-id="dd071-122">La supervisión y el archivado de cada uno aún requieren una base de datos back-end separada, que se puede colocar en el mismo servidor que la base de datos back-end del grupo de aplicaciones para el usuario o puede alojarse en servidores back-end independientes.</span><span class="sxs-lookup"><span data-stu-id="dd071-122">Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="dd071-123">El servidor de chat persistente es ahora un rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="dd071-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="dd071-124">En Microsoft Lync Server 2010, el servidor de chats grupales era una aplicación de confianza de terceros para Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="dd071-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="dd071-125">En Lync Server 2013, la funcionalidad del servidor de chat persistente se implementa con tres nuevos roles de servidor:</span><span class="sxs-lookup"><span data-stu-id="dd071-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="dd071-126">**PersistentChatService:** Servicios principales del servidor de chat persistente implementados como un rol front-end</span><span class="sxs-lookup"><span data-stu-id="dd071-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="dd071-127">**PersistentChatStore:** Función back-end del servidor</span><span class="sxs-lookup"><span data-stu-id="dd071-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="dd071-128">**PersistentChatComplianceStore:** Rol de servidor back end para cumplimiento de las conversaciones persistentes</span><span class="sxs-lookup"><span data-stu-id="dd071-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

