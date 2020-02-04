---
title: 'Lync Server 2013: ámbito de la Directiva de ubicación de asignación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395b8a4271338231b4c2c1927f7e40fb21a1cb14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="080a6-102">Asignación de un ámbito de directivas de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="080a6-102">Assigning location policy scope in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="080a6-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="080a6-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="080a6-104">Al igual que con otras directivas de Lync Server, las directivas de ubicación se pueden asignar a varios niveles de ámbito: global, de sitio y usuario.</span><span class="sxs-lookup"><span data-stu-id="080a6-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="080a6-105">Sin embargo, el ámbito de las directivas de ubicación de nivel de usuario tiene un bit diferente al de otras directivas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="080a6-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="080a6-106">No solo se pueden aplicar directivas de ubicación por usuario a los objetos de extremo (como usuarios y objetos de contacto de teléfono comunes), sino que también se pueden aplicar a sitios de red de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="080a6-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="080a6-107">Los sitios de red son agrupaciones de subredes de clientes asociadas con una ubicación geográfica (pero no es necesario que sean todas las subredes de un sitio central o de un sitio de sucursal completo).</span><span class="sxs-lookup"><span data-stu-id="080a6-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="080a6-108">Los clientes conectados a las subredes de un sitio de red escogen automáticamente la directiva de ubicación asignada a dicho sitio de red.</span><span class="sxs-lookup"><span data-stu-id="080a6-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="080a6-109">Si la directiva de ubicación de usuario se asigna tanto a un usuario como a un sitio de red, la directiva de ubicación basada en el sitio de red sustituye a cualquier otra configuración de directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="080a6-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="080a6-110">Cada sitio de red tiene una directiva de ubicación asignada y cada directiva tendrá asignados valores diferentes de Usos de la RTC, URI de notificación y URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="080a6-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="080a6-111">El motivo de este comportamiento de ámbito de directiva especial es que, cuando un usuario hospedado en un grupo de un sitio de oficina visita otro sitio y tiene que realizar una llamada de emergencia, se aplicará la configuración de enrutamiento de llamada E9-1-1 correspondiente a dicho sitio de red, independientemente de a qué grupo o a qué sitio esté asignado el usuario.</span><span class="sxs-lookup"><span data-stu-id="080a6-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

