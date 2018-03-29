---
title: Planificación de la alta disponibilidad y de la recuperación ante desastres en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/29/2018
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype para Business Server ofrece alta disponibilidad con agrupación, recuperación ante desastres con grupo de emparejamiento y varios modos de alta disponibilidad del servidor de extremo atrás, incluidos grupos de disponibilidad AlwaysOn, creación de reflejos de base de datos y organización por clústeres de conmutación por error SQL del servidor.
ms.openlocfilehash: e2e433112146e3be771abb12ef50e09749e8e325
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server-2015"></a><span data-ttu-id="4c991-103">Planificación de la alta disponibilidad y de la recuperación ante desastres en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4c991-103">Plan for high availability and disaster recovery in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4c991-104">Skype para Business Server ofrece alta disponibilidad con agrupación, recuperación ante desastres con grupo de emparejamiento y varios modos de alta disponibilidad del servidor de extremo atrás, incluidos grupos de disponibilidad AlwaysOn, creación de reflejos de base de datos y organización por clústeres de conmutación por error SQL del servidor.</span><span class="sxs-lookup"><span data-stu-id="4c991-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="4c991-105">Alta disponibilidad se refiere a asegurarse de que Skype para servicios Business Server están disponibles incluso si uno o más servidores deja de funcionar.</span><span class="sxs-lookup"><span data-stu-id="4c991-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="4c991-106">La recuperación ante desastres se basa en preservar los servicios en caso de que ocurra un desastre natural o un error humano, intentando resguardar la mayor cantidad de datos que sea posible.</span><span class="sxs-lookup"><span data-stu-id="4c991-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="4c991-107">Como en versiones anteriores de Lync Server, la característica principal de alta disponibilidad para la mayoría de funciones de servidor en Skype para Business Server es la redundancia de servidor a través de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="4c991-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="4c991-108">Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor.</span><span class="sxs-lookup"><span data-stu-id="4c991-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="4c991-109">Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.</span><span class="sxs-lookup"><span data-stu-id="4c991-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="4c991-110">Skype para Business Server también proporciona opciones de recuperación de grupos de Front-End de desastres.</span><span class="sxs-lookup"><span data-stu-id="4c991-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="4c991-111">Puede configurar dos grupos de servidores en distintas áreas geográficas para que funcionen como copias de seguridad entre ellas.</span><span class="sxs-lookup"><span data-stu-id="4c991-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="4c991-112">Así pues, si tiene todo un grupo de servidores o un sitio y dejan de funcionar, el grupo de copia de seguridad puede seguir suministrando el servicio a los usuarios en ambos sitios.</span><span class="sxs-lookup"><span data-stu-id="4c991-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="4c991-113">Skype para Business Server también admite cuatro modos de alta disponibilidad para los servidores de fondo atrás: la creación de reflejo de base de datos, grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error AlwaysOn (FCI) y organización por clústeres de conmutación por error SQL.</span><span class="sxs-lookup"><span data-stu-id="4c991-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: database mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c991-114">No se admiten grupos de disponibilidad AlwaysOn con servidores de charla persistente.</span><span class="sxs-lookup"><span data-stu-id="4c991-114">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="4c991-115">En esta sección se explican estas características y trata además los pasos que puede tomar en la alta disponibilidad y la recuperación ante desastres para sus otros roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="4c991-115">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4c991-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c991-116">See also</span></span>

#### 

[<span data-ttu-id="4c991-117">Administración y frontal grupo de servidores de alta disponibilidad</span><span class="sxs-lookup"><span data-stu-id="4c991-117">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="4c991-118">Frontal de recuperación de desastres de grupo final en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4c991-118">Front End pool disaster recovery in Skype for Business Server 2015</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="4c991-119">Experiencia del usuario durante la falla de grupo en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4c991-119">User experience during pool failure in Skype for Business Server 2015</span></span>](user-experience.md)
  
[<span data-ttu-id="4c991-120">Back End alta disponibilidad del servidor en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4c991-120">Back End Server high availability in Skype for Business Server 2015</span></span>](back-end-server.md)
  
[<span data-ttu-id="4c991-121">Compartimiento de archivos alta disponibilidad en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4c991-121">File sharing high availability in Skype for Business Server 2015</span></span>](file-sharing.md)

