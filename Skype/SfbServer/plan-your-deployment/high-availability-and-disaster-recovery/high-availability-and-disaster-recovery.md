---
title: Planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype empresarial Server ofrece alta disponibilidad con la agrupación de servidores, la recuperación ante desastres con emparejamiento de bloque y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y el clúster de conmutación por error de SQL.
ms.openlocfilehash: 521ddaa9878ba660e509f248d2f2ffb944608d87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815928"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="c61b9-103">Planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c61b9-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="c61b9-104">Skype empresarial Server ofrece alta disponibilidad con la agrupación de servidores, la recuperación ante desastres con emparejamiento de bloque y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y el clúster de conmutación por error de SQL.</span><span class="sxs-lookup"><span data-stu-id="c61b9-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="c61b9-105">La alta disponibilidad se refiere a asegurarse de que los servicios de Skype empresarial Server estén disponibles incluso si uno o más servidores están desactivados.</span><span class="sxs-lookup"><span data-stu-id="c61b9-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="c61b9-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span><span class="sxs-lookup"><span data-stu-id="c61b9-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="c61b9-107">Como en las versiones anteriores de Lync Server, la característica de alta disponibilidad principal para la mayoría de los roles de servidor de Skype empresarial Server es la redundancia de servidores a través de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="c61b9-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="c61b9-108">Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor.</span><span class="sxs-lookup"><span data-stu-id="c61b9-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="c61b9-109">Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.</span><span class="sxs-lookup"><span data-stu-id="c61b9-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="c61b9-110">Skype empresarial Server también proporciona opciones de recuperación ante desastres para las agrupaciones front end.</span><span class="sxs-lookup"><span data-stu-id="c61b9-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="c61b9-111">Puede configurar dos grupos de servidores en distintas áreas geográficas para que funcionen como copias de seguridad entre ellas.</span><span class="sxs-lookup"><span data-stu-id="c61b9-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="c61b9-112">Así pues, si tiene todo un grupo de servidores o un sitio y dejan de funcionar, el grupo de copia de seguridad puede seguir suministrando el servicio a los usuarios en ambos sitios.</span><span class="sxs-lookup"><span data-stu-id="c61b9-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="c61b9-113">Skype empresarial Server también admite cuatro modos de alta disponibilidad para los servidores back-end: SQL Mirroring, grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) siempre y clústeres de conmutación por error de SQL.</span><span class="sxs-lookup"><span data-stu-id="c61b9-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c61b9-114">La creación de reflejos de SQL está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c61b9-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c61b9-115">Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn, y los métodos de clúster de conmutación por error de SQL son preferidos con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c61b9-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="c61b9-116">Los grupos de disponibilidad AlwaysOn no son compatibles con los servidores de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="c61b9-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="c61b9-117">En esta sección se explican estas características y trata además los pasos que puede tomar en la alta disponibilidad y la recuperación ante desastres para sus otros roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="c61b9-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c61b9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c61b9-118">See also</span></span>

[<span data-ttu-id="c61b9-119">Alta disponibilidad y administración del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="c61b9-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="c61b9-120">Recuperación ante desastres del grupo de servidores front-end en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c61b9-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="c61b9-121">Experiencia de usuario durante la falla de un grupo de servidores de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="c61b9-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="c61b9-122">Servidor back-end de alta disponibilidad en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c61b9-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="c61b9-123">Alta disponibilidad del uso compartido de archivos en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c61b9-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
