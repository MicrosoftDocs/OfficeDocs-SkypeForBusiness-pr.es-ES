---
title: Implementar la alta disponibilidad y la recuperación ante desastres
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype empresarial Server ofrece alta disponibilidad con la agrupación de servidores, la recuperación ante desastres con emparejamiento de bloque y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y el clúster de conmutación por error de SQL.
ms.openlocfilehash: 68c6a12f80ac2d915c678f69146d0001daedbe5c
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790128"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="db070-103">Implementar la alta disponibilidad y la recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="db070-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="db070-104">Skype empresarial Server ofrece alta disponibilidad con la agrupación de servidores, la recuperación ante desastres con emparejamiento de bloque y varios modos de alta disponibilidad del servidor back-end, incluidos los grupos de disponibilidad AlwaysOn, la creación de reflejo de base de datos y el clúster de conmutación por error de SQL.</span><span class="sxs-lookup"><span data-stu-id="db070-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="db070-105">La alta disponibilidad se refiere a asegurarse de que los servicios de Skype empresarial Server estén disponibles incluso si uno o más servidores están desactivados. La recuperación ante desastres hace referencia a mantener los servicios en caso de que se produzca un desastre natural o humano, y preservar la mayor cantidad de información posible antes del desastre.</span><span class="sxs-lookup"><span data-stu-id="db070-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="db070-106">En esta sección se explica cómo implementar estas características y también se describen los pasos que puede seguir en la alta disponibilidad y la recuperación ante desastres para sus otros roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="db070-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="db070-107">La creación de reflejos de SQL está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="db070-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="db070-108">Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error (FCI) AlwaysOn, y los métodos de clúster de conmutación por error de SQL son preferidos con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="db070-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="db070-109">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="db070-109">Related sections</span></span>

[<span data-ttu-id="db070-110">Planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="db070-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="db070-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="db070-111">See also</span></span>

[<span data-ttu-id="db070-112">Implementar un grupo de disponibilidad AlwaysOn en un servidor back-end en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="db070-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="db070-113">Implementar grupos front-end emparejados para recuperación ante desastres en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="db070-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="db070-114">Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="db070-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
