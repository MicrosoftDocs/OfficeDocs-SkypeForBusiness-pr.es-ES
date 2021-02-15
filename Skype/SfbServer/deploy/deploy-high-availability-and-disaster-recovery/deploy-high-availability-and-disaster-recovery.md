---
title: Implementar la alta disponibilidad y la recuperación ante desastres
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype Empresarial Server ofrece alta disponibilidad con agrupación de servidores, recuperación ante desastres con emparejamiento de grupos de servidores y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de la base de datos y los clústeres de conmutación por error SQL servidor.
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830620"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="c6d8a-103">Implementar la alta disponibilidad y la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="c6d8a-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="c6d8a-104">Skype Empresarial Server ofrece alta disponibilidad con agrupación de servidores, recuperación ante desastres con emparejamiento de grupos de servidores y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de la base de datos y los clústeres de conmutación por error SQL servidor.</span><span class="sxs-lookup"><span data-stu-id="c6d8a-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="c6d8a-105">La alta disponibilidad hace referencia a asegurarse de que los servicios de Skype Empresarial Server estén disponibles incluso si uno o más servidores no están disponibles. La recuperación ante desastres se refiere a mantener los servicios en caso de desastre natural o humano y conservar tantos datos de antes del desastre como sea posible.</span><span class="sxs-lookup"><span data-stu-id="c6d8a-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="c6d8a-106">En esta sección se explica cómo implementar estas características y también se tratan los pasos que puede seguir para la alta disponibilidad y la recuperación ante desastres para algunos de los otros roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="c6d8a-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="c6d8a-107">SQL mirroring está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6d8a-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c6d8a-108">Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn y SQL de clústeres de conmutación por error son preferidos con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6d8a-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="c6d8a-109">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c6d8a-109">Related sections</span></span>

[<span data-ttu-id="c6d8a-110">Planear la alta disponibilidad y la recuperación ante desastres en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c6d8a-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="c6d8a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6d8a-111">See also</span></span>

[<span data-ttu-id="c6d8a-112">Implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c6d8a-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="c6d8a-113">Implementar grupos de servidores front-end emparejados para la recuperación ante desastres en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c6d8a-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="c6d8a-114">Implementar SQL creación de reflejos para la alta disponibilidad del servidor back-end en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="c6d8a-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
