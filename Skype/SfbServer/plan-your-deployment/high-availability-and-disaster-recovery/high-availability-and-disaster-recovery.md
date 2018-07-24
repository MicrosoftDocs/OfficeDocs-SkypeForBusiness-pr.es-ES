---
title: Planeación de alta disponibilidad y recuperación ante desastres en Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype para Business Server proporcione una alta disponibilidad con servidor de agrupación, recuperación ante desastres con el emparejamiento de grupo de servidores y varios modos de alta disponibilidad de servidor Back-End, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y agrupación en clústeres de conmutación por error SQL.
ms.openlocfilehash: 94db95c097fca62e31a01efd1d254ab6d3cd6d37
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20996462"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="7ca6d-103">Planeación de alta disponibilidad y recuperación ante desastres en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7ca6d-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="7ca6d-104">Skype para Business Server proporcione una alta disponibilidad con servidor de agrupación, recuperación ante desastres con el emparejamiento de grupo de servidores y varios modos de alta disponibilidad de servidor Back-End, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y agrupación en clústeres de conmutación por error SQL.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="7ca6d-105">Alta disponibilidad hace referencia a asegurándose de que Skype para servicios de Business Server están disponibles incluso si uno o más servidores deja de funcionar.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="7ca6d-106">La recuperación ante desastres se basa en preservar los servicios en caso de que ocurra un desastre natural o un error humano, intentando resguardar la mayor cantidad de datos que sea posible.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="7ca6d-107">Al igual que en versiones anteriores de Lync Server, la característica principal de alta disponibilidad para la mayoría de roles de servidor de Skype para Business Server es la redundancia de servidor a través de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="7ca6d-108">Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="7ca6d-109">Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="7ca6d-110">Skype para Business Server también proporciona opciones de recuperación de grupos de servidores Front-End de ante desastres.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="7ca6d-111">Puede configurar dos grupos de servidores en distintas áreas geográficas para que funcionen como copias de seguridad entre ellas.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="7ca6d-112">Así pues, si tiene todo un grupo de servidores o un sitio y dejan de funcionar, el grupo de copia de seguridad puede seguir suministrando el servicio a los usuarios en ambos sitios.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="7ca6d-113">Skype para Business Server también admite cuatro modos de alta disponibilidad para los servidores Back-End: SQL la creación de reflejos, grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) AlwaysOn y agrupación en clústeres de conmutación por error SQL.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ca6d-114">La creación de reflejos de SQL está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7ca6d-115">Los métodos de agrupación en clústeres de conmutación por error de grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL son preferidos con Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="7ca6d-116">Grupos de disponibilidad AlwaysOn no son compatibles con servidores de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="7ca6d-117">En esta sección se explican estas características y trata además los pasos que puede tomar en la alta disponibilidad y la recuperación ante desastres para sus otros roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="7ca6d-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7ca6d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ca6d-118">See also</span></span>

[<span data-ttu-id="7ca6d-119">Alta disponibilidad y administración del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="7ca6d-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="7ca6d-120">Front-recuperación de desastres de grupo de servidores de final en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7ca6d-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="7ca6d-121">Experiencia del usuario durante error de grupo de servidores en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7ca6d-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="7ca6d-122">Back-End alta disponibilidad del servidor en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7ca6d-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="7ca6d-123">Archivo de uso compartido de alta disponibilidad en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7ca6d-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)