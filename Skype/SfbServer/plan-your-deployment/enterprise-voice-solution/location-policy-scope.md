---
title: Asignar el ámbito de directiva de ubicación en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planear las directivas de ubicación para una implementación de E9-1-1 en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 0c39d0f464b7cde9521dbb69043411b964f74858
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892220"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="42912-103">Asignar el ámbito de directiva de ubicación en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="42912-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="42912-104">Planear las directivas de ubicación para una implementación de E9-1-1 en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="42912-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="42912-105">Como con otro Skype para las directivas de servidor empresarial, se pueden asignar directivas de ubicación en varios niveles de ámbito: global, sitio y usuario.</span><span class="sxs-lookup"><span data-stu-id="42912-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="42912-106">Sin embargo, el ámbito de las directivas de ubicación de nivel de usuario comporta un poco diferente a con otro Skype para las directivas de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="42912-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="42912-107">No sólo se pueden aplicar las directivas de ubicación por usuario a objetos de extremo (por ejemplo, los usuarios y objetos de contacto de teléfono de área común), también se pueden aplicar a Skype Business Server sitios de red.</span><span class="sxs-lookup"><span data-stu-id="42912-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="42912-108">Los sitios de red son agrupaciones de subredes de clientes asociadas con una ubicación geográfica (pero no es necesario que sean todas las subredes de un sitio central o de un sitio de sucursal completo).</span><span class="sxs-lookup"><span data-stu-id="42912-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="42912-109">Los clientes conectados a las subredes de un sitio de red escogen automáticamente la directiva de ubicación asignada a dicho sitio de red.</span><span class="sxs-lookup"><span data-stu-id="42912-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="42912-110">Si la directiva de ubicación de usuario se asigna tanto a un usuario como a un sitio de red, la directiva de ubicación basada en el sitio de red sustituye a cualquier otra configuración de directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="42912-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="42912-111">Cada sitio de red tiene una directiva de ubicación asignada y cada directiva tendrá asignados valores diferentes de Usos de la RTC, URI de notificación y URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="42912-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="42912-112">El motivo de este comportamiento de ámbito de directiva especial es que, cuando un usuario hospedado en un grupo de un sitio de oficina visita otro sitio y tiene que realizar una llamada de emergencia, se aplicará la configuración de enrutamiento de llamada E9-1-1 correspondiente a dicho sitio de red, independientemente de a qué grupo o a qué sitio esté asignado el usuario.</span><span class="sxs-lookup"><span data-stu-id="42912-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

