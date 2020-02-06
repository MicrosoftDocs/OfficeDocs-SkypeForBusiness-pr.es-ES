---
title: Asignar ámbito de directiva de ubicación en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planear las directivas de ubicación para una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 3865db146676ed64da9422d2a8731e44451ec6ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802760"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="c9a05-103">Asignar ámbito de directiva de ubicación en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c9a05-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="c9a05-104">Planear las directivas de ubicación para una implementación de E9-1-1 en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c9a05-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c9a05-105">Al igual que con otras directivas de Skype empresarial Server, las directivas de ubicación se pueden asignar en varios niveles de ámbito: global, de sitio y de usuario.</span><span class="sxs-lookup"><span data-stu-id="c9a05-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="c9a05-106">Sin embargo, el ámbito de las directivas de ubicación de nivel de usuario tiene un bit diferente al de otras directivas de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c9a05-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="c9a05-107">No solo se pueden aplicar directivas de ubicación por usuario a los objetos de extremo (como usuarios y objetos de contacto de teléfono comunes), sino que también se pueden aplicar a sitios de red de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c9a05-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="c9a05-108">Los sitios de red son agrupaciones de subredes de clientes asociadas con una ubicación geográfica (pero no es necesario que sean todas las subredes de un sitio central o de un sitio de sucursal completo).</span><span class="sxs-lookup"><span data-stu-id="c9a05-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="c9a05-109">Los clientes conectados a las subredes de un sitio de red escogen automáticamente la directiva de ubicación asignada a dicho sitio de red.</span><span class="sxs-lookup"><span data-stu-id="c9a05-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="c9a05-110">Si la directiva de ubicación de usuario se asigna tanto a un usuario como a un sitio de red, la directiva de ubicación basada en el sitio de red sustituye a cualquier otra configuración de directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="c9a05-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="c9a05-111">Cada sitio de red tiene una directiva de ubicación asignada y cada directiva tendrá asignados valores diferentes de Usos de la RTC, URI de notificación y URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c9a05-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9a05-112">El motivo de este comportamiento de ámbito de directiva especial es que, cuando un usuario hospedado en un grupo de un sitio de oficina visita otro sitio y tiene que realizar una llamada de emergencia, se aplicará la configuración de enrutamiento de llamada E9-1-1 correspondiente a dicho sitio de red, independientemente de a qué grupo o a qué sitio esté asignado el usuario.</span><span class="sxs-lookup"><span data-stu-id="c9a05-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

