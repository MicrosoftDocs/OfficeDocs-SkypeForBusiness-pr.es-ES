---
title: Asignar ámbito de directiva de ubicación en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Planificación de directivas de ubicación para una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825530"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="04483-103">Asignar ámbito de directiva de ubicación en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="04483-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="04483-104">Planificación de directivas de ubicación para una implementación de E9-1-1 en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="04483-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="04483-105">Al igual que con otras directivas de Skype Empresarial Server, las directivas de ubicación se pueden asignar en varios niveles de ámbito: global, de sitio y de usuario.</span><span class="sxs-lookup"><span data-stu-id="04483-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="04483-106">Sin embargo, el ámbito de las directivas de ubicación de nivel de usuario se comporta de forma un poco diferente que con otras directivas de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="04483-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="04483-107">No solo se pueden aplicar directivas de ubicación por usuario a objetos de extremo (como usuarios y objetos de contacto de teléfono de área común), sino que también se pueden aplicar a los sitios de red de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="04483-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="04483-108">Los sitios de red son agrupaciones de subredes de clientes asociadas con una ubicación geográfica (pero no es necesario que sean todas las subredes de un sitio central o sitio de sucursal completo).</span><span class="sxs-lookup"><span data-stu-id="04483-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="04483-109">Los clientes conectados a las subredes de un sitio de red escogen automáticamente la directiva de ubicación asignada a dicho sitio de red.</span><span class="sxs-lookup"><span data-stu-id="04483-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="04483-110">Si la directiva de ubicación en el nivel de usuario se asigna tanto a un usuario como a un sitio de red, la directiva de ubicación basada en sitio de la red sustituye a cualquier otra configuración de directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="04483-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="04483-111">Cada sitio de red tiene asignada una directiva de ubicación, y cada directiva tendrá asignados valores diferentes de Uso de RTC, URI de notificación y URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="04483-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="04483-112">El motivo de este comportamiento de ámbito de directiva especial es que, cuando un usuario hospedado en un grupo de usuarios de un sitio de oficina visita otro sitio y tiene que realizar una llamada de emergencia, se aplicará la configuración de enrutamiento de llamada E9-1-1 correspondiente a dicho sitio de red independientemente de a qué grupo de usuarios o sitio esté asignado el usuario.</span><span class="sxs-lookup"><span data-stu-id="04483-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

