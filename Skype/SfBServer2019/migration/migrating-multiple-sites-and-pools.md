---
title: Migrar múltiples sitios y grupos de servidores
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype empresarial Server 2019 admite implementaciones de varios sitios y de varios grupos. El proceso de migración de varios grupos a Skype empresarial Server 2019 requiere las siguientes consideraciones:'
ms.openlocfilehash: d1257590c431bc15aad4db03908aa6d95fd5fce3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813448"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="5dafc-104">Migrar múltiples sitios y grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="5dafc-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="5dafc-105">Skype empresarial Server 2019 admite implementaciones de varios sitios y de varios grupos.</span><span class="sxs-lookup"><span data-stu-id="5dafc-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="5dafc-106">El proceso de migración de varios grupos a Skype empresarial Server 2019 requiere las siguientes consideraciones:</span><span class="sxs-lookup"><span data-stu-id="5dafc-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="5dafc-107">Después de implementar un grupo piloto de Skype empresarial Server 2019, debe definir un subconjunto de usuarios piloto que se moverá al grupo de Skype empresarial Server 2019 y una metodología para validar la funcionalidad de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5dafc-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="5dafc-108">Por ejemplo, después de mover un usuario a la agrupación piloto, compruebe que la Directiva de conferencia del usuario se ha movido a Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5dafc-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="5dafc-109">Después de implementar un servidor perimetral en la agrupación piloto, debe validar que los usuarios externos puedan comunicarse con el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="5dafc-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="5dafc-110">Las funcionalidades chat persistente, reflejo SQL y XMPP han quedado obsoletas en Skype empresarial Server 2019 y ya no están disponibles como características de Skype empresarial Server 2019, pero se pueden continuar en un entorno de coexistencia si se han implementado previamente en un entorno heredado.</span><span class="sxs-lookup"><span data-stu-id="5dafc-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="5dafc-111">Si desea seguir usando estas características, debe planear la continuación de un entorno de coexistencia en el que determinados usuarios permanecerán en agrupaciones heredadas.</span><span class="sxs-lookup"><span data-stu-id="5dafc-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="5dafc-112">Después de realizar la transición de los servidores perimetrales de las rutas federadas a los servidores perimetrales de Skype empresarial Server 2019, debe validar que los usuarios federados puedan comunicarse con el grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="5dafc-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="5dafc-113">Después de mover todos los usuarios y los objetos de contacto que no son de usuario, debe validar que el grupo heredado esté vacío.</span><span class="sxs-lookup"><span data-stu-id="5dafc-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="5dafc-114">Después de verificar que el grupo heredado está vacío, puede desactivar el grupo.</span><span class="sxs-lookup"><span data-stu-id="5dafc-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="5dafc-115">Para obtener más información sobre cómo desactivar el grupo de servidores y los servidores heredados, consulte [Phase 8: retiro pools heredados](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="5dafc-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

