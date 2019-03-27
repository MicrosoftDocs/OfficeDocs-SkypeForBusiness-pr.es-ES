---
title: Implementar la alta disponibilidad y la recuperación ante desastres
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype para Business Server proporcione una alta disponibilidad con servidor de agrupación, recuperación ante desastres con el emparejamiento de grupo de servidores y varios modos de alta disponibilidad de servidor Back-End, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y agrupación en clústeres de conmutación por error SQL.
ms.openlocfilehash: bbd3c4092962e757a7565f1da054c82438a79ded
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876778"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="a8009-103">Implementar la alta disponibilidad y la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="a8009-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="a8009-104">Skype para Business Server proporcione una alta disponibilidad con servidor de agrupación, recuperación ante desastres con el emparejamiento de grupo de servidores y varios modos de alta disponibilidad de servidor Back-End, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y agrupación en clústeres de conmutación por error SQL.</span><span class="sxs-lookup"><span data-stu-id="a8009-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="a8009-105">Alta disponibilidad hace referencia a asegurándose de que Skype para servicios de Business Server están disponibles incluso si uno o más servidores deja de funcionar. Recuperación ante desastres hace referencia a mantener los servicios desplazándose en caso de desastre natural o causado por humanos y conservar la mayor cantidad de datos de antes del desastre como sea posible.</span><span class="sxs-lookup"><span data-stu-id="a8009-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="a8009-106">En esta sección se explica cómo implementar estas características y también se describen los pasos que puede seguir en la alta disponibilidad y la recuperación ante desastres para sus otros roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="a8009-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="a8009-107">La creación de reflejos de SQL está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8009-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a8009-108">Los métodos de agrupación en clústeres de conmutación por error de grupos de disponibilidad AlwaysOn, instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL son preferidos con Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8009-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="a8009-109">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a8009-109">Related sections</span></span>

[<span data-ttu-id="a8009-110">Planeación de alta disponibilidad y recuperación ante desastres en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="a8009-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="a8009-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8009-111">See also</span></span>

[<span data-ttu-id="a8009-112">Implementar un grupo de disponibilidad AlwaysOn en un servidor Back-End de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="a8009-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="a8009-113">Implementación de grupos de servidores Front-End emparejados para la recuperación ante desastres en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="a8009-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="a8009-114">Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a8009-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
