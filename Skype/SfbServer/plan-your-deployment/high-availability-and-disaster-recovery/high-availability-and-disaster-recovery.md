---
title: Planear la alta disponibilidad y la recuperación ante desastres en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype Empresarial Server ofrece alta disponibilidad con agrupación de servidores, recuperación ante desastres con emparejamiento de grupos de servidores y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de la base de datos y los clústeres de conmutación por error SQL servidor.
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802820"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="925fe-103">Planear la alta disponibilidad y la recuperación ante desastres en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="925fe-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="925fe-104">Skype Empresarial Server ofrece alta disponibilidad con agrupación de servidores, recuperación ante desastres con emparejamiento de grupos de servidores y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de la base de datos y los clústeres de conmutación por error SQL servidor.</span><span class="sxs-lookup"><span data-stu-id="925fe-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="925fe-105">La alta disponibilidad hace referencia a asegurarse de que los servicios de Skype Empresarial Server están disponibles incluso si uno o más servidores no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="925fe-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="925fe-106">La recuperación ante desastres se refiere a mantener los servicios en el caso de un desastre natural o causado por personas, y conservar tantos datos de antes del desastre como sea posible.</span><span class="sxs-lookup"><span data-stu-id="925fe-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="925fe-107">Al igual que en versiones anteriores de Lync Server, la principal característica de alta disponibilidad para la mayoría de los roles de servidor en Skype Empresarial Server es la redundancia de servidores mediante agrupación.</span><span class="sxs-lookup"><span data-stu-id="925fe-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="925fe-108">Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.</span><span class="sxs-lookup"><span data-stu-id="925fe-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="925fe-109">Esto se aplica a los servidores front-end, los servidores perimetrales, los servidores de mediación y los directores.</span><span class="sxs-lookup"><span data-stu-id="925fe-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="925fe-110">Skype Empresarial Server también proporciona opciones de recuperación ante desastres para grupos de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="925fe-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="925fe-111">Puede configurar dos grupos de servidores en diferentes áreas geográficas para que sirvan como copias de seguridad entre sí.</span><span class="sxs-lookup"><span data-stu-id="925fe-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="925fe-112">A continuación, si tiene un grupo de servidores o un sitio completo, el grupo de copia de seguridad puede seguir brindando servicio a los usuarios de ambos sitios.</span><span class="sxs-lookup"><span data-stu-id="925fe-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="925fe-113">Skype Empresarial Server también admite cuatro modos de alta disponibilidad para los servidores back-end: creación de reflejos de SQL, grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) AlwaysOn y clústeres de conmutación SQL conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="925fe-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="925fe-114">SQL mirroring está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="925fe-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="925fe-115">Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL de clústeres de conmutación por error son preferidos con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="925fe-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="925fe-116">Los grupos de disponibilidad AlwaysOn no son compatibles con los servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="925fe-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="925fe-117">En esta sección se explican estas características y también se explican los pasos que puede seguir para la alta disponibilidad y la recuperación ante desastres para algunos de los otros roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="925fe-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="925fe-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="925fe-118">See also</span></span>

[<span data-ttu-id="925fe-119">Alta disponibilidad y administración del grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="925fe-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="925fe-120">Recuperación ante desastres del grupo de servidores front-end en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="925fe-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="925fe-121">Experiencia del usuario durante el error del grupo en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="925fe-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="925fe-122">Alta disponibilidad del servidor back-end en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="925fe-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="925fe-123">Alta disponibilidad de uso compartido de archivos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="925fe-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
