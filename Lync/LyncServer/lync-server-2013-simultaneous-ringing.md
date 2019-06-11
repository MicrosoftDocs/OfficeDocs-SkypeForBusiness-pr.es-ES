---
title: 'Lync Server 2013: Tono de llamada simultáneo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7303c1fc77d109bd08044c8acff56aaf538790d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="58ec7-102">Tono de llamada simultáneo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58ec7-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58ec7-103">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="58ec7-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="58ec7-104">Cuando la persona a la que se llama tiene habilitado el timbre simultáneo, el enrutamiento basado en la ubicación analiza la ubicación de la persona que llama y los puntos finales de las partes a las que se llama para determinar si se debe distribuir la llamada.</span><span class="sxs-lookup"><span data-stu-id="58ec7-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="58ec7-105">En la siguiente tabla se muestra un usuario con la configuración de llamadas simultáneas habilitada y el destino de llamadas simultáneas es un usuario en el mismo sitio de red, en un sitio de red diferente o en un sitio de red desconocido.</span><span class="sxs-lookup"><span data-stu-id="58ec7-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58ec7-106">Llamada RTC entrante para</span><span class="sxs-lookup"><span data-stu-id="58ec7-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="58ec7-107">Ubicado en el mismo sitio de red que el destinatario</span><span class="sxs-lookup"><span data-stu-id="58ec7-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="58ec7-108">Ubicado en un sitio de red distinto del sitio del destinatario</span><span class="sxs-lookup"><span data-stu-id="58ec7-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="58ec7-109">Se encuentra en un sitio de red desconocido o no está habilitado para el enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="58ec7-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58ec7-110">Usuario de Lync</span><span class="sxs-lookup"><span data-stu-id="58ec7-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="58ec7-111">Llamadas simultáneas permitidas</span><span class="sxs-lookup"><span data-stu-id="58ec7-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="58ec7-112">Llamadas simultáneas no permitidas</span><span class="sxs-lookup"><span data-stu-id="58ec7-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="58ec7-113">Llamadas simultáneas no permitidas</span><span class="sxs-lookup"><span data-stu-id="58ec7-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="58ec7-114">En la tabla siguiente se muestra una llamada de un usuario de Lync (es decir, el autor de la llamada de Lync) en el mismo sitio de red, en un sitio de red diferente o desde un sitio de red desconocido.</span><span class="sxs-lookup"><span data-stu-id="58ec7-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="58ec7-115">El destinatario de la llamada tiene un punto final de la RTC (por ejemplo, teléfono móvil) configurado como un objetivo de llamada simultánea.</span><span class="sxs-lookup"><span data-stu-id="58ec7-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="58ec7-116">En este escenario, el enrutamiento basado en la ubicación determinará si la llamada debe dirigirse al destino simultáneo (por ejemplo, teléfono móvil) del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="58ec7-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58ec7-117">Destino de llamadas simultáneas</span><span class="sxs-lookup"><span data-stu-id="58ec7-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="58ec7-118">Ubicado en el mismo sitio de red que el destinatario</span><span class="sxs-lookup"><span data-stu-id="58ec7-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="58ec7-119">Ubicado en un sitio de red distinto del sitio del destinatario</span><span class="sxs-lookup"><span data-stu-id="58ec7-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="58ec7-120">Se encuentra en un sitio de red desconocido o no está habilitado para el enrutamiento basado en la ubicación</span><span class="sxs-lookup"><span data-stu-id="58ec7-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58ec7-121">Extremo de RTC</span><span class="sxs-lookup"><span data-stu-id="58ec7-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="58ec7-122">Llamadas simultáneas permitidas a través de la directiva del enrutamiento de voz del sitio del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="58ec7-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="58ec7-123">Llamadas simultáneas permitidas a través de la directiva del enrutamiento de voz del sitio del autor de la llamada</span><span class="sxs-lookup"><span data-stu-id="58ec7-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="58ec7-124">Llamadas simultáneas permitidas a través de la directiva del enrutamiento de voz del autor de la llamada para troncos no habilitados para el enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="58ec7-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="58ec7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="58ec7-125">See Also</span></span>


[<span data-ttu-id="58ec7-126">Escenarios para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58ec7-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

