---
title: Migración de varios sitios y grupos de servidores
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype para Business Server 2019 es compatible con las implementaciones de varios sitios y grupo de varios servidores. El proceso de migración de varios grupos de servidores a Skype para Business Server 2019 requiere las siguientes consideraciones:'
ms.openlocfilehash: 9716df65acfde26c41001bbc252b746ea1bd5241
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028750"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="ae9c0-104">Migración de varios sitios y grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="ae9c0-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="ae9c0-105">Skype para Business Server 2019 es compatible con las implementaciones de varios sitios y grupo de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="ae9c0-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="ae9c0-106">El proceso de migración de varios grupos de servidores a Skype para Business Server 2019 requiere las siguientes consideraciones:</span><span class="sxs-lookup"><span data-stu-id="ae9c0-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="ae9c0-107">Después de implementar un Skype para Business Server 2019 el grupo piloto, debe definir un subconjunto de usuarios pilotos que se moverán a la Skype una metodología para validar la funcionalidad de los usuarios y de grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ae9c0-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="ae9c0-108">Por ejemplo, después de mover un usuario al grupo piloto, compruebe que la directiva del usuario conferencia ha movido a Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ae9c0-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="ae9c0-109">Después de implementar un servidor perimetral en el grupo piloto, debe comprobar que los usuarios externos pueden comunicarse con el Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ae9c0-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="ae9c0-110">Chat en grupo, la creación de reflejos de SQL y la funcionalidad XMPP están en desuso en Skype para Business Server 2019 y ya no están disponibles como Skype para las características de Business Server 2019, pero puede continuar en un entorno de coexistencia si anteriormente se implementan en un entorno heredado.</span><span class="sxs-lookup"><span data-stu-id="ae9c0-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="ae9c0-111">Si desea seguir utilizando estas características, debe planear continuar con un entorno de coexistencia, donde permanecerá determinados usuarios en grupos de servidores heredados.</span><span class="sxs-lookup"><span data-stu-id="ae9c0-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="ae9c0-112">Después de trasladar los servidores perimetrales de las rutas federadas para el piloto Skype para los servidores perimetrales de Business Server 2019, debe comprobar que los usuarios federados pueden comunicarse con el Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ae9c0-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="ae9c0-113">Después de mover todos los usuarios y objetos de contacto que no sean usuarios, deberá validar que el grupo heredado está vacío.</span><span class="sxs-lookup"><span data-stu-id="ae9c0-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="ae9c0-114">Después de comprobar que el grupo heredado está vacío, a continuación, puede desactivar el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ae9c0-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="ae9c0-115">Para obtener información detallada acerca de cómo desactivar los servidores y el grupo de servidores heredado heredado, vea [fase 8: retirar grupos heredados](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="ae9c0-115">For details about how to deactivate the legacy legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

