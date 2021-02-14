---
title: Migrar múltiples sitios y grupos de servidores
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype Empresarial Server 2019 admite implementaciones de varios sitios y de varios servidores. El proceso de migración de varios grupos a Skype Empresarial Server 2019 requiere las siguientes consideraciones:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752662"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="72cb7-104">Migrar múltiples sitios y grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="72cb7-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="72cb7-105">Skype Empresarial Server 2019 admite implementaciones de varios sitios y de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="72cb7-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="72cb7-106">El proceso de migración de varios grupos a Skype Empresarial Server 2019 requiere las siguientes consideraciones:</span><span class="sxs-lookup"><span data-stu-id="72cb7-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="72cb7-107">Después de implementar un grupo piloto de Skype Empresarial Server 2019, debe definir un subconjunto de usuarios piloto que se trasladarán al grupo de Skype Empresarial Server 2019 y una metodología para validar la funcionalidad de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="72cb7-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="72cb7-108">Por ejemplo, después de mover un usuario al grupo piloto, compruebe que la directiva de conferencia del usuario se ha movido a Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="72cb7-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="72cb7-109">Después de implementar un servidor perimetral en el grupo piloto, debe validar que los usuarios externos puedan comunicarse con el grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="72cb7-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="72cb7-110">Las funciones de chat persistente, creación de reflejo de SQL y XMPP están en desuso en Skype Empresarial Server 2019 y ya no están disponibles como características de Skype Empresarial Server 2019, pero pueden continuar en un entorno de coexistencia si se implementaron anteriormente en un entorno heredado.</span><span class="sxs-lookup"><span data-stu-id="72cb7-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="72cb7-111">Si desea seguir usando estas características, debe planear continuar con un entorno de coexistencia en el que determinados usuarios permanecerán en grupos heredados.</span><span class="sxs-lookup"><span data-stu-id="72cb7-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="72cb7-112">Después de realizar la transición de los servidores perimetrales de las rutas federadas a los servidores perimetrales piloto de Skype Empresarial Server 2019, debe validar que los usuarios federados puedan comunicarse con el grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="72cb7-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="72cb7-113">Después de mover todos los usuarios y objetos de contacto que no son de usuario, debe validar que el grupo heredado está vacío.</span><span class="sxs-lookup"><span data-stu-id="72cb7-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="72cb7-114">Después de comprobar que el grupo heredado está vacío, puede desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="72cb7-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="72cb7-115">Para obtener más información acerca de cómo desactivar el grupo heredado y los servidores, consulte [Fase 8: Retirar grupos heredados.](phase-8-decommission-legacy-pools.md)</span><span class="sxs-lookup"><span data-stu-id="72cb7-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

